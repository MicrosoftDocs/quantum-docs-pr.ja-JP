---
title: 複数の量子ビット
description: 2つ以上の qubits に対して操作を実行する方法について説明します。
author: QuantumWriter
uid: microsoft.quantum.concepts.multiple-qubits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
ms.openlocfilehash: 224bd5165f508f6cd1fdb85fb5c14ba2e23e59ea
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630377"
---
# <a name="multiple-qubits"></a><span data-ttu-id="1af42-103">複数の Qubits</span><span class="sxs-lookup"><span data-stu-id="1af42-103">Multiple Qubits</span></span>

<span data-ttu-id="1af42-104">シングル qubit ゲートには、特定の時点で複数の状態にする機能など、いくつかのカウンター直感的な機能がありますが、1つのクォンタムコンピューターに存在するものがシングル qubit ゲートの場合は、計算能力を備えたデバイスを使用します。これは、電卓でも古典的な cray で dwarfed ます。</span><span class="sxs-lookup"><span data-stu-id="1af42-104">While single-qubit gates possess some counter-intuitive features, such as the ability to be in more than one state at a given time, if all we had in a quantum computer were single-qubit gates then we would have a device with computational power that would be dwarfed by even a calculator let alone a classical supercomputer.</span></span>
<span data-ttu-id="1af42-105">クォンタムコンピューティングの真の力は、qubits の数を増やすと明らかになります。</span><span class="sxs-lookup"><span data-stu-id="1af42-105">The true power of quantum computing only becomes evident as we increase the number of qubits.</span></span>
<span data-ttu-id="1af42-106">クォンタムの状態ベクターのベクター空間の次元が、qubits の数で指数関数的に増加するため、この機能は部分的に発生します。</span><span class="sxs-lookup"><span data-stu-id="1af42-106">This power arises, in part, because the dimension of the vector space of quantum state vectors grows exponentially with the number of qubits.</span></span>
<span data-ttu-id="1af42-107">つまり、1つの qubit をモデル化することはできますが、50-qubit クォンタムの計算をシミュレートすると、既存のスーパースーパーの制限が確実にプッシュされます。</span><span class="sxs-lookup"><span data-stu-id="1af42-107">This means that while a single qubit can be trivially modeled, simulating a fifty-qubit quantum computation would arguably push the limits of existing supercomputers.</span></span>
<span data-ttu-id="1af42-108">1つの追加の qubit だけで計算のサイズを大きくすると、状態を格納するために必要なメモリが*倍増*し、計算時間が約*2 倍*になります。</span><span class="sxs-lookup"><span data-stu-id="1af42-108">Increasing the size of the computation by only one additional qubit *doubles* the memory required to store the state and roughly *doubles* the computational time.</span></span>
<span data-ttu-id="1af42-109">このように計算能力が急速に倍増するのは、比較的少数の qubits を使用しているクォンタムコンピューターが、今日の最も強力なスーパースーパーコンピューターと明日のコンピューティングタスクに比べてはるかに長いためです。</span><span class="sxs-lookup"><span data-stu-id="1af42-109">This rapid doubling of computational power is why a quantum computer with a relatively small number of qubits can far surpass the most powerful supercomputers of today, tomorrow and beyond for some computational tasks.</span></span>

<span data-ttu-id="1af42-110">クォンタムの状態ベクターに指数的な増加があるのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="1af42-110">Why do we have exponential growth for quantum state vectors?</span></span>  <span data-ttu-id="1af42-111">このセクションの目的は、シングル qubit 状態からマルチ qubit 状態を構築するために使用されるルールを確認することと、一般的な多対ビットクォンタムコンピュータを形成するためにゲートセットに含める必要があるゲート操作について説明することです。</span><span class="sxs-lookup"><span data-stu-id="1af42-111">Our goal in this section is to review the rules used to build multi-qubit states out of single-qubit states as well as discuss the gate operations that we need to include in our gate set to form a universal many-qubit quantum computer.</span></span>
<span data-ttu-id="1af42-112">これらのツールは、Q # コードでよく使用されるゲートセットを理解するために必要です。また、結び付きや干渉などの量子効果が古典のコンピューティングより強力なものである理由についても理解するために必要です。</span><span class="sxs-lookup"><span data-stu-id="1af42-112">These tools are absolutely necessary to understand the gate sets that are commonly used in Q# code and also to gain intuition about why quantum effects such as entanglement or interference render quantum computing more powerful than classical computing.</span></span>

## <a name="representing-two-qubits"></a><span data-ttu-id="1af42-113">2つの Qubits を表す</span><span class="sxs-lookup"><span data-stu-id="1af42-113">Representing Two Qubits</span></span>
<span data-ttu-id="1af42-114">2つの状態の間の主な違いは、2つの値が2次元ではなく4次元であることです。</span><span class="sxs-lookup"><span data-stu-id="1af42-114">The main difference between one- and two-qubit states is that two-qubit states are four dimensional rather than two dimensional.</span></span>
<span data-ttu-id="1af42-115">これは、2つの状態の計算基準が、1つの "1 つの" 状態のすべての製品によって形成されているためです。</span><span class="sxs-lookup"><span data-stu-id="1af42-115">This is because the computational basis for two-qubit states is formed by the tensor products of one-qubit states.</span></span>  <span data-ttu-id="1af42-116">たとえば、次のように配置します。}</span><span class="sxs-lookup"><span data-stu-id="1af42-116">For example, we have \begin{align}</span></span>
<span data-ttu-id="1af42-117">00 \equiv \ begin{ bmatrix } 1 \\ \\ 0 & end{ bmatrix } \ otimes \ begin{ bmatrix } 1 \\ \\ 0 \ end{ bmatrix } &= \ begin{ bmatrix } 1 0 0 & \\ \\ \\\\ \\\\ end{ bmatrix } , \qquad 01 \equiv/begin{ bmatrix } 1 \\ \\ 0 & end{ bmatrix } /otimes & begin{} bmatrix 0 \\ \\ 1 \ end{ bmatrix } = \ begin{ bmatrix } 0 1 & end{ \\ \\ \\\\ \\\\ bmatrix } , \\ \\ 10 \equiv & begin{ bmatrix } 0 \\ \\ 1 & end{ bmatrix } \ otimes \ begin{ bmatrix } 1 \\ \\ 0 \ end{ bmatrix } &= \ begin{ bmatrix } 0 \\ \\ 0 \\\\ 1% \\\\ end{ bmatrix } , \qquad 11 \equiv/begin{ bmatrix } 0 \\ \\ 1 & end{} 0 0 bmatrix } bmatrix \\ \\ bmatrix } bmatrix \\ \\ \\\\ 0 0 \\\\ 1 \ end{ bmatrix } ですが、このようになります。</span><span class="sxs-lookup"><span data-stu-id="1af42-117">00 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} &= \begin{bmatrix}1 \\\\ 0\\\\ 0\\\\ 0 \end{bmatrix},\qquad 01 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \begin{bmatrix}0 \\\\ 1\\\\ 0\\\\ 0 \end{bmatrix},\\\\ 10 \equiv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} &= \begin{bmatrix}0 \\\\ 0\\\\ 1\\\\ 0 \end{bmatrix},\qquad 11 \equiv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \begin{bmatrix}0 \\\\ 0\\\\ 0\\\\ 1 \end{bmatrix}.</span></span>
<span data-ttu-id="1af42-118">& end{align}</span><span class="sxs-lookup"><span data-stu-id="1af42-118">\end{align}</span></span>

<span data-ttu-id="1af42-119">$ $ この構築を使用して、$n qubits のクォンタム状態がディメンション $ 2 ^ n の単位ベクトルで表されることがよくわかります。</span><span class="sxs-lookup"><span data-stu-id="1af42-119">It is easy to see that more generally the quantum state of $n$ qubits is represented by a unit vector of dimension $2^n$ using this construction.</span></span>  <span data-ttu-id="1af42-120">ベクター</span><span class="sxs-lookup"><span data-stu-id="1af42-120">The vector</span></span>

<span data-ttu-id="1af42-121">$ $ \ begin{ bmatrix } \ alpha_ {00 } \\ \\ \ alpha_ {01 } \\ \\ \ alpha_ {10 } \\ \\ \ alpha_ {11 \ } end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1af42-121">$$ \begin{bmatrix} \alpha_{00} \\\\  \alpha_{01} \\\\  \alpha_{10} \\\\  \alpha_{11} \end{bmatrix}</span></span>
$$

<span data-ttu-id="1af42-122">2つの qubits のクォンタム状態を表します ($ | \ alpha_ {00 } | ^ 2 + | \ alpha_ {01 } | ^ 2 + | \ alpha_ {10 | ^ 2 + | \ } alpha_ {11 } | ^ 2 = 1) $ 。</span><span class="sxs-lookup"><span data-stu-id="1af42-122">represents a quantum state on two qubits if $|\alpha_{00}|^2+|\alpha_{01}|^2+|\alpha_{10}|^2+|\alpha_{11}|^2=1$.</span></span> <span data-ttu-id="1af42-123">1つの qubits の場合と同様に、複数の qubits のクォンタム状態ベクトルには、システムの動作を説明するために必要なすべての情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="1af42-123">Just as with single qubits, the quantum state vector of multiple qubits holds all the information needed to describe the system's behavior.</span></span>

<span data-ttu-id="1af42-124">2つの独立した qubits が指定されている場合、1つは状態 $、begin{- bmatrix } alpha \ beta \ \\ \\ end{ bmatrix } $、2番目の qubits が state $ & begin{ bmatrix } \ gamma \\ \\ \ delta \ end{ bmatrix } $ となります。</span><span class="sxs-lookup"><span data-stu-id="1af42-124">If we are given two separate qubits, one in the state $\begin{bmatrix} \alpha \\\\  \beta \end{bmatrix}$ and a second qubit in the state  $\begin{bmatrix} \gamma \\\\  \delta \end{bmatrix}$, the corresponding two-qubit state is</span></span>

<span data-ttu-id="1af42-125">$ $ & begin{- bmatrix } α \\ \\ \ ベータ bmatrix } bmatrix } \\ \\ \ & # {-& #-& #}bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1af42-125">$$ \begin{bmatrix} \alpha \\\\  \beta \end{bmatrix} \otimes \begin{bmatrix} \gamma \\\\  \delta \end{bmatrix}</span></span> 
<span data-ttu-id="1af42-126">= \ begin{ bmatrix } \ alpha \ begin{\ bmatrix } gamma \\ \\ bmatrix } \\ \\ bmatrix } \\ \\ bmatrix } \-& # 0; & # {-ガンマ \ デルタ \ end{& end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1af42-126">=\begin{bmatrix} \alpha \begin{bmatrix} \gamma \\\\  \delta \end{bmatrix} \\\\ \beta \begin{bmatrix}\gamma \\\\  \delta \end{bmatrix} \end{bmatrix}</span></span>
<span data-ttu-id="1af42-127">= \ begin{- bmatrix } alpha \gamma \\ \\ \ α \ \delta \\ \\ ベータ \ ベータ \ & # \gamma \\ \\ \delta { bmatrix } , $ $</span><span class="sxs-lookup"><span data-stu-id="1af42-127">= \begin{bmatrix} \alpha\gamma \\\\  \alpha\delta \\\\  \beta\gamma \\\\  \beta\delta \end{bmatrix}, $$</span></span>

<span data-ttu-id="1af42-128">操作 $ otimes $ は、ベクターの Kronecker (または製品) と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="1af42-128">where the operation $\otimes$ is called the tensor product (or Kronecker product) of vectors.</span></span> <span data-ttu-id="1af42-129">2つの single qubit 状態の最新の状態を常に取得し、2つの1つの状態を形成することはできますが、2つの単一 qubit 状態のすべての状態を2つの1つの状態のままにして書き込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="1af42-129">Note that while we can always take the tensor product of two single-qubit states to form a two-qubit state, not all two-qubit quantum states can be written as the tensor product of two single-qubit states.</span></span>
<span data-ttu-id="1af42-130">たとえば、状態が $-psi = \ begin{-alpha- bmatrix } \\ \\ beta/end{ bmatrix } $ および $-phi/begin{-gamma {\ の場合、 = bmatrix } \\ \\ bmatrix } その状態は、状態であるため、</span><span class="sxs-lookup"><span data-stu-id="1af42-130">For example, there are no states $\psi=\begin{bmatrix} \alpha \\\\  \beta \end{bmatrix}$ and $\phi=\begin{bmatrix} \gamma \\\\  \delta \end{bmatrix}$ such that their tensor product is the state</span></span> 

<span data-ttu-id="1af42-131">$ $ \ psi \otimes \ phi = \ begin{ bmatrix } 1/\ sqrt {2 } \\ \\ 0 \\ \\ 0 \\ \\ 1/\ sqrt {2 } \ end{ bmatrix } . $ $</span><span class="sxs-lookup"><span data-stu-id="1af42-131">$$\psi\otimes \phi = \begin{bmatrix} 1/\sqrt{2} \\\\  0 \\\\  0 \\\\  1/\sqrt{2} \end{bmatrix}.$$</span></span> 

<span data-ttu-id="1af42-132">このような2つの qubit 状態は、シングル qubit 状態の管理されていない製品として記述することはできません。2つの qubits は、[*あり*](https://en.wikipedia.org/wiki/Quantum_entanglement)であると言います。</span><span class="sxs-lookup"><span data-stu-id="1af42-132">Such a two-qubit state, which cannot be written as the tensor product of single-qubit states, is called an "entangled state"; the two qubits are said to be [*entangled*](https://en.wikipedia.org/wiki/Quantum_entanglement).</span></span>  <span data-ttu-id="1af42-133">疎に言うと、クォンタムの状態は、1つの qubit 状態の状態を維持したものと考えることはできません。そのため、状態が保持する情報は、qubit のいずれかに限定されません。</span><span class="sxs-lookup"><span data-stu-id="1af42-133">Loosely speaking, because the quantum state cannot be thought of as a tensor product of single qubit states, the information that the state holds is not confined to either of the qubits individually.</span></span>  <span data-ttu-id="1af42-134">この情報は、2つの状態の間の相関関係でローカルではなく保存されます。</span><span class="sxs-lookup"><span data-stu-id="1af42-134">Rather, the information is stored non-locally in the correlations between the two states.</span></span>  <span data-ttu-id="1af42-135">このような非局所情報は、古典的なコンピューティングに対するクォンタムコンピューティングの主要な特徴の1つであり、クォンタムの電話と[クォンタムのエラー修正](xref:microsoft.quantum.libraries.error-correction)[を含むさまざま](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/teleportation)なクォンタムプロトコルに不可欠です。</span><span class="sxs-lookup"><span data-stu-id="1af42-135">This non-locality of information is one of the major distinguishing features of quantum computing over classical computing and is essential for a number of quantum protocols including [quantum teleportation](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/teleportation) and [quantum error correction](xref:microsoft.quantum.libraries.error-correction).</span></span>

## <a name="measuring-two-qubit-states"></a><span data-ttu-id="1af42-136">2つのビット状態の測定</span><span class="sxs-lookup"><span data-stu-id="1af42-136">Measuring Two-Qubit States</span></span> ##
<span data-ttu-id="1af42-137">2つのビット状態の測定は、単一の qubit 測定と非常によく似ています。</span><span class="sxs-lookup"><span data-stu-id="1af42-137">Measuring two-qubit states is very similar to single-qubit measurements.</span></span> <span data-ttu-id="1af42-138">状態の測定</span><span class="sxs-lookup"><span data-stu-id="1af42-138">Measuring the state</span></span>

<span data-ttu-id="1af42-139">$ $ \ begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1af42-139">$$ \begin{bmatrix}</span></span>
        <span data-ttu-id="1af42-140">\ alpha_ {00 } \\ \\ \ alpha_ {01 } \\ \\ \ alpha_ {10 } \\ \\ \ alpha_ {11}</span><span class="sxs-lookup"><span data-stu-id="1af42-140">\alpha_{00} \\\\ \alpha_{01} \\\\ \alpha_{10} \\\\ \alpha_{11}</span></span>
    <span data-ttu-id="1af42-141">エンドbmatrix}</span><span class="sxs-lookup"><span data-stu-id="1af42-141">\end{bmatrix}</span></span>
$$

<span data-ttu-id="1af42-142">確率が $ | \ $ alpha_ {00 | ^ 2、$1 が確率が $ | \ } $ $ alpha_ {01 | ^ 2、$10 が確率が $ } $ $ | \ alpha_ {10 } | ^ 2 $ 、$11 が $ 確率が $ | \ alpha_ {11 } | ^ 2 $ である $0 を使用して、を生成します。</span><span class="sxs-lookup"><span data-stu-id="1af42-142">yields $00$ with probability $|\alpha_{00}|^2$, $01$ with probability $|\alpha_{01}|^2$, $10$ with probability $|\alpha_{10}|^2$, and $11$ with probability $|\alpha_{11}|^2$.</span></span> <span data-ttu-id="1af42-143">変数 $ \ alpha_ {00 } , \ alpha_ {01 } , \ alpha_ {10 } , $ および $ \ alpha_ {11 $ は、 } この接続を明確にするために意図的に名前が付けられました。</span><span class="sxs-lookup"><span data-stu-id="1af42-143">The variables $\alpha_{00}, \alpha_{01}, \alpha_{10},$ and $\alpha_{11}$ were deliberately named to make this connection clear.</span></span> <span data-ttu-id="1af42-144">測定の後、結果が $0 の場合、 $ 2 つの qubit システムのクォンタムの状態が折りたたまれ、現在の状態になります。</span><span class="sxs-lookup"><span data-stu-id="1af42-144">After the measurement, if the outcome is $00$ then the quantum state of the two-qubit system has collapsed and is now</span></span>

<span data-ttu-id="1af42-145">$ $0 \equivbmatrix}</span><span class="sxs-lookup"><span data-stu-id="1af42-145">$$ 00 \equiv \begin{bmatrix}</span></span>
        <span data-ttu-id="1af42-146">1 0 0 0 \\ \\ \\ \\ \\ \\ \ end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="1af42-146">1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="1af42-147">2つの qubit クォンタム状態の1つの qubit だけを測定することもできます。</span><span class="sxs-lookup"><span data-stu-id="1af42-147">It is also possible to measure just one qubit of a two-qubit quantum state.</span></span> <span data-ttu-id="1af42-148">Qubits の1つだけを測定する場合、測定の影響はわずかに異なります。これは、状態全体が1つのサブシステムにのみ折りたたまれるのではなく、すべての状態が計算ベースの状態に折りたたまれないためです。</span><span class="sxs-lookup"><span data-stu-id="1af42-148">In cases where you measure only one of the qubits, the impact of measurement is subtly different because the entire state is not collapsed to a computational basis state, rather it is collapsed to only one sub-system.</span></span>  <span data-ttu-id="1af42-149">言い換えると、1つの qubit だけを測定すると、サブシステムの1つだけが折りたたまれますが、すべてが折りたたまれるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="1af42-149">In other words, in such cases measuring only one qubit only collapses one of the subsystems but not all of them.</span></span>  

<span data-ttu-id="1af42-150">これを確認するには、次の状態の最初の qubit を測定することを検討します。これは、最初に "0" 状態に設定された2つの qubit の Hadamard transform $H を適用することによって形成され $ ます。 $ $ H ^ {\ otimes 2 } \ left (\ begin{ bmatrix } 1 \\ \\ 0/end{/ bmatrix } otimes \ begin{ bmatrix } 1 \\ \\ 0 \ end{ bmatrix } \ right) = \frac{1 } {2 & } begin{ bmatrix } 1 & 1 & 1 & 1 \\ \\ 1 &-1 & 1 &-1 \\ \\ 1 & 1 &-1 &-1 \\ \\ 1 &-1 &-1 & 1 & end{/ bmatrix } begin{ bmatrix } 1 0 0 0 \\\\ \\\\ \\\\ \end { bmatrix } = \frac{1 } {2 & } begin{ bmatrix } 1 1 1 1 1 \\\\ \\\\ \\\\ \end { bmatrix } \ map\frac{1 } } = 0 & } {\ sqrt{2}/beginになります。 } { bmatrix } 1 \\\\ 1 \\\\ 0 0% \\\\ end{ bmatrix } \\ \\ \ \frac{1} = 1 & } {\ sqrt{2 } } \ begin{ bmatrix } 0 \\\\ 0 \\\\ 1 1 & \\\\ end{} bmatrix } \\ \\ ケース } 。</span><span class="sxs-lookup"><span data-stu-id="1af42-150">To see this consider measuring the first qubit of the following state, which is formed by applying the Hadamard transform $H$ on two qubits initially set to the "0" state: $$ H^{\otimes 2} \left( \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} \right) = \frac{1}{2}\begin{bmatrix}1 & 1 & 1 & 1 \\\\ 1 & -1 & 1 & -1 \\\\ 1 & 1 & -1 & -1 \\\\ 1 & -1 & -1 & 1 \end{bmatrix}\begin{bmatrix}1\\\\ 0\\\\ 0\\\\ 0\end{bmatrix} = \frac{1}{2}\begin{bmatrix}1\\\\ 1\\\\ 1\\\\ 1\end{bmatrix} \mapsto \begin{cases}\text{outcome }=0 & \frac{1}{\sqrt{2}}\begin{bmatrix}1\\\\ 1\\\\ 0\\\\ 0 \end{bmatrix}\\\\ \text{outcome }=1 & \frac{1}{\sqrt{2}}\begin{bmatrix}0\\\\ 0\\\\ 1\\\\ 1 \end{bmatrix}\\\\  \end{cases}.</span></span>
<span data-ttu-id="1af42-151">$ $ 両方の結果が50% の確率で発生しています。</span><span class="sxs-lookup"><span data-stu-id="1af42-151">$$ Both outcomes have 50% probability of occurring.</span></span>  <span data-ttu-id="1af42-152">2つの結果を50% の確率で intuited ことができます。これは、最初の量子状態ベクトルが、最初の qubit の $0 と $1 をスワップした状態で不変であるという事実です $ $ 。</span><span class="sxs-lookup"><span data-stu-id="1af42-152">The outcome being 50% probability for both can be intuited from the fact that the initial quantum state vector is invariant under swapping $0$ with $1$ on the first qubit.</span></span>

<span data-ttu-id="1af42-153">最初または2番目の qubit を測定するための数学的規則は単純です。</span><span class="sxs-lookup"><span data-stu-id="1af42-153">The mathematical rule for measuring the first or second qubit is simple.</span></span>  <span data-ttu-id="1af42-154">$E を $ $k ^ {\ rm th } $ 計算ベースのベクターに _k して、問題の $ $ qubit が $e の値に対して値 $1 を受け取るように、すべての _k $k のセットにすることを許可 $S し $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="1af42-154">If we let $e_k$ be the $k^{\rm th}$ computational basis vector and let $S$ be the set of all $e_k$ such that the qubit in question takes the value $1$ for that value of $k$.</span></span>  <span data-ttu-id="1af42-155">たとえば、最初の qubit の測定に関心がある場合、$S $ は $e _1 \equiv 10 $ および $e 3 11 で構成 \equiv さ $ れます。</span><span class="sxs-lookup"><span data-stu-id="1af42-155">For example, if we are interested in measuring the first qubit then $S$ would consist of $e_1\equiv 10$ and $e_3\equiv 11$.</span></span>  <span data-ttu-id="1af42-156">同様に、2番目の qubit $S に関心がある場合、 $ $e _2 \equiv 01 $ と $e 3 \equiv 11 で構成され $ ます。</span><span class="sxs-lookup"><span data-stu-id="1af42-156">Similarly, if we are interested in the second qubit $S$ would consist of $e_2\equiv 01$ and $e_3 \equiv 11$.</span></span>  <span data-ttu-id="1af42-157">その後、選択された qubit を $1 に測定する確率 $ は、state vector $ \ psi$</span><span class="sxs-lookup"><span data-stu-id="1af42-157">Then the probability of measuring the chosen qubit to be $1$ is for state vector $\psi$</span></span>

<span data-ttu-id="1af42-158">$ $ P (\ text{結果 } = 1) = \ sum_ {e_k \ { 、Set} S- } psi ^ \ ダガー e_k e_k ^ \ ダガー \psi.</span><span class="sxs-lookup"><span data-stu-id="1af42-158">$$ P(\text{outcome}=1)= \sum_{e_k \text{ in the set } S}\psi^\dagger e_k e_k^\dagger \psi.</span></span>
$$

> [!NOTE]
> <span data-ttu-id="1af42-159">このドキュメントでは、リトルエンディアン形式を使用して計算のラベルを付けています。</span><span class="sxs-lookup"><span data-stu-id="1af42-159">In this document we are using the little-endian format to label the computational basis.</span></span> <span data-ttu-id="1af42-160">リトルエンディアンフォーマットでは、最下位ビットが最初に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1af42-160">In little endian format, the least significant bits come first.</span></span> <span data-ttu-id="1af42-161">たとえば、リトルエンディアン形式の4番目の数値は、ビット001の文字列で表されます。</span><span class="sxs-lookup"><span data-stu-id="1af42-161">For example, the number four in little-endian format is represented by the string of bits 001.</span></span>

<span data-ttu-id="1af42-162">各 qubit 測定 $ では $0 または $1 のみが生成 $ されるため、$0 を測定する確率 $ は単に $1-P (\ text{結果 } = 1) $ となります。</span><span class="sxs-lookup"><span data-stu-id="1af42-162">Since each qubit measurement can only yield $0$ or $1$, the probability of measuring $0$ is simply $1-P(\text{outcome}=1)$.</span></span>  <span data-ttu-id="1af42-163">これは、$1 を測定する確率の式のみを明示的に指定するためです $ 。</span><span class="sxs-lookup"><span data-stu-id="1af42-163">This is why we only explicitly give a formula for the probability of measuring $1$.</span></span>

<span data-ttu-id="1af42-164">このような測定値が状態にあるアクションは、として数学的に表現できます。</span><span class="sxs-lookup"><span data-stu-id="1af42-164">The action that such a measurement has on the state can be expressed mathematically as</span></span>

<span data-ttu-id="1af42-165">$ $ \ psi \ mapo { \ sum_ {e_k \ { Set} S のテキスト } e_k e_k ^ \ ダガー \ psi } {\ sqrt{P (\ text{結果 } = 1)}}</span><span class="sxs-lookup"><span data-stu-id="1af42-165">$$ \psi \mapsto \frac{\sum_{e_k \text{ in the set } S} e_k e_k^\dagger \psi}{\sqrt{P(\text{outcome}=1)}}.</span></span>
$$

<span data-ttu-id="1af42-166">注意リーダーは、測定の確率がゼロの場合に何が起こるかについて心配することがあります。</span><span class="sxs-lookup"><span data-stu-id="1af42-166">The cautious reader may worry about what happens when the probability of the measurement is zero.</span></span>  <span data-ttu-id="1af42-167">この場合、結果の状態は技術的に未定義ですが、確率がゼロであるため、このような eventualities について心配する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1af42-167">While the resultant state is technically undefined in this case, we never need to worry about such eventualities because the probability is zero!</span></span>


<span data-ttu-id="1af42-168">$前に示した uniform state vector に $-psi を設定し、最初の qubit の測定に関心がある場合は、</span><span class="sxs-lookup"><span data-stu-id="1af42-168">If we take $\psi$ to be the uniform state vector given above and are interested in measuring the first qubit then</span></span> 

<span data-ttu-id="1af42-169">$ $ P (最初の qubit } = 1) = (\ psi ^-ダガー e_1) (e_1 ^-ダガー/psi) + (-psi e_3 e_3 ^-ダガー) = | e_1 ^-ダガー-psi | ^ 2 + | e_3 ^ \ ダガー/psi ^ 2 です (& t) | 。</span><span class="sxs-lookup"><span data-stu-id="1af42-169">$$ P(\text{measurement of first qubit}=1) = (\psi^\dagger e_1)(e_1^\dagger \psi)+(\psi^\dagger e_3)(e_3^\dagger \psi)=|e_1^\dagger \psi|^2+|e_3^\dagger \psi|^2.</span></span>
$$

<span data-ttu-id="1af42-170">これは、結果 $10 と $11 を測定するために期待される2つの確率の合計のみであることに注意 $ $ してください。</span><span class="sxs-lookup"><span data-stu-id="1af42-170">Note that this is just the sum of the two probabilities that would be expected for measuring the results $10$ and $11$ were all the qubits to be measured.</span></span>
<span data-ttu-id="1af42-171">この例では、次のように評価されます。</span><span class="sxs-lookup"><span data-stu-id="1af42-171">For our example, this evaluates to</span></span>

<span data-ttu-id="1af42-172">$ $ \frac{1 } {4 } \ 左 | \ begin{ bmatrix } 0&0&1&0 \end {\ bmatrix } begin{ bmatrix } 1 1 1 1 \\\\ \\\\ \\\\ \end { bmatrix } \ 右 | ^ 2 + \frac{1 } {4, } left | \ begin{ bmatrix } 0&0&0&1 \end {/ bmatrix } begin{ bmatrix } 1 1 1 1 \\\\ \\\\ \\\\ \end { bmatrix } \ 右 | ^ 2 = \frac{1 } {2 } .</span><span class="sxs-lookup"><span data-stu-id="1af42-172">$$ \frac{1}{4}\left|\begin{bmatrix}0&0&1&0\end{bmatrix}\begin{bmatrix}1\\\\ 1\\\\ 1\\\\ 1\end{bmatrix} \right|^2+\frac{1}{4}\left|\begin{bmatrix}0&0&0&1\end{bmatrix}\begin{bmatrix}1\\\\ 1\\\\ 1\\\\ 1\end{bmatrix} \right|^2=\frac{1}{2}.</span></span>
$$

<span data-ttu-id="1af42-173">これは、直感がどのような確率を示すかということに完全に一致します。</span><span class="sxs-lookup"><span data-stu-id="1af42-173">which perfectly matches what our intuition tells us the probability should be.</span></span>  <span data-ttu-id="1af42-174">同様に、状態はとして書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="1af42-174">Similarly, the state can be written as</span></span>

<span data-ttu-id="1af42-175">$ $ \ frac { \frac{e_1 } {2 } + \frac{e_3 { } 2 } } {\ sqrt { \frac{1 } {2 } }} = \frac{1 } {\ sqrt{2 } } \ begin{ bmatrix } 0 \\\\ 0 \\\\ 1 \\\\ 1 \end {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1af42-175">$$ \frac{\frac{e_1}{2}+\frac{e_3}{2}}{\sqrt{\frac{1}{2}}}=\frac{1}{\sqrt{2}}\begin{bmatrix} 0\\\\ 0\\\\ 1\\\\ 1\end{bmatrix}</span></span>
$$

<span data-ttu-id="1af42-176">ここでも、直感に従っています。</span><span class="sxs-lookup"><span data-stu-id="1af42-176">again in accordance with our intuition.</span></span>

## <a name="two-qubit-operations"></a><span data-ttu-id="1af42-177">2つの Qubit 操作</span><span class="sxs-lookup"><span data-stu-id="1af42-177">Two-Qubit Operations</span></span>
<span data-ttu-id="1af42-178">シングル qubit の場合と同様に、すべてのユニタリ変換は、qubit で有効な操作です。</span><span class="sxs-lookup"><span data-stu-id="1af42-178">As in the single-qubit case, any unitary transformation is a valid operation on qubits.</span></span> <span data-ttu-id="1af42-179">一般に、$n qubits でのユニタリ変換は、 $ サイズが $ $ 2 ^ n/times 2 ^ n (サイズが $ 2 ^ n) のマトリックス $U であり、 $ $ $U ^ {-1 } = U ^-ダガーのようになり $ ます。</span><span class="sxs-lookup"><span data-stu-id="1af42-179">In general, a unitary transformation on $n$ qubits is a matrix $U$ of size $2^n \times 2^n$ (so that it acts on vectors of size $2^n$), such that $U^{-1} = U^\dagger$.</span></span>
<span data-ttu-id="1af42-180">たとえば、CNOT (制御された) ゲートは、一般的に使用される2つの qubit ゲートであり、次のような種類の表で表されています。</span><span class="sxs-lookup"><span data-stu-id="1af42-180">For example, the CNOT (controlled-NOT) gate is a commonly used two-qubit gate and is represented by the following unitary matrix:</span></span>

<span data-ttu-id="1af42-181">$ $ \ オペレーター名 {cnot } = \ begin{1 \ 0 \ 0 \ 0 0 \ 1 \ 0 \ 0 0 \ 0 \ 0 \ 1 0 \ 0 \ bmatrix } \\ \\ 1 \ 0 & \\ \\ \\ \\ end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1af42-181">$$ \operatorname{CNOT} = \begin{bmatrix} 1\ 0\ 0\ 0  \\\\  0\ 1\ 0\ 0 \\\\  0\ 0\ 0\ 1 \\\\  0\ 0\ 1\ 0 \end{bmatrix}</span></span>
$$

<span data-ttu-id="1af42-182">両方の qubit にシングル qubit ゲートを適用して、2つの qubit ゲートを形成することもできます。</span><span class="sxs-lookup"><span data-stu-id="1af42-182">We can also form two-qubit gates by applying single-qubit gates on both qubits.</span></span> <span data-ttu-id="1af42-183">たとえば、ゲートを適用する場合は、</span><span class="sxs-lookup"><span data-stu-id="1af42-183">For example, if we apply the gates</span></span> 

<span data-ttu-id="1af42-184">$ $ \ begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1af42-184">$$ \begin{bmatrix}</span></span>
<span data-ttu-id="1af42-185">a \ b \\\\ c \ d \ end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1af42-185">a\ b\\\\ c\ d \end{bmatrix}</span></span>
$$

<span data-ttu-id="1af42-186">および</span><span class="sxs-lookup"><span data-stu-id="1af42-186">and</span></span>

<span data-ttu-id="1af42-187">$ $ \ begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1af42-187">$$\begin{bmatrix}</span></span>
<span data-ttu-id="1af42-188">e \ f \\\\ g \ h \ end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1af42-188">e\ f\\\\ g\ h \end{bmatrix}</span></span>
$$

<span data-ttu-id="1af42-189">1番目と2番目の qubits に対して、これは、次のようになります。 $ $ & begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1af42-189">to the first and second qubits, respectively, this is equivalent to applying the two-qubit unitary given by their tensor product: $$\begin{bmatrix}</span></span>
<span data-ttu-id="1af42-190">a \ b \\\\ c \ d \ end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1af42-190">a\ b\\\\ c\ d \end{bmatrix}</span></span>
<span data-ttu-id="1af42-191">\ otimes \ begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1af42-191">\otimes \begin{bmatrix}</span></span>
<span data-ttu-id="1af42-192">e \ f \\\\ g \ h \ end{ bmatrix } = \ begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1af42-192">e\ f\\\\ g\ h \end{bmatrix}= \begin{bmatrix}</span></span>
    <span data-ttu-id="1af42-193">ae \ af \ "\\ bf \\ \\ ag \ ah \ bg \" を \\ \\ \\ \\ bmatrix } "にして、" 2 "の2つのビットゲートを形成することができます。これは、既知のシングル qubit ゲートの最新機能を使用して、2つの qubit ゲートを形成できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="1af42-193">ae\ af\ be\ bf \\\\ ag\ ah\ bg\ bh \\\\ ce\ cf\ de\ df \\\\ cg\ ch\ dg\ dh \end{bmatrix}.$$ Thus we can form two-qubit gates by taking the tensor product of some known single-qubit gates.</span></span> <span data-ttu-id="1af42-194">2つの qubit ゲートの例としては、$H/otimes H $ 、$X/times $ /bold done、$X/Otimes Z などがあり $ ます。</span><span class="sxs-lookup"><span data-stu-id="1af42-194">Some examples of two-qubit gates include $H \otimes H$, $X \otimes \boldone$, and $X \otimes Z$.</span></span>

<span data-ttu-id="1af42-195">いずれの2つのシングル qubit ゲートでも2つのビットゲートが定義されていますが、その場合は、元の状態のままであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1af42-195">Note that while any two single-qubit gates define a two-qubit gate by taking their tensor product, the converse is not true.</span></span> <span data-ttu-id="1af42-196">すべての2つのビットゲートが、シングル qubit ゲートの全製品として書き込まれるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="1af42-196">Not all two-qubit gates can be written as the tensor product of single-qubit gates.</span></span>  <span data-ttu-id="1af42-197">このようなゲートは、 *entangling*ゲートと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="1af42-197">Such a gate is called an *entangling* gate.</span></span> <span data-ttu-id="1af42-198">Entangling ゲートの一例として、CNOT gate が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="1af42-198">One example of an entangling gate is the CNOT gate.</span></span>

<span data-ttu-id="1af42-199">制御されていないゲートの背後にある直感は、任意のゲートに汎用化できます。</span><span class="sxs-lookup"><span data-stu-id="1af42-199">The intuition behind a controlled-not gate can be generalized to arbitrary gates.</span></span>  <span data-ttu-id="1af42-200">一般に、制御されたゲートは、特定の qubit が $1 の場合を除き、id として機能するゲートです (ie にはアクションがありません) $ 。</span><span class="sxs-lookup"><span data-stu-id="1af42-200">A controlled gate in general is a gate that acts as identity (ie it has no action) unless a specific qubit is $1$.</span></span>  <span data-ttu-id="1af42-201">ここでは、制御されたユニタリを示します。この例では、$x ラベルが付けられた qubit で制御さ $ れ、$-ラムダ \_ x (U) $ を使用します。</span><span class="sxs-lookup"><span data-stu-id="1af42-201">We denote a controlled unitary, controlled in this case on the qubit labeled $x$, with a $\Lambda\_x(U)$.</span></span>  <span data-ttu-id="1af42-202">例として、$ \ Lambda_0 (U) e {1/otimes \_ } {-psi } = e \_ {1 } /otimes U { } /psi $ and $-ラムダ \_ 0 (u) e {0/otimes \_ } { } /psi = e \_ {0 } /otimes { } /psi $, ここで $e \_ 0 $ と $e \_ 1 は、 $ 値 $0 と $1 に対応する1つの qubit の計算ベースのベクトルです $ $ 。</span><span class="sxs-lookup"><span data-stu-id="1af42-202">As an example $\Lambda_0(U) e\_{1}\otimes {\psi}=e\_{1}\otimes U{\psi}$ and $\Lambda\_0(U) e\_{0}\otimes {\psi}=e\_{0}\otimes{\psi}$, where $e\_0$ and $e\_1$ are the computational basis vectors for a single qubit corresponding to the values $0$ and $1$.</span></span>  <span data-ttu-id="1af42-203">たとえば、次のようになります。次の制御された $Z ゲートについて考えてみましょう $ 。 $ $ \ ラムダ \_ 0 (Z) = \ begin{ bmatrix } 1&0&0&0 0&1&0&0 0&0 \\ \\ \\ \\&1&0 \\ \\ 0&0&0 & -1、end{ bmatrix } = (-bold \otimes } \otimes done h)。</span><span class="sxs-lookup"><span data-stu-id="1af42-203">For example, consider the following controlled-$Z$ gate then we can express this as $$ \Lambda\_0(Z)= \begin{bmatrix}1&0&0&0\\\\0&1&0&0\\\\0&0&1&0\\\\0&0&0&-1 \end{bmatrix}=(\boldone\otimes H)\operatorname{CNOT}(\boldone\otimes H).</span></span>
$$

<span data-ttu-id="1af42-204">制御された unitaries 効率的な方法で構築することは、大きな課題です。</span><span class="sxs-lookup"><span data-stu-id="1af42-204">Building controlled unitaries in an efficient manner is a major challenge.</span></span>  <span data-ttu-id="1af42-205">これを実装する最も簡単な方法は、基本的なゲートの制御されたバージョンのデータベースを形成し、元のすべての位置合わせ操作のすべての基本ゲートを、制御される対応するに置き換えることです。</span><span class="sxs-lookup"><span data-stu-id="1af42-205">The simplest way to implement this requires forming a database of controlled versions of fundamental gates and replacing every fundamental gate in the original unitary operation with its controlled counterpart.</span></span>  <span data-ttu-id="1af42-206">多くの場合、これはかなり無駄であり、巧妙な洞察を使用して、いくつかのゲートを制御されたバージョンに置き換えるだけで、同じ影響を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="1af42-206">This is often quite wasteful and clever insight often can be used to just replace a few gates with controlled versions to achieve the same impact.</span></span>  <span data-ttu-id="1af42-207">このため、最適化された手作業でチューニングされたバージョンがわかっている場合は、ユーザーが制御されたバージョンのユニタリを定義できるようにするための、単純な方法をフレームワークに提供します。</span><span class="sxs-lookup"><span data-stu-id="1af42-207">For this reason, we provide in our framework the ability to perform either the naive method of controlling or allow the user to define a controlled version of the unitary if an optimized hand-tuned version is known.</span></span>

<span data-ttu-id="1af42-208">また、典型的情報を使用してゲートを制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="1af42-208">Gates can also be controlled using classical information.</span></span>  <span data-ttu-id="1af42-209">たとえば、クラシックデプロイで制御されないゲートゲートは、単なる通常のゲートではありませんが、古典ビットが量子ビットではなく $1 である場合にのみ適用され $ ます。</span><span class="sxs-lookup"><span data-stu-id="1af42-209">A classically controlled not-gate, for example, is just an ordinary not-gate but it is only applied if a classical bit is $1$ as opposed to a quantum bit.</span></span>  <span data-ttu-id="1af42-210">この意味では、クラシックデプロイ制御ゲートは、コードの1つの分岐でのみゲートが適用されるように、クォンタムコード内の if ステートメントと考えることができます。</span><span class="sxs-lookup"><span data-stu-id="1af42-210">In this sense, a classically controlled gate can be thought of as an if statement in the quantum code wherein the gate is applied only in one branch of the code.</span></span>


<span data-ttu-id="1af42-211">シングル qubit の場合と同様に、2つの qubit ゲートセットは、 \times $ このセットから任意の有効桁数になるゲートの製品によって、$4 4 つのすべてのインの行列を近似する場合にユニバーサルになります。</span><span class="sxs-lookup"><span data-stu-id="1af42-211">As in the single-qubit case, a two-qubit gate set is universal if any $4\times 4$ unitary matrix can be approximated by a product of gates from this set to arbitrary precision.</span></span>
<span data-ttu-id="1af42-212">ユニバーサルゲートセットの一例として、Hadamard ゲート、T ゲート、CNOT gate があります。</span><span class="sxs-lookup"><span data-stu-id="1af42-212">One example of a universal gate set is the Hadamard gate, the T gate, and the CNOT gate.</span></span> <span data-ttu-id="1af42-213">これらのゲートの製品を作成することによって、2つの qubits 上のすべてのユニタリ行列を概算することができます。</span><span class="sxs-lookup"><span data-stu-id="1af42-213">By taking products of these gates, we can approximate any unitary matrix on two qubits.</span></span>

## <a name="many-qubit-systems"></a><span data-ttu-id="1af42-214">多対ビットシステム</span><span class="sxs-lookup"><span data-stu-id="1af42-214">Many-Qubit Systems</span></span>
<span data-ttu-id="1af42-215">ここでは、2つのビットケースで調査したのとまったく同じパターンに従って、小規模なシステムから多数の qubit クォンタムの状態を構築します。</span><span class="sxs-lookup"><span data-stu-id="1af42-215">We follow exactly the same patterns explored in the two-qubit case to build many-qubit quantum states from smaller systems.</span></span>  <span data-ttu-id="1af42-216">このような状態は、より小さい状態の製品を作成することによって構築されます。</span><span class="sxs-lookup"><span data-stu-id="1af42-216">Such states are built by forming tensor products of smaller states.</span></span>  <span data-ttu-id="1af42-217">たとえば、クォンタムコンピューターにビット文字列 $1011001 をエンコードすることを検討してください $ 。</span><span class="sxs-lookup"><span data-stu-id="1af42-217">For example, consider encoding the bit string $1011001$ in a quantum computer.</span></span>  <span data-ttu-id="1af42-218">これを次のようにエンコードできます。</span><span class="sxs-lookup"><span data-stu-id="1af42-218">We can encode this as</span></span>

<span data-ttu-id="1af42-219">$ $1011001 \equiv \ begin{ bmatrix } 0 \\ \\ 1 & end{\ bmatrix } otimes \ begin{ bmatrix } 1 & \\ \\ bmatrix } bmatrix } \\ \\ bmatrix } bmatrix } \\ \\ bmatrix } bmatrix } \\ \\ bmatrix } bmatrix } \\ \\ bmatrix } bmatrix } \\ \\ bmatrix } end{{/otimes \ begin{0 1 & end{/otimes \ begin{0 1 & end{/otimes \ begin{1 0 & end{/otimes & begin{0 1 & end{..</span><span class="sxs-lookup"><span data-stu-id="1af42-219">$$ 1011001 \equiv \begin{bmatrix} 0 \\\\  1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\  0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\  1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\  1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\  0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\  0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\  1 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="1af42-220">クォンタムゲートは、まったく同じ方法で動作します。</span><span class="sxs-lookup"><span data-stu-id="1af42-220">Quantum gates work in exactly the same way.</span></span>  <span data-ttu-id="1af42-221">たとえば、 $ 最初の qubit に $X ゲートを適用し、2番目と3番目の qubit の間で CNOT を実行する場合は、この変換を次のように表現することができます。</span><span class="sxs-lookup"><span data-stu-id="1af42-221">For example, if we wish to apply the $X$ gate to the first qubit and then perform a CNOT between the second and third qubits we may express this transformation as</span></span>

<span data-ttu-id="1af42-222">& i)}</span><span class="sxs-lookup"><span data-stu-id="1af42-222">\begin{align}</span></span>
<span data-ttu-id="1af42-223">& (X/otimes \operatorname{CNOT}_{12] \ (& o) \ (& o) \ (& o) \ ole times \ (& o) \ @ times \ (& o) \ begin{1 & end{/otimes \ begin{1 0 \ end{/otimes \ begin{ } \otimes bmatrix } \\ \\ bmatrix } bmatrix } \\ \\ bmatrix } bmatrix } 0 \\ \\ 1 & end{/otimes-begin{1 bmatrix \qquad; } bmatrix } \\ \\ bmatrix } bmatrix } \\ \\ bmatrix } bmatrix } \\ \\ bmatrix } bmatrix } \\ \\ bmatrix } \\ \\ \qquad \equiv & end{/otimes & begin{1 0 \ end{/otimes & begin{0 1 \ end{& 0011001. (otimes)。</span><span class="sxs-lookup"><span data-stu-id="1af42-223">&(X \otimes \operatorname{CNOT}_{12}\otimes \boldone\otimes \boldone \otimes \boldone \otimes \boldone) \begin{bmatrix} 0 \\\\  1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\  0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\  1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\  1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\  0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\  0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\  1 \end{bmatrix}\\\\ &\qquad\qquad\equiv 0011001.</span></span>
<span data-ttu-id="1af42-224">& end{align}</span><span class="sxs-lookup"><span data-stu-id="1af42-224">\end{align}</span></span>

<span data-ttu-id="1af42-225">多くの qubit システムでは、多くの場合、クォンタムコンピューターの一時的なメモリとして機能する qubit を割り当てたり、割り当てを解除したりする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1af42-225">In many qubit systems, there is often a need to allocate and deallocate qubits that serve as temporary memory for the quantum computer.</span></span>  <span data-ttu-id="1af42-226">このような qubit は ancilla と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="1af42-226">Such a qubit is called an ancilla.</span></span>  <span data-ttu-id="1af42-227">既定では、割り当て時に qubit 状態が 0 $e に初期化されるとし $ ます。</span><span class="sxs-lookup"><span data-stu-id="1af42-227">By default we assume the qubit state is initialized to $e_0$ upon allocation.</span></span>  <span data-ttu-id="1af42-228">また、解放の前に0を $e するために再び返されると想定 $ しています。</span><span class="sxs-lookup"><span data-stu-id="1af42-228">We further assume that it is returned again to $e_0$ before deallocation.</span></span>  <span data-ttu-id="1af42-229">この想定は重要です。そのため、ancilla qubit が割り当て解除されたときに別の qubit レジスタを使用すると、割り当て解除のプロセスによって ancilla が破損する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1af42-229">This assumption is important because if an ancilla qubit becomes entangled with another qubit register when it becomes deallocated then the process of deallocation will damage the ancilla.</span></span>  <span data-ttu-id="1af42-230">このため、このような qubits は解放される前に初期状態に戻されると常に想定されています。</span><span class="sxs-lookup"><span data-stu-id="1af42-230">For this reason, we always assume that such qubits are reverted to their initial state before being released.</span></span>

<span data-ttu-id="1af42-231">最後に、2つの qubit クォンタムコンピューターに対してユニバーサルクォンタムコンピューティングを実現するために、ゲートセットに新しいゲートを追加する必要がありましたが、マルチ qubit ケースでは新しいゲートを導入する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1af42-231">Finally, although new gates needed to be added to our gate set to achieve universal quantum computing for two qubit quantum computers, no new gates need to be introduced in the multi-qubit case.</span></span>  <span data-ttu-id="1af42-232">ゲート $H $ 、$T、 $ および cnot は、多数の qubits に対して設定されたユニバーサルゲートを形成しません。これは、一般的なすべてのデータ長変換を、一連の2つの qubits 回転に分割できるためです。</span><span class="sxs-lookup"><span data-stu-id="1af42-232">The gates $H$, $T$ and CNOT form a universal gate set on many qubits because any general unitary transformation can be broken into a series of two qubit rotations.</span></span>  <span data-ttu-id="1af42-233">次に、2つのビットケースに対して開発された理論を活用し、多くの qubit があるときに、ここでもう一度使用します。</span><span class="sxs-lookup"><span data-stu-id="1af42-233">We then can leverage the theory developed for the two-qubit case and use it again here when we have many qubits.</span></span>

<span data-ttu-id="1af42-234">これまでに使用してきた線形代数表記は、マルチ qubit の状態を示すために使用されていますが、状態のサイズを大きくするにつれて煩雑になる傾向があります。</span><span class="sxs-lookup"><span data-stu-id="1af42-234">While the linear algebraic notation that we have been using thus far can certainly be used to describe multi-qubit states, it becomes increasingly cumbersome as we increase the size of the states.</span></span>  <span data-ttu-id="1af42-235">たとえば、長さ7ビット文字列の結果として得られる列ベクトルは $128 $ 次元で、前に説明した表記法を使用して表現されます。</span><span class="sxs-lookup"><span data-stu-id="1af42-235">The resulting column-vector for a length 7 bit string, for example, is $128$ dimensional, which makes expressing it using the notation described previously very cumbersome.</span></span>  <span data-ttu-id="1af42-236">このため、次に、このような高次元ベクターを簡潔に記述できるように、クォンタムコンピューティングに共通の表記を示しています。</span><span class="sxs-lookup"><span data-stu-id="1af42-236">For this reason, we next present a common notation in quantum computing that allows us to concisely describe these high-dimensional vectors.</span></span>
