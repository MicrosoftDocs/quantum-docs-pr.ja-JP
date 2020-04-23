---
title: Q# テクニック - すべてをまとめます
description: 量子テレポーテーションを示す基本的な Q# プログラムを紹介します。
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4bd91699017e4c1acd9f4449b8a65e39bd07878e
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030567"
---
# <a name="putting-it-all-together-teleportation"></a><span data-ttu-id="2e30a-103">すべてをまとめる:テレポーテーション</span><span class="sxs-lookup"><span data-stu-id="2e30a-103">Putting It All Together: Teleportation</span></span> #
<span data-ttu-id="2e30a-104">[量子回路](xref:microsoft.quantum.concepts.circuits)で定義されているテレポーテーション回路の例に戻りましょう。</span><span class="sxs-lookup"><span data-stu-id="2e30a-104">Let's return to the example of the teleportation circuit defined in [Quantum Circuits](xref:microsoft.quantum.concepts.circuits).</span></span> <span data-ttu-id="2e30a-105">これまでに学んだ概念を説明するためにこれを使用します。</span><span class="sxs-lookup"><span data-stu-id="2e30a-105">We're going to use this to illustrate the concepts we've learned so far.</span></span> <span data-ttu-id="2e30a-106">量子テレポーテーションの説明は、理論に慣れていない人のために以下に示され、その後Q#でのコード実装のチュートリアルが続きます。</span><span class="sxs-lookup"><span data-stu-id="2e30a-106">An explanation of quantum teleportation is provided below for those who are unfamiliar with the theory, followed by a walkthrough of the code implementation in Q#.</span></span> 

## <a name="quantum-teleportation-theory"></a><span data-ttu-id="2e30a-107">量子テレポーテーション:理論</span><span class="sxs-lookup"><span data-stu-id="2e30a-107">Quantum Teleportation: Theory</span></span>
<span data-ttu-id="2e30a-108">量子テレポーテーションは、未知の量子状態('__メッセージ__'と呼ぶ)をある場所の量子ビットから別の場所の量子ビットに送信する技術です(これらの量子ビットをそれぞれ'__ここ__'と'__があります__'と呼ぶ)。</span><span class="sxs-lookup"><span data-stu-id="2e30a-108">Quantum teleportation is a technique for sending an unknown quantum state (which we'll refer to as the '__message__') from a qubit in one location to a qubit in another location (we'll refer to these qubits as '__here__' and '__there__', respectively).</span></span> <span data-ttu-id="2e30a-109">Dirac 表記を使用して、__メッセージ__をベクターとして表現できます。</span><span class="sxs-lookup"><span data-stu-id="2e30a-109">We can represent our __message__ as a vector using Dirac notation:</span></span> 

<span data-ttu-id="2e30a-110">$$ \ケット{\psi} = \{0}アルファ\ケット +{1} \ベータ\ケット $$</span><span class="sxs-lookup"><span data-stu-id="2e30a-110">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="2e30a-111">メッセージ__qubit__の状態は、$\α$ と $\beta$ の値がわからないため、不明です。</span><span class="sxs-lookup"><span data-stu-id="2e30a-111">The __message__ qubit's state is unknown to us as we do not know the values of $\alpha$ and $\beta$.</span></span>

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="2e30a-112">手順 1: 絡み合った状態を作成する</span><span class="sxs-lookup"><span data-stu-id="2e30a-112">Step 1: Create an entangled state</span></span>
<span data-ttu-id="2e30a-113">__メッセージ__を送信するために __、ここで__量子ビット__がそこに__量子ビットと絡み合う必要があります.</span><span class="sxs-lookup"><span data-stu-id="2e30a-113">In order to send the __message__ we need for the qubit __here__ to be entangled with the qubit __there__.</span></span> <span data-ttu-id="2e30a-114">これは、ハダマールゲートを適用し、続いてCNOTゲートを適用することによって達成されます。</span><span class="sxs-lookup"><span data-stu-id="2e30a-114">This is achieved by applying a Hadamard gate, followed by a CNOT gate.</span></span> <span data-ttu-id="2e30a-115">これらのゲート操作の背後にある数学を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="2e30a-115">Let's look at the math behind these gate operations.</span></span>

<span data-ttu-id="2e30a-116">私たちは __、$\ket__ {0}$ 状態の__両方で__、あちこちの量子ビットから始めます。</span><span class="sxs-lookup"><span data-stu-id="2e30a-116">We will begin with the qubits __here__ and __there__ both in the $\ket{0}$ state.</span></span> <span data-ttu-id="2e30a-117">これらの量子ビットを絡めた後、それらは状態になります:</span><span class="sxs-lookup"><span data-stu-id="2e30a-117">After entangling these qubits, they are in the state:</span></span>

<span data-ttu-id="2e30a-118">$$ \ケット{\phi^+} ={1}\frac{2}{\sqrt{00} }(\ケット + \ケット{11}) $$</span><span class="sxs-lookup"><span data-stu-id="2e30a-118">$$ \ket{\phi^+} = \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) $$</span></span>

### <a name="step-2-send-the-message"></a><span data-ttu-id="2e30a-119">手順 2: メッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="2e30a-119">Step 2: Send the message</span></span>
<span data-ttu-id="2e30a-120">__メッセージ__を送信するには、まず__メッセージ__qubit を持つ CNOT ゲートを適用し、__ここで__qubit を入力として適用します (__メッセージ__・クビットはコントロール、__ここに__クビットはターゲット・クビットです。</span><span class="sxs-lookup"><span data-stu-id="2e30a-120">To send the __message__ we first apply a CNOT gate with the __message__ qubit and __here__ qubit as inputs (the __message__ qubit being the control and the __here__ qubit being the target qubit, in this instance).</span></span> <span data-ttu-id="2e30a-121">この入力状態は、次の場合に書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="2e30a-121">This input state can be written:</span></span>

<span data-ttu-id="2e30a-122">$$ \ケット{\psi}\ケット{\phi^}} = (\{0}アルファ\ケット +{1}\ベータ\ケット{1})(\frac{2}{\sqrt{11}}(\ケット + \ケット{00}) $$</span><span class="sxs-lookup"><span data-stu-id="2e30a-122">$$ \ket{\psi}\ket{\phi^+} = (\alpha\ket{0} + \beta\ket{1})(\frac{1}{\sqrt{2}}(\ket{00} + \ket{11})) $$</span></span>

<span data-ttu-id="2e30a-123">これは次の目的に拡張されます。</span><span class="sxs-lookup"><span data-stu-id="2e30a-123">This expands to:</span></span>

<span data-ttu-id="2e30a-124">$$ \ket{\psi}\ケット{\phi^} = \frac{\α}{\sqrt{2}{000} }\ケット + \frac{\アルファ}{\sqrt{2}}\ケット{011}+ \frac{\ベータ}{\sqrt{2}}\sqrt{100} }{2}\frac{\β}\sqrt }\sqrt }\ケット }\ケット{111}\$$</span><span class="sxs-lookup"><span data-stu-id="2e30a-124">$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$</span></span>

<span data-ttu-id="2e30a-125">CNOT ゲートは、コントロールの量子ビットが 1 の場合にターゲットのクビットを反転します。</span><span class="sxs-lookup"><span data-stu-id="2e30a-125">As a reminder, the CNOT gate flips the target qubit when the control qubit is 1.</span></span> <span data-ttu-id="2e30a-126">たとえば、$\ket{000}$ を入力すると、最初のクビット (コントロール) が 0 であるため、変更は行いません。</span><span class="sxs-lookup"><span data-stu-id="2e30a-126">So for example, an input of $\ket{000}$ will result in no change as the first qubit (the control) is 0.</span></span> <span data-ttu-id="2e30a-127">ただし、最初の量子ビットが 1 (たとえば$\ket{100}$) の入力である場合を考えます。</span><span class="sxs-lookup"><span data-stu-id="2e30a-127">However, take a case where the first qubit is 1 - for example an input of $\ket{100}$.</span></span> <span data-ttu-id="2e30a-128">この例では、2 番目のクビット{110}(ターゲット) が CNOT ゲートによって反転されるので、出力は $\ket $ です。</span><span class="sxs-lookup"><span data-stu-id="2e30a-128">In this instance, the output is $\ket{110}$ as the second qubit (the target) is flipped by the CNOT gate.</span></span>

<span data-ttu-id="2e30a-129">CNOT ゲートが上記の入力に対して作用したら、出力を考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="2e30a-129">Let's now consider our output once the CNOT gate has acted on our input above.</span></span> <span data-ttu-id="2e30a-130">結果は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2e30a-130">The result is:</span></span>

<span data-ttu-id="2e30a-131">$${2}\frac{\α}{\sqrt}\{000}ケット + \frac{\アルファ{2}}{\sqrt{011} }\ケット + \frac{\ベータ{2}}\\sqrt }\ケット{110}+ \frac{\ベータ}\sqrt{2}}\ケット{101}$$</span><span class="sxs-lookup"><span data-stu-id="2e30a-131">$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$</span></span>

<span data-ttu-id="2e30a-132">__メッセージ__を送信する次の手順は、__メッセージの量子__ビット (各用語の最初のクビット) にハダマール ゲートを適用することです。</span><span class="sxs-lookup"><span data-stu-id="2e30a-132">The next step to send the __message__ is to apply a Hadamard gate to the __message__ qubit (that's the first qubit of each term).</span></span> 

<span data-ttu-id="2e30a-133">ハダマール門は次のように思い出してください。</span><span class="sxs-lookup"><span data-stu-id="2e30a-133">As a reminder, the Hadamard gate does the following:</span></span>

<span data-ttu-id="2e30a-134">入力</span><span class="sxs-lookup"><span data-stu-id="2e30a-134">Input</span></span> | <span data-ttu-id="2e30a-135">出力</span><span class="sxs-lookup"><span data-stu-id="2e30a-135">Output</span></span>
---------------------------| ---------------------------------------------------------------
<span data-ttu-id="2e30a-136">$\ケット{0}$</span><span class="sxs-lookup"><span data-stu-id="2e30a-136">$\ket{0}$</span></span>  | <span data-ttu-id="2e30a-137">$\frac{1}{2}{\sqrt}(\{0}ケット +{1}\ケット)</span><span class="sxs-lookup"><span data-stu-id="2e30a-137">$\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})$</span></span>
<span data-ttu-id="2e30a-138">$\ケット{1}$</span><span class="sxs-lookup"><span data-stu-id="2e30a-138">$\ket{1}$</span></span>  | <span data-ttu-id="2e30a-139">$\frac{1}{2}{\sqrt}(\{0}ケット -{1}\ケット)$</span><span class="sxs-lookup"><span data-stu-id="2e30a-139">$\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$</span></span>

<span data-ttu-id="2e30a-140">上記の出力の各項の最初のクビットにハダードゲートを適用すると、次の結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="2e30a-140">If we apply the Hadamard gate to the first qubit of each term of our output above, we get the following result:</span></span>

<span data-ttu-id="2e30a-141">$${2}\frac{\α}{\sqrt }(\frac{1}{\sqrt{2}{0} })\{1}ケット{00}+ \frac{\アルファ}{\sqrt{2}}(\ket{1}{2}{0} + \ket)\{1}ケット{11}+ \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ケット{0}- \ケット{1})\ケット{10}+ \frac{\ベータ}{\sqrt{2}}(\frac{1}{\sqrt})(\{2}ケット{0}{1}- \ケット{01})\ケット $$</span><span class="sxs-lookup"><span data-stu-id="2e30a-141">$$ \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{00} + \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{11} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{10} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{01} $$</span></span>

<span data-ttu-id="2e30a-142">各用語には 2 つの $\frac{1}{\sqrt{2}}$ ファクターがあることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2e30a-142">Note that each term has two $\frac{1}{\sqrt{2}}$ factors.</span></span> <span data-ttu-id="2e30a-143">これらを乗算して、次の結果を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="2e30a-143">We can multiply these out giving the following result:</span></span>

<span data-ttu-id="2e30a-144">$$ \frac{\α}{2}(\ケット{0}{1}+ \{00}ケット )\ケット{2}+ \ケット{0}+ \{1}ケット +{11} \ケット + \ケット{2}+{0} \frac{\ベータ} (\ケット{1}- \ケット ) \ ケット{10}+ \frac{\{2}ベータ} (\ケット{0}- \ケット{1})\ケット )\ケット)\ケット)\ケット)\ケット{01}</span><span class="sxs-lookup"><span data-stu-id="2e30a-144">$$ \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{01} $$</span></span>

<span data-ttu-id="2e30a-145">$\frac{1}{2}$ ファクターは各用語に共通しているので、括弧の外に持ち出すことができます。</span><span class="sxs-lookup"><span data-stu-id="2e30a-145">The  $\frac{1}{2}$ factor is common to each term so we can now take it outside the brackets:</span></span>

<span data-ttu-id="2e30a-146">{1}{2}$$ \frac \big[\α(\ケット{0}{1}+ \{00}ケット)\ケット)\{0}ケット)\{1}ケット+{11} \ケット)\ケット{0}+ \{1}ケット +{10} \ケット +{0} \ケット{1}+ \{01}ケット + \ベータ (\ケット ) \ケット \ケット \大きい] $$</span><span class="sxs-lookup"><span data-stu-id="2e30a-146">$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$</span></span>

<span data-ttu-id="2e30a-147">その後、各用語の括弧を乗算することができます:</span><span class="sxs-lookup"><span data-stu-id="2e30a-147">We can then multiply out the brackets for each term giving:</span></span>

<span data-ttu-id="2e30a-148">$$ \frac{1}{2}\big[\α\ケット{000}+{100} \アルファ\ケット{011}+ \アルファ\{111}ケット + \{010}ベータ\ケット -{110} \ベータ\ケット{001}+ \ベータ{101}\ケット - \ベータ\ケト \大きい] $$</span><span class="sxs-lookup"><span data-stu-id="2e30a-148">$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $$</span></span>

### <a name="step-3-measure-the-result"></a><span data-ttu-id="2e30a-149">ステップ 3: 結果を測定する</span><span class="sxs-lookup"><span data-stu-id="2e30a-149">Step 3: Measure the result</span></span>

<span data-ttu-id="2e30a-150">__ここ__と絡み__合っている__ため、__ここで__の測定はそこの状態に影響を与__えます__.</span><span class="sxs-lookup"><span data-stu-id="2e30a-150">Due to __here__ and __there__ being entangled, any measurement on __here__ will affect the state of __there__.</span></span> <span data-ttu-id="2e30a-151">1 番目と 2 番目の量子ビット (__メッセージ__と__ここ__) を測定すると、この絡み合いの性質により、__どのような状態にある__かを知ることができます。</span><span class="sxs-lookup"><span data-stu-id="2e30a-151">If we measure the first and second qubit (__message__ and __here__) we can learn what state __there__ is in, due to this property of entanglement.</span></span> 

* <span data-ttu-id="2e30a-152">測定して結果 00 を取得すると、重ね合わせが崩壊し、この結果と一致する項だけが残ります。</span><span class="sxs-lookup"><span data-stu-id="2e30a-152">If we measure and get a result 00, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="2e30a-153">それは$\アルファ\ケット{000}+\ベータ\ケット{001}$です。</span><span class="sxs-lookup"><span data-stu-id="2e30a-153">That's $\alpha\ket{000} +\beta\ket{001}$.</span></span> <span data-ttu-id="2e30a-154">これは$\ケット (\アルファ\ケット{00}{0}+\ベータ\ケット{1})にリファクタリングすることができます。</span><span class="sxs-lookup"><span data-stu-id="2e30a-154">This can be refactored to $\ket{00}(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="2e30a-155">したがって、最初と2番目の量子ビットを00に測定すると、3番目の量子ビット__が__$(\α\ket{0} +\beta\ket){1}の状態にあることがわかります。</span><span class="sxs-lookup"><span data-stu-id="2e30a-155">Therefore if we measure the first and second qubit to be 00, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="2e30a-156">測定して結果 01 を取得すると、重ね合わせが崩壊し、この結果と一致する項だけが残ります。</span><span class="sxs-lookup"><span data-stu-id="2e30a-156">If we measure and get a result 01, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="2e30a-157">それは$\アルファ\ケット{011}+\ベータ\ケット{010}$です。</span><span class="sxs-lookup"><span data-stu-id="2e30a-157">That's $\alpha\ket{011} +\beta\ket{010}$.</span></span> <span data-ttu-id="2e30a-158">これは$\ケット (\アルファ\ケット{01}{1}+\ベータ\ケット{0})にリファクタリングすることができます。</span><span class="sxs-lookup"><span data-stu-id="2e30a-158">This can be refactored to $\ket{01}(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="2e30a-159">したがって、最初と2番目の量子ビットを01に測定すると、3番目の量子ビット__が__$(\α\ket{1} +\beta\ket){0}の状態にあることがわかります。</span><span class="sxs-lookup"><span data-stu-id="2e30a-159">Therefore if we measure the first and second qubit to be 01, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span>
* <span data-ttu-id="2e30a-160">測定して結果 10 を取得すると、重ね合わせが崩壊し、この結果と一致する項だけが残ります。</span><span class="sxs-lookup"><span data-stu-id="2e30a-160">If we measure and get a result 10, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="2e30a-161">それは$\アルファ\ケット{100}-\ベータ\ケット{101}$です。</span><span class="sxs-lookup"><span data-stu-id="2e30a-161">That's $\alpha\ket{100} -\beta\ket{101}$.</span></span> <span data-ttu-id="2e30a-162">これは$\ケット (\アルファ\ケット{10}{0}-\ベータ\ケット{1})にリファクタリングすることができます。</span><span class="sxs-lookup"><span data-stu-id="2e30a-162">This can be refactored to $\ket{10}(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="2e30a-163">したがって、最初と2番目の量子ビットを10に測定すると、3番目の量子ビット__が__$(\α\ket{0} -\beta\ket){1}の状態にあることがわかります。</span><span class="sxs-lookup"><span data-stu-id="2e30a-163">Therefore if we measure the first and second qubit to be 10, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span>
* <span data-ttu-id="2e30a-164">測定して結果11を取得すると、重ね合わせが崩壊し、この結果と一致する項だけが残ります。</span><span class="sxs-lookup"><span data-stu-id="2e30a-164">If we measure and get a result 11, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="2e30a-165">それは$\アルファ\ケット{111}-\ベータ\ケット{110}$です。</span><span class="sxs-lookup"><span data-stu-id="2e30a-165">That's $\alpha\ket{111} -\beta\ket{110}$.</span></span> <span data-ttu-id="2e30a-166">これは$\ケット (\アルファ\ケット{11}{1}-\ベータ\ケット{0})にリファクタリングすることができます。</span><span class="sxs-lookup"><span data-stu-id="2e30a-166">This can be refactored to $\ket{11}(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="2e30a-167">したがって、1 番目と 2 番目の量子ビットを 11 に測定すると、3 番目の qubit が $(\α\ket __there__{1} -\beta\ket){0}の状態にあることがわかります。</span><span class="sxs-lookup"><span data-stu-id="2e30a-167">Therefore if we measure the first and second qubit to be 11, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span>

### <a name="step-4-interpret-the-result"></a><span data-ttu-id="2e30a-168">ステップ 4: 結果を解釈する</span><span class="sxs-lookup"><span data-stu-id="2e30a-168">Step 4: Interpret the result</span></span>

<span data-ttu-id="2e30a-169">私たちが送信したい元の__メッセージ__は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2e30a-169">As a reminder, the original __message__ we wished to send was:</span></span>

<span data-ttu-id="2e30a-170">$$ \ケット{\psi} = \{0}アルファ\ケット +{1} \ベータ\ケット $$</span><span class="sxs-lookup"><span data-stu-id="2e30a-170">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="2e30a-171">受け取った状態が意図された状態になるように、この状態に__そこに__量子ビットを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e30a-171">We need to get the __there__ qubit into this state, so that the received state is the one that was intended.</span></span> 

* <span data-ttu-id="2e30a-172">測定して00の結果を得た場合、3番目の量子ビットは、__状態__$(\α\ket{0} +\β\ket){1}です。</span><span class="sxs-lookup"><span data-stu-id="2e30a-172">If we measured and got a result of 00, then the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="2e30a-173">これは意図された__メッセージ__であるため、変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="2e30a-173">As this is the intended __message__, no alteration is required.</span></span>
* <span data-ttu-id="2e30a-174">測定して01の結果を得た場合、3番目の量子ビットは、__状態__$(\α\ket{1} +\β\ket){0}です。</span><span class="sxs-lookup"><span data-stu-id="2e30a-174">If we measured and got a result of 01, then the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="2e30a-175">これは意図した__メッセージ__とは異なりますが、NOT ゲートを適用すると、目的の状態 $(\α\ケット{0}+\{1}ベータ\ケット)$が得られます。</span><span class="sxs-lookup"><span data-stu-id="2e30a-175">This differs from the intended __message__, however applying a NOT gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="2e30a-176">測定して10の結果を得た場合、3番目の量子ビットは、__状態__$(\α\ケット{0}-\ベータ\ケット{1})です。</span><span class="sxs-lookup"><span data-stu-id="2e30a-176">If we measured and got a result of 10, then the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="2e30a-177">これは意図した__メッセージ__とは異なりますが、Z ゲートを適用すると、目的の状態 $(\α\ケット{0}+\{1}ベータ\ケット) $ が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e30a-177">This differs from the intended __message__, however applying a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="2e30a-178">測定して11の結果を得た場合、3番目の量子ビットは、__状態__$(\α\ケット{1}-\ベータ\ケット{0})です。</span><span class="sxs-lookup"><span data-stu-id="2e30a-178">If we measured and got a result of 11, then the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="2e30a-179">これは意図した__メッセージ__とは異なりますが、NOT ゲートの後に Z ゲートを適用すると、目的の状態 $(\α\ケット{0}{1}+\ベータ\ケット)$が得られます。</span><span class="sxs-lookup"><span data-stu-id="2e30a-179">This differs from the intended __message__, however applying a NOT gate followed by a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>

<span data-ttu-id="2e30a-180">要約すると、測定する場合、最初の量子ビットが1であれば、Zゲートが適用されます。</span><span class="sxs-lookup"><span data-stu-id="2e30a-180">To summarize, if we measure and the first qubit is 1, a Z gate is applied.</span></span> <span data-ttu-id="2e30a-181">測定する場合、2 番目のクビットが 1 の場合は、NOT ゲートが適用されます。</span><span class="sxs-lookup"><span data-stu-id="2e30a-181">If we measure and the second qubit is 1, a NOT gate is applied.</span></span>

### <a name="summary"></a><span data-ttu-id="2e30a-182">まとめ</span><span class="sxs-lookup"><span data-stu-id="2e30a-182">Summary</span></span>
<span data-ttu-id="2e30a-183">以下に示すテキストブック量子回路は、テレポーテーションを実装しています。</span><span class="sxs-lookup"><span data-stu-id="2e30a-183">Shown below is a text-book quantum circuit that implements the teleportation.</span></span> <span data-ttu-id="2e30a-184">左から右に移動すると、次のことがわかります。</span><span class="sxs-lookup"><span data-stu-id="2e30a-184">Moving from left to right you can see:</span></span>
- <span data-ttu-id="2e30a-185">ステップ1:ハダマール__門と__CNOTゲートを適用して__あちこち__に絡み合う。</span><span class="sxs-lookup"><span data-stu-id="2e30a-185">Step 1: Entangling __here__ and __there__ by applying a Hadamard gate and CNOT gate.</span></span>
- <span data-ttu-id="2e30a-186">ステップ 2: CNOT ゲートとハダマールゲートを使用して__メッセージ__を送信します。</span><span class="sxs-lookup"><span data-stu-id="2e30a-186">Step 2: Sending the __message__ using a CNOT gate and a Hadamard gate.</span></span>
- <span data-ttu-id="2e30a-187">ステップ3:第1および第2の量子ビット、__メッセージ__と__ここで__の測定を取る.</span><span class="sxs-lookup"><span data-stu-id="2e30a-187">Step 3: Taking a measurement of the first and second qubits, __message__ and __here__.</span></span>
- <span data-ttu-id="2e30a-188">ステップ4:ステップ3での測定結果に応じて、NOTゲートまたはZゲートを適用する。</span><span class="sxs-lookup"><span data-stu-id="2e30a-188">Step 4: Applying a NOT gate or a Z gate, depending on the result of the measurement in step 3.</span></span>

!['テレポート(msg:クビット、そこ:クビット) : ユニット'](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a><span data-ttu-id="2e30a-190">量子テレポーテーション:コード</span><span class="sxs-lookup"><span data-stu-id="2e30a-190">Quantum Teleportation: Code</span></span>

<span data-ttu-id="2e30a-191">私たちは量子テレポーテーションのための私たちの回路を持っています:</span><span class="sxs-lookup"><span data-stu-id="2e30a-191">We have our circuit for quantum teleportation:</span></span>

!['テレポート(msg:クビット、そこ:クビット) : ユニット'](~/media/teleportation.svg)

<span data-ttu-id="2e30a-193">この量子回路の各ステップをQ#に変換できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2e30a-193">We can now translate each of the steps in this quantum circuit into Q#.</span></span>

### <a name="step-0-definition"></a><span data-ttu-id="2e30a-194">ステップ 0: 定義</span><span class="sxs-lookup"><span data-stu-id="2e30a-194">Step 0: Definition</span></span>
<span data-ttu-id="2e30a-195">テレポーテーションを行う際には、送信したい__メッセージ__と、そのメッセージをどこに送信したいのかを知る必要__があります__。</span><span class="sxs-lookup"><span data-stu-id="2e30a-195">When we perform teleportation, we must know the __message__ we wish to send, and where we wish to send it (__there__).</span></span> <span data-ttu-id="2e30a-196">このため、引数として 2 つの量子ビットを与えられた新しいテレポート操作を定義し、`msg`と`there`:</span><span class="sxs-lookup"><span data-stu-id="2e30a-196">For this reason, we begin by defining a new Teleport operation that is given two qubits as arguments, `msg` and `there`:</span></span>

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

<span data-ttu-id="2e30a-197">また、`here``using`ブロックで達成する qubit を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e30a-197">We also need to allocate a qubit `here` which we achieve with a `using` block:</span></span>

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="2e30a-198">手順 1: 絡み合った状態を作成する</span><span class="sxs-lookup"><span data-stu-id="2e30a-198">Step 1: Create an entangled state</span></span>
<span data-ttu-id="2e30a-199">その後、と 操作を使用して、`here`絡`there`み合った@"microsoft.quantum.intrinsic.h"ペア@"microsoft.quantum.intrinsic.cnot"を作成できます。</span><span class="sxs-lookup"><span data-stu-id="2e30a-199">We can then create the entangled pair between `here` and `there` by using the @"microsoft.quantum.intrinsic.h" and @"microsoft.quantum.intrinsic.cnot" operations:</span></span>

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a><span data-ttu-id="2e30a-200">手順 2: メッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="2e30a-200">Step 2: Send the message</span></span>
<span data-ttu-id="2e30a-201">次の $\演算子名 {CNOT}$ と $H$ ゲートを使用して、メッセージの量子ビットを移動します。</span><span class="sxs-lookup"><span data-stu-id="2e30a-201">We then use the next $\operatorname{CNOT}$ and $H$ gates to move our message qubit:</span></span>

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a><span data-ttu-id="2e30a-202">ステップ 3 & 4: 結果の測定と解釈</span><span class="sxs-lookup"><span data-stu-id="2e30a-202">Step 3 & 4: Measuring and interpreting the result</span></span>
<span data-ttu-id="2e30a-203">最後@"microsoft.quantum.intrinsic.m"に、測定を実行し、必要なゲート操作を実行して、`if`必要な状態を取得します。</span><span class="sxs-lookup"><span data-stu-id="2e30a-203">Finally, we use @"microsoft.quantum.intrinsic.m" to perform the measurements and perform the necessary gate operations to get the desired state, as denoted by `if` statements:</span></span>

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

### <a name="step-5-restarting-the-qubit-register"></a><span data-ttu-id="2e30a-204">手順 5: qubit レジスタを再起動する</span><span class="sxs-lookup"><span data-stu-id="2e30a-204">Step 5: Restarting the qubit register</span></span>

<span data-ttu-id="2e30a-205">Q# の各操作の最後に、qubits を状態 $\ket{0}$にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e30a-205">At the end of every Q# operation we need to let the qubits in the state $\ket{0}$.</span></span> <span data-ttu-id="2e30a-206">すべての量子ビット@"microsoft.quantum.intrinsic.reset"をゼロ状態に再起動するために使用することができ、これは私たちの操作を終了します。</span><span class="sxs-lookup"><span data-stu-id="2e30a-206">We can use @"microsoft.quantum.intrinsic.reset" to restart all the qubits to the zero state and this will finish our operation.</span></span>

```qsharp
        Reset(msg);
        Reset(here);
        Reset(there);
    }
}
```


