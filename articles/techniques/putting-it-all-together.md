---
title: 'すべてをまとめておく-Q # テクニック |Microsoft Docs'
description: 'まとめ: Q # の手法'
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 3605826da159757d4b321dbf4ec6acd7f4e6be05
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820166"
---
# <a name="putting-it-all-together-teleportation"></a><span data-ttu-id="82d04-103">すべてをまとめます。</span><span class="sxs-lookup"><span data-stu-id="82d04-103">Putting It All Together: Teleportation</span></span> #
<span data-ttu-id="82d04-104">「[クォンタム回線](xref:microsoft.quantum.concepts.circuits)」で定義されている例に戻りましょう。</span><span class="sxs-lookup"><span data-stu-id="82d04-104">Let's return to the example of the teleportation circuit defined in [Quantum Circuits](xref:microsoft.quantum.concepts.circuits).</span></span> <span data-ttu-id="82d04-105">これまでに学習した概念を説明するために、これを使用します。</span><span class="sxs-lookup"><span data-stu-id="82d04-105">We're going to use this to illustrate the concepts we've learned so far.</span></span> <span data-ttu-id="82d04-106">ここでは、理論に習熟している方について説明し、その後に Q # でのコード実装のチュートリアルを示します。</span><span class="sxs-lookup"><span data-stu-id="82d04-106">An explanation of quantum teleportation is provided below for those who are unfamiliar with the theory, followed by a walkthrough of the code implementation in Q#.</span></span> 

## <a name="quantum-teleportation-theory"></a><span data-ttu-id="82d04-107">クォンタムの受付: 理論</span><span class="sxs-lookup"><span data-stu-id="82d04-107">Quantum Teleportation: Theory</span></span>
<span data-ttu-id="82d04-108">"__メッセージ__" と呼ばれる不明なクォンタムの状態を、ある場所の qubit から別の場所にある qubit に送信するための手法です (これらの qubit はそれぞれ ' ここ ' と '__ここ__ __' と__呼ばれています)。</span><span class="sxs-lookup"><span data-stu-id="82d04-108">Quantum teleportation is a technique for sending an unknown quantum state (which we'll refer to as the '__message__') from a qubit in one location to a qubit in another location (we'll refer to these qubits as '__here__' and '__there__', respectively).</span></span> <span data-ttu-id="82d04-109">Dirac 表記を使用して、__メッセージ__をベクトルとして表すことができます。</span><span class="sxs-lookup"><span data-stu-id="82d04-109">We can represent our __message__ as a vector using Dirac notation:</span></span> 

<span data-ttu-id="82d04-110">$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $</span><span class="sxs-lookup"><span data-stu-id="82d04-110">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="82d04-111">$ \ Alpha $ と $ \ ベータ $ の値がわからないため、__メッセージ__qubit の状態は不明です。</span><span class="sxs-lookup"><span data-stu-id="82d04-111">The __message__ qubit's state is unknown to us as we do not know the values of $\alpha$ and $\beta$.</span></span>

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="82d04-112">手順 1: ありの状態を作成する</span><span class="sxs-lookup"><span data-stu-id="82d04-112">Step 1: Create an entangled state</span></span>
<span data-ttu-id="82d04-113">__メッセージ__を送信するには、__ここ__に qubit を入力する必要が__あります。__</span><span class="sxs-lookup"><span data-stu-id="82d04-113">In order to send the __message__ we need for the qubit __here__ to be entangled with the qubit __there__.</span></span> <span data-ttu-id="82d04-114">これを実現するには、Hadamard ゲートを適用し、その後に CNOT gate を適用します。</span><span class="sxs-lookup"><span data-stu-id="82d04-114">This is achieved by applying a Hadamard gate, followed by a CNOT gate.</span></span> <span data-ttu-id="82d04-115">これらのゲート操作の背後にある数学を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="82d04-115">Let's look at the math behind these gate operations.</span></span>

<span data-ttu-id="82d04-116">__ここ__では qubits から開始し、__両方とも $__ \ket{0}$ 状態にします。</span><span class="sxs-lookup"><span data-stu-id="82d04-116">We will begin with the qubits __here__ and __there__ both in the $\ket{0}$ state.</span></span> <span data-ttu-id="82d04-117">これらの qubits を entangling した後、次のような状態になります。</span><span class="sxs-lookup"><span data-stu-id="82d04-117">After entangling these qubits, they are in the state:</span></span>

<span data-ttu-id="82d04-118">$ $ \ket{\phi ^ +} = \ frac{1}{\ sqrt{2}} (\ket{00} + \ket{11}) $ $</span><span class="sxs-lookup"><span data-stu-id="82d04-118">$$ \ket{\phi^+} = \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) $$</span></span>

### <a name="step-2-send-the-message"></a><span data-ttu-id="82d04-119">手順 2: メッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="82d04-119">Step 2: Send the message</span></span>
<span data-ttu-id="82d04-120">__メッセージ__を送信するには、まず、__メッセージ__QUBIT を含む cnot gate を適用し、__次__に入力として qubit を適用します (この例では、__メッセージ__qubit がコントロールで、__ここ__ではターゲット qubit になります)。</span><span class="sxs-lookup"><span data-stu-id="82d04-120">To send the __message__ we first apply a CNOT gate with the __message__ qubit and __here__ qubit as inputs (the __message__ qubit being the control and the __here__ qubit being the target qubit, in this instance).</span></span> <span data-ttu-id="82d04-121">この入力状態は、次のように記述できます。</span><span class="sxs-lookup"><span data-stu-id="82d04-121">This input state can be written:</span></span>

<span data-ttu-id="82d04-122">$ $ \ket{\psi}\ket{\phi ^ +} = (\alpha\ket{0} + \beta\ket{1}) (\ frac{1}{\ sqrt{2}} (\ket{00} + \ket{11})) $ $</span><span class="sxs-lookup"><span data-stu-id="82d04-122">$$ \ket{\psi}\ket{\phi^+} = (\alpha\ket{0} + \beta\ket{1})(\frac{1}{\sqrt{2}}(\ket{00} + \ket{11})) $$</span></span>

<span data-ttu-id="82d04-123">次のように展開されます。</span><span class="sxs-lookup"><span data-stu-id="82d04-123">This expands to:</span></span>

<span data-ttu-id="82d04-124">$ $ \ket{\psi}\ket{\phi ^ +} = \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{100} + \frac{\beta}{\sqrt{2}} \ket{111} $ $</span><span class="sxs-lookup"><span data-stu-id="82d04-124">$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$</span></span>

<span data-ttu-id="82d04-125">なお、コントロール qubit が1の場合、CNOT gate はターゲットの qubit を反転します。</span><span class="sxs-lookup"><span data-stu-id="82d04-125">As a reminder, the CNOT gate flips the target qubit when the control qubit is 1.</span></span> <span data-ttu-id="82d04-126">たとえば、$ \ket{000}$ を入力すると、最初の qubit (コントロール) は0になり、変更は行われません。</span><span class="sxs-lookup"><span data-stu-id="82d04-126">So for example, an input of $\ket{000}$ will result in no change as the first qubit (the control) is 0.</span></span> <span data-ttu-id="82d04-127">ただし、最初の qubit が 1 (たとえば、$ \ket{100}$ の入力) である場合は、</span><span class="sxs-lookup"><span data-stu-id="82d04-127">However, take a case where the first qubit is 1 - for example an input of $\ket{100}$.</span></span> <span data-ttu-id="82d04-128">このインスタンスでは、2番目の qubit (ターゲット) が CNOT gate によって反転されているため、出力は $ \ket{110}$ になります。</span><span class="sxs-lookup"><span data-stu-id="82d04-128">In this instance, the output is $\ket{110}$ as the second qubit (the target) is flipped by the CNOT gate.</span></span>

<span data-ttu-id="82d04-129">ここでは、CNOT gate が前述の入力を操作した後の出力について考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="82d04-129">Let's now consider our output once the CNOT gate has acted on our input above.</span></span> <span data-ttu-id="82d04-130">結果は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="82d04-130">The result is:</span></span>

<span data-ttu-id="82d04-131">$ $ \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{110} + \frac{\beta}{\sqrt{2}} \ket{101} $ $</span><span class="sxs-lookup"><span data-stu-id="82d04-131">$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$</span></span>

<span data-ttu-id="82d04-132">__メッセージ__を送信する次の手順では、Hadamard gate を__メッセージ__qubit (各用語の最初の qubit) に適用します。</span><span class="sxs-lookup"><span data-stu-id="82d04-132">The next step to send the __message__ is to apply a Hadamard gate to the __message__ qubit (that's the first qubit of each term).</span></span> 

<span data-ttu-id="82d04-133">リマインダーとして、Hadamard ゲートは次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="82d04-133">As a reminder, the Hadamard gate does the following:</span></span>

<span data-ttu-id="82d04-134">Input (入力)</span><span class="sxs-lookup"><span data-stu-id="82d04-134">Input</span></span> | <span data-ttu-id="82d04-135">出力</span><span class="sxs-lookup"><span data-stu-id="82d04-135">Output</span></span>
---------------------------| ---------------------------------------------------------------
<span data-ttu-id="82d04-136">$ \ket{0}$</span><span class="sxs-lookup"><span data-stu-id="82d04-136">$\ket{0}$</span></span>  | <span data-ttu-id="82d04-137">$ \ frac{1}{\ sqrt{2}} (\ket{0} + \ket{1}) $</span><span class="sxs-lookup"><span data-stu-id="82d04-137">$\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})$</span></span>
<span data-ttu-id="82d04-138">$ \ket{1}$</span><span class="sxs-lookup"><span data-stu-id="82d04-138">$\ket{1}$</span></span>  | <span data-ttu-id="82d04-139">$ \ frac{1}{\ sqrt{2}} (\ket{0}-\ket{1}) $</span><span class="sxs-lookup"><span data-stu-id="82d04-139">$\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$</span></span>

<span data-ttu-id="82d04-140">上記の出力の各用語の最初の qubit に Hadamard ゲートを適用すると、次の結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="82d04-140">If we apply the Hadamard gate to the first qubit of each term of our output above, we get the following result:</span></span>

<span data-ttu-id="82d04-141">$ $ \frac{\alpha}{\sqrt{2}} (\ frac{1}{\ sqrt{2}} (\ket{0} + \ket{1})) \ket{00} + \frac{\alpha}{\sqrt{2}} (\ frac{1}{\ sqrt{2}} (\ket{0} + \ket{1})) \ket{11} + \frac{\beta}{\sqrt{2}} (\ frac{1}{\ sqrt{2}} (\ket{0}-\ket{1})) \ket{10} + \frac{\beta}{\sqrt{2}} (-frac{1}{\ sqrt{2}} (\ket{0}-\ket{1})) \ket{01} $ $</span><span class="sxs-lookup"><span data-stu-id="82d04-141">$$ \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{00} + \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{11} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{10} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{01} $$</span></span>

<span data-ttu-id="82d04-142">各用語には $2/frac{1}{/sqrt{2}} $ 要因があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="82d04-142">Note that each term has two $\frac{1}{\sqrt{2}}$ factors.</span></span> <span data-ttu-id="82d04-143">次の結果を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="82d04-143">We can multiply these out giving the following result:</span></span>

<span data-ttu-id="82d04-144">$ $ \frac{\alpha}{2}(\ket{0} + \ket{1}) \ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1}) \ket{11} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{10} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{01} $ $</span><span class="sxs-lookup"><span data-stu-id="82d04-144">$$ \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{01} $$</span></span>

<span data-ttu-id="82d04-145">$ & Frac{1}{2}$ factor は各用語に共通であるため、角かっこの外側に移動できます。</span><span class="sxs-lookup"><span data-stu-id="82d04-145">The  $\frac{1}{2}$ factor is common to each term so we can now take it outside the brackets:</span></span>

<span data-ttu-id="82d04-146">$ $ \ frac{1}{2}big [\ alpha (\ket{0} + \ket{1}) \ket{00} + \ アルファ (\ket{0} + \ket{1}) \ket{11} + \ beta (\ket{0}-\ket{1}) \ket{10} + \ beta (\ket{0}-\ket{1}) \ket{01}</span><span class="sxs-lookup"><span data-stu-id="82d04-146">$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$</span></span>

<span data-ttu-id="82d04-147">次に、各用語の角かっこを掛けて、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="82d04-147">We can then multiply out the brackets for each term giving:</span></span>

<span data-ttu-id="82d04-148">$ $ \ frac{1}{2}\ big [\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010}-\beta\ket{110} + \beta\ket{001}-\beta\ket{101}\ big] $ $</span><span class="sxs-lookup"><span data-stu-id="82d04-148">$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $$</span></span>

### <a name="step-3-measure-the-result"></a><span data-ttu-id="82d04-149">手順 3: 結果を測定する</span><span class="sxs-lookup"><span data-stu-id="82d04-149">Step 3: Measure the result</span></span>

<span data-ttu-id="82d04-150">__ここ__ __では__、この__ような測定__値__があるため__、その状態に影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="82d04-150">Due to __here__ and __there__ being entangled, any measurement on __here__ will affect the state of __there__.</span></span> <span data-ttu-id="82d04-151">1番目と2番目の qubit (__メッセージ__と__ここで__) を測定する__場合は、__ このプロパティによってどのような状態になっているかを知ることができます。</span><span class="sxs-lookup"><span data-stu-id="82d04-151">If we measure the first and second qubit (__message__ and __here__) we can learn what state __there__ is in, due to this property of entanglement.</span></span> 

* <span data-ttu-id="82d04-152">測定して結果00を取得すると、法則は折りたたまれ、この結果と一致する用語のみが残ります。</span><span class="sxs-lookup"><span data-stu-id="82d04-152">If we measure and get a result 00, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="82d04-153">$ \Alpha\ket{000} + \beta\ket{001}$ です。</span><span class="sxs-lookup"><span data-stu-id="82d04-153">That's $\alpha\ket{000} +\beta\ket{001}$.</span></span> <span data-ttu-id="82d04-154">これは、$ \ket{00}(\alpha\ket{0} + \beta\ket{1}) $ にリファクタリングできます。</span><span class="sxs-lookup"><span data-stu-id="82d04-154">This can be refactored to $\ket{00}(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="82d04-155">したがって、1番目と2番目の qubit を00として測定した場合、3番目の qubit__が state__$ (\alpha\ket{0} + \beta\ket{1}) $ にあることがわかります。</span><span class="sxs-lookup"><span data-stu-id="82d04-155">Therefore if we measure the first and second qubit to be 00, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="82d04-156">結果01を測定して取得した場合、法則は折りたたまれ、この結果と一致する用語のみが残ります。</span><span class="sxs-lookup"><span data-stu-id="82d04-156">If we measure and get a result 01, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="82d04-157">$ \Alpha\ket{011} + \beta\ket{010}$ です。</span><span class="sxs-lookup"><span data-stu-id="82d04-157">That's $\alpha\ket{011} +\beta\ket{010}$.</span></span> <span data-ttu-id="82d04-158">これは、$ \ket{01}(\alpha\ket{1} + \beta\ket{0}) $ にリファクタリングできます。</span><span class="sxs-lookup"><span data-stu-id="82d04-158">This can be refactored to $\ket{01}(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="82d04-159">したがって、1番目と2番目の qubit を01として測定した場合、3番目の qubit__が state__$ (\alpha\ket{1} + \beta\ket{0}) $ にあることがわかります。</span><span class="sxs-lookup"><span data-stu-id="82d04-159">Therefore if we measure the first and second qubit to be 01, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span>
* <span data-ttu-id="82d04-160">評価して結果10を取得すると、法則は折りたたまれ、この結果との間には一致する語句だけが残ります。</span><span class="sxs-lookup"><span data-stu-id="82d04-160">If we measure and get a result 10, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="82d04-161">これは $ \alpha\ket{100}-\beta\ket{101}$ です。</span><span class="sxs-lookup"><span data-stu-id="82d04-161">That's $\alpha\ket{100} -\beta\ket{101}$.</span></span> <span data-ttu-id="82d04-162">これは、$ \ket{10}(\alpha\ket{0}-\beta\ket{1}) $ にリファクタリングできます。</span><span class="sxs-lookup"><span data-stu-id="82d04-162">This can be refactored to $\ket{10}(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="82d04-163">したがって、1番目と2番目の qubit を10に測定した場合、3番目の qubit__が state__$ (\alpha\ket{0}-\beta\ket{1}) $ にあることがわかります。</span><span class="sxs-lookup"><span data-stu-id="82d04-163">Therefore if we measure the first and second qubit to be 10, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span>
* <span data-ttu-id="82d04-164">結果11を測定して取得した場合、法則は折りたたまれ、この結果と一致する用語のみが残ります。</span><span class="sxs-lookup"><span data-stu-id="82d04-164">If we measure and get a result 11, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="82d04-165">これは $ \alpha\ket{111}-\beta\ket{110}$ です。</span><span class="sxs-lookup"><span data-stu-id="82d04-165">That's $\alpha\ket{111} -\beta\ket{110}$.</span></span> <span data-ttu-id="82d04-166">これは、$ \ket{11}(\alpha\ket{1}-\beta\ket{0}) $ にリファクタリングできます。</span><span class="sxs-lookup"><span data-stu-id="82d04-166">This can be refactored to $\ket{11}(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="82d04-167">したがって、1番目と2番目の qubit を11に測定した場合、3番目の qubit__が state__$ (\alpha\ket{1}-\beta\ket{0}) $ にあることがわかります。</span><span class="sxs-lookup"><span data-stu-id="82d04-167">Therefore if we measure the first and second qubit to be 11, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span>

### <a name="step-4-interpret-the-result"></a><span data-ttu-id="82d04-168">手順 4: 結果を解釈する</span><span class="sxs-lookup"><span data-stu-id="82d04-168">Step 4: Interpret the result</span></span>

<span data-ttu-id="82d04-169">リマインダーとして、送信する元の__メッセージ__は次のようになりました。</span><span class="sxs-lookup"><span data-stu-id="82d04-169">As a reminder, the original __message__ we wished to send was:</span></span>

<span data-ttu-id="82d04-170">$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $</span><span class="sxs-lookup"><span data-stu-id="82d04-170">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="82d04-171">受信状態が想定されているものであるように、この状態に__ある__qubit を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82d04-171">We need to get the __there__ qubit into this state, so that the received state is the one that was intended.</span></span> 

* <span data-ttu-id="82d04-172">測定して00の結果を得た場合、3番目の qubit は state $ (\alpha\ket{0} + \beta\ket{1}) $ に__あり__ます。</span><span class="sxs-lookup"><span data-stu-id="82d04-172">If we measured and got a result of 00, then the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="82d04-173">これは目的の__メッセージ__であるため、変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="82d04-173">As this is the intended __message__, no alteration is required.</span></span>
* <span data-ttu-id="82d04-174">を測定し、結果を01にした場合、3番目の qubit は state $ (\alpha\ket{1} + \beta\ket{0}) $ に__あり__ます。</span><span class="sxs-lookup"><span data-stu-id="82d04-174">If we measured and got a result of 01, then the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="82d04-175">これは目的の__メッセージ__とは異なりますが、NOT gate を適用すると、目的の状態 $ (\alpha\ket{0} + \beta\ket{1}) $ になります。</span><span class="sxs-lookup"><span data-stu-id="82d04-175">This differs from the intended __message__, however applying a NOT gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="82d04-176">測定し、結果が10の場合、3番目の qubit は state $ (\alpha\ket{0}-\beta\ket{1}) $ に__あり__ます。</span><span class="sxs-lookup"><span data-stu-id="82d04-176">If we measured and got a result of 10, then the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="82d04-177">これは目的の__メッセージ__とは異なりますが、Z ゲートを適用すると、目的の状態 $ (\alpha\ket{0} + \beta\ket{1}) $ になります。</span><span class="sxs-lookup"><span data-stu-id="82d04-177">This differs from the intended __message__, however applying a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="82d04-178">測定し、結果が11の場合、3番目の qubit は state $ (\alpha\ket{1}-\beta\ket{0}) $ に__あり__ます。</span><span class="sxs-lookup"><span data-stu-id="82d04-178">If we measured and got a result of 11, then the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="82d04-179">これは目的の__メッセージ__とは異なりますが、NOT ゲートの後に Z ゲートを適用すると、目的の状態 $ (\alpha\ket{0} + \beta\ket{1}) $ が適用されます。</span><span class="sxs-lookup"><span data-stu-id="82d04-179">This differs from the intended __message__, however applying a NOT gate followed by a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>

<span data-ttu-id="82d04-180">まとめると、測定し、最初の qubit が1の場合、Z ゲートが適用されます。</span><span class="sxs-lookup"><span data-stu-id="82d04-180">To summarize, if we measure and the first qubit is 1, a Z gate is applied.</span></span> <span data-ttu-id="82d04-181">測定し、2番目の qubit が1の場合、NOT gate が適用されます。</span><span class="sxs-lookup"><span data-stu-id="82d04-181">If we measure and the second qubit is 1, a NOT gate is applied.</span></span>

### <a name="summary"></a><span data-ttu-id="82d04-182">概要</span><span class="sxs-lookup"><span data-stu-id="82d04-182">Summary</span></span>
<span data-ttu-id="82d04-183">次に示すのは、電話を実装するテキスト帳のクォンタム回線です。</span><span class="sxs-lookup"><span data-stu-id="82d04-183">Shown below is a text-book quantum circuit that implements the teleportation.</span></span> <span data-ttu-id="82d04-184">左から右に移動すると、次のように表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="82d04-184">Moving from left to right you can see:</span></span>
- <span data-ttu-id="82d04-185">手順 1: Hadamard ゲートと CNOT gate を適用__して、__ __ここ__に Entangling します。</span><span class="sxs-lookup"><span data-stu-id="82d04-185">Step 1: Entangling __here__ and __there__ by applying a Hadamard gate and CNOT gate.</span></span>
- <span data-ttu-id="82d04-186">手順 2: CNOT ゲートと Hadamard gate を使用して__メッセージ__を送信する。</span><span class="sxs-lookup"><span data-stu-id="82d04-186">Step 2: Sending the __message__ using a CNOT gate and a Hadamard gate.</span></span>
- <span data-ttu-id="82d04-187">手順 3: 1 番目と2番目の qubits、__メッセージ__、__およびの__測定値を取得します。</span><span class="sxs-lookup"><span data-stu-id="82d04-187">Step 3: Taking a measurement of the first and second qubits, __message__ and __here__.</span></span>
- <span data-ttu-id="82d04-188">手順 4: 手順 3. で測定の結果に応じて、NOT gate または Z ゲートを適用します。</span><span class="sxs-lookup"><span data-stu-id="82d04-188">Step 4: Applying a NOT gate or a Z gate, depending on the result of the measurement in step 3.</span></span>

![' テレポート (msg: Qubit、: Qubit): Unit '](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a><span data-ttu-id="82d04-190">クォンタム受付: コード</span><span class="sxs-lookup"><span data-stu-id="82d04-190">Quantum Teleportation: Code</span></span>

<span data-ttu-id="82d04-191">Quantum の回線を使用しています。</span><span class="sxs-lookup"><span data-stu-id="82d04-191">We have our circuit for quantum teleportation:</span></span>

![' テレポート (msg: Qubit、: Qubit): Unit '](~/media/teleportation.svg)

<span data-ttu-id="82d04-193">これで、この量子回線の各ステップを Q # に変換できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="82d04-193">We can now translate each of the steps in this quantum circuit into Q#.</span></span>

### <a name="step-0-definition"></a><span data-ttu-id="82d04-194">手順 0: 定義</span><span class="sxs-lookup"><span data-stu-id="82d04-194">Step 0: Definition</span></span>
<span data-ttu-id="82d04-195">電話をかけるときは、送信する__メッセージ__と送信する場所 (ここに__あり__ます) を把握しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="82d04-195">When we perform teleportation, we must know the __message__ we wish to send, and where we wish to send it (__there__).</span></span> <span data-ttu-id="82d04-196">このため、最初に新しいテレポート操作を定義します。これには、引数として2つの qubits、`msg` と `there`を指定します。</span><span class="sxs-lookup"><span data-stu-id="82d04-196">For this reason, we begin by defining a new Teleport operation that is given two qubits as arguments, `msg` and `there`:</span></span>

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

<span data-ttu-id="82d04-197">また、`using` ブロックで実現する qubit `here` を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="82d04-197">We also need to allocate a qubit `here` which we achieve with a `using` block:</span></span>

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="82d04-198">手順 1: ありの状態を作成する</span><span class="sxs-lookup"><span data-stu-id="82d04-198">Step 1: Create an entangled state</span></span>
<span data-ttu-id="82d04-199">次に、@"microsoft.quantum.intrinsic.h" と @"microsoft.quantum.intrinsic.cnot" の操作を使用して、`here` と `there` の間にありのペアを作成できます。</span><span class="sxs-lookup"><span data-stu-id="82d04-199">We can then create the entangled pair between `here` and `there` by using the @"microsoft.quantum.intrinsic.h" and @"microsoft.quantum.intrinsic.cnot" operations:</span></span>

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a><span data-ttu-id="82d04-200">手順 2: メッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="82d04-200">Step 2: Send the message</span></span>
<span data-ttu-id="82d04-201">次に、$ & $H $ ゲートを使用して、メッセージ qubit を移動します。</span><span class="sxs-lookup"><span data-stu-id="82d04-201">We then use the next $\operatorname{CNOT}$ and $H$ gates to move our message qubit:</span></span>

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a><span data-ttu-id="82d04-202">手順 3 & 4: 結果の測定と解釈</span><span class="sxs-lookup"><span data-stu-id="82d04-202">Step 3 & 4: Measuring and interpreting the result</span></span>
<span data-ttu-id="82d04-203">最後に、`if` ステートメントで示されているように、@"microsoft.quantum.intrinsic.m" を使用して測定を実行し、必要なゲート操作を実行して目的の状態を取得します。</span><span class="sxs-lookup"><span data-stu-id="82d04-203">Finally, we use @"microsoft.quantum.intrinsic.m" to perform the measurements and perform the necessary gate operations to get the desired state, as denoted by `if` statements:</span></span>

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

<span data-ttu-id="82d04-204">これにより、`here`の割り当てを解除し、本文を終了して、操作を終了できるようになります。</span><span class="sxs-lookup"><span data-stu-id="82d04-204">This finishes the definition of our teleportation operator, so we can deallocate `here`, end the body, and end the operation.</span></span>

```qsharp
    }
}
```
