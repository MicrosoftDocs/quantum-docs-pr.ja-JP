---
title: クォンタム回線 |Microsoft Docs
description: 量子回路
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: fe845aa0dde7c780ea6721dfe2559119e90b4aa5
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820795"
---
# <a name="quantum-circuits"></a><span data-ttu-id="183c8-103">クォンタム回線</span><span class="sxs-lookup"><span data-stu-id="183c8-103">Quantum Circuits</span></span>
<span data-ttu-id="183c8-104">ここでは、ユニタリ変換 $ \ text{CNOT} _{01}(hotimes 1) $ について考えてみます。</span><span class="sxs-lookup"><span data-stu-id="183c8-104">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="183c8-105">このゲートシーケンスは、下回っありの2つのビット状態を作成するので、クォンタムコンピューティングにとって基本的な意味を持ちます。</span><span class="sxs-lookup"><span data-stu-id="183c8-105">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="183c8-106">$ $ \mathrm{CNOT}_{01}(hotimes 1) \ket{00} = \ frac{1}{\ sqrt{2}} \ left (\ket{00} + \ket{11} 右)、$ $</span><span class="sxs-lookup"><span data-stu-id="183c8-106">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="183c8-107">このような複雑さを持つ操作は、クォンタムアルゴリズムとクォンタムエラー修正で広く普及しています。そのため、*量子回線図*と呼ばれるシンプルな方法で視覚化を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="183c8-107">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram*.</span></span>
<span data-ttu-id="183c8-108">この下回っありのクォンタム状態を準備するためのサーキット図は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="183c8-108">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/Concepts1.png)

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="183c8-109">クォンタム回路図の表記規則</span><span class="sxs-lookup"><span data-stu-id="183c8-109">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="183c8-110">このクォンタム操作のビジュアル言語は、クォンタム回線を表現するための規則を理解した後に、同等のマトリックスを書き出すよりも簡単に消化できます。</span><span class="sxs-lookup"><span data-stu-id="183c8-110">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="183c8-111">以下の規則を確認します。</span><span class="sxs-lookup"><span data-stu-id="183c8-111">We review these conventions below.</span></span>

<span data-ttu-id="183c8-112">回路図では、各実線は qubit レジスタを表しています。</span><span class="sxs-lookup"><span data-stu-id="183c8-112">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="183c8-113">慣例として、一番上の行は qubit レジスタ $0 $ で、残りは順番にラベル付けされます。</span><span class="sxs-lookup"><span data-stu-id="183c8-113">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="183c8-114">上の例の回線は、2つの qubits (または1つの qubits で構成される2つのレジスタ) で動作しているように表されています。</span><span class="sxs-lookup"><span data-stu-id="183c8-114">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="183c8-115">1つ以上の qubit レジスタに作用するゲートは、ボックスとして示されます。</span><span class="sxs-lookup"><span data-stu-id="183c8-115">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="183c8-116">たとえば、シンボルは</span><span class="sxs-lookup"><span data-stu-id="183c8-116">For example, the symbol</span></span>

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_2.png)

<span data-ttu-id="183c8-117">[Hadamard](xref:microsoft.quantum.intrinsic.h)ゲートは、シングル qubit レジスタに対して動作します。</span><span class="sxs-lookup"><span data-stu-id="183c8-117">is the [Hadamard](xref:microsoft.quantum.intrinsic.h) gate acting on a single-qubit register.</span></span>

<span data-ttu-id="183c8-118">クォンタムゲートは、ゲートが最初に qubits に適用されたときの左端のゲートと共に、時系列順に並べられます。</span><span class="sxs-lookup"><span data-stu-id="183c8-118">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="183c8-119">つまり、回線をクォンタム状態のままにしている場合、ワイヤは図の各ゲートを通じて、左から右にクォンタムの状態を取り込みます。</span><span class="sxs-lookup"><span data-stu-id="183c8-119">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="183c8-120">つまり、</span><span class="sxs-lookup"><span data-stu-id="183c8-120">That is to say</span></span> 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_3.png)

<span data-ttu-id="183c8-121">は、$CBA が $ であることを示します。</span><span class="sxs-lookup"><span data-stu-id="183c8-121">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="183c8-122">行列乗算は反対の規則に従います。最初に右端の行列が適用されます。</span><span class="sxs-lookup"><span data-stu-id="183c8-122">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="183c8-123">ただし、量子回線図では、最初に一番左のゲートが適用されます。</span><span class="sxs-lookup"><span data-stu-id="183c8-123">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="183c8-124">この違いによって混乱が生じる可能性があるため、線形代数の図と量子回線の図の大きな違いに注意することが重要です。</span><span class="sxs-lookup"><span data-stu-id="183c8-124">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="183c8-125">クォンタム回線の入力と出力</span><span class="sxs-lookup"><span data-stu-id="183c8-125">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="183c8-126">前に示したすべての例では、クォンタムゲートから送信されたワイヤの数とまったく同じ数 (qubits) の入力がクォンタムゲートに含まれていました。</span><span class="sxs-lookup"><span data-stu-id="183c8-126">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="183c8-127">最初は、クォンタム回線が一般に入力よりも多くの出力を持つことができると考えられるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="183c8-127">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="183c8-128">ただし、これは不可能です。これは、すべてのクォンタム操作、測定値の保存は、すべての処理が行われるためです。</span><span class="sxs-lookup"><span data-stu-id="183c8-128">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="183c8-129">同じ数の出力が入力として含まれていなかった場合は、元に戻すことはできず、そのため、不一致になります。</span><span class="sxs-lookup"><span data-stu-id="183c8-129">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="183c8-130">このため、サーキット図に描画されるすべてのボックスには、それを終了するときとまったく同じ数のワイヤを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="183c8-130">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="183c8-131">マルチ qubit 回路図は、単 qubit と同様の規則に従います。</span><span class="sxs-lookup"><span data-stu-id="183c8-131">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="183c8-132">明確な例として、$ を $ (H & otimes X) $ に $B、2つの qubit のを定義し、次のように回線を表現することができます。</span><span class="sxs-lookup"><span data-stu-id="183c8-132">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_4.png)

<span data-ttu-id="183c8-133">また、回線が使用されているコンテキストに応じて、2 1-qubit レジスタではなく、1つの2つの2つのビットレジスタに対するアクションを持つ $B $ を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="183c8-133">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="183c8-134">このような抽象回路図の中で最も役に立つのは、複雑なクォンタムアルゴリズムを高いレベルで記述し、基本ゲートにコンパイルする必要がない場合などです。</span><span class="sxs-lookup"><span data-stu-id="183c8-134">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="183c8-135">これは、アルゴリズム内の各サブルーチンがどのように機能するかについてすべての詳細を理解しなくても、大規模なクォンタムアルゴリズムのデータフローに関する直感を取得できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="183c8-135">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="183c8-136">制御ゲート</span><span class="sxs-lookup"><span data-stu-id="183c8-136">Controlled gates</span></span>
<span data-ttu-id="183c8-137">マルチ qubit クォンタム回路図に組み込まれているもう1つのコンストラクトは制御です。</span><span class="sxs-lookup"><span data-stu-id="183c8-137">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="183c8-138">クォンタム片制御ゲートのアクション。 $-ラムダ (G) $ が指定されています。ここでは、1つの qubit の値が $G $ のアプリケーションを制御しています。この例では、製品状態入力 $-ラムダ (G) (\ alpha \ket{0} +/ベータ{1}) \ket{\psi} = \ alpha \ket{0} \ket{\psi} + \ beta \ket{1} G\ket {\ psi}</span><span class="sxs-lookup"><span data-stu-id="183c8-138">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$.</span></span>
<span data-ttu-id="183c8-139">つまり、制御されたゲートが $ \ psi $ を含むレジスタに $ $G を適用するのは、コントロールの qubit が値 $1 $ を受け取る場合のみです。</span><span class="sxs-lookup"><span data-stu-id="183c8-139">That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="183c8-140">一般に、このような制御された操作を回路図に記述します。</span><span class="sxs-lookup"><span data-stu-id="183c8-140">In general, we describe such controlled operations in circuit diagrams as</span></span>

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_5.png)

<span data-ttu-id="183c8-141">ここで、黒い円はゲートが制御されているクォンタムビットを表し、垂直方向のワイヤは、コントロール qubit が値 $1 $ を受け取るときに適用されるユニタリを表します。</span><span class="sxs-lookup"><span data-stu-id="183c8-141">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="183c8-142">$G = X $ および $G = Z $ の特殊なケースでは、ゲートの制御されたバージョンを記述するために次の表記が導入されます (制御された X ゲートは[$CNOT $ gate](xref:microsoft.quantum.intrinsic.cnot)であることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="183c8-142">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:microsoft.quantum.intrinsic.cnot)):</span></span>

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_6.png)

<span data-ttu-id="183c8-143">Q # は、操作の制御されたバージョンを自動的に生成するメソッドを提供します。これにより、プログラマは、これらの操作を手作業でコードに渡す必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="183c8-143">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="183c8-144">この例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="183c8-144">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="183c8-145">測定演算子</span><span class="sxs-lookup"><span data-stu-id="183c8-145">Measurement operator</span></span>
<span data-ttu-id="183c8-146">回路図で視覚化する残りの操作は、測定値です。</span><span class="sxs-lookup"><span data-stu-id="183c8-146">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="183c8-147">測定は、qubit レジスタを受け取り、それを測定し、その結果を古典的な情報として出力します。</span><span class="sxs-lookup"><span data-stu-id="183c8-147">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="183c8-148">測定値はメーター記号で示され、常に入力として qubit レジスタ (実線で示されます) を受け取り、古典的な情報を出力します (2 本の線で示されます)。</span><span class="sxs-lookup"><span data-stu-id="183c8-148">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="183c8-149">具体的には、このようなサブサーキットは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="183c8-149">Specifically, such a subcircuit looks like:</span></span>

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="183c8-150">![測定回路](~/media/concepts_7.png)</span><span class="sxs-lookup"><span data-stu-id="183c8-150">![Measurement circuit](~/media/concepts_7.png)</span></span>

<span data-ttu-id="183c8-151">Q # この目的のために[メジャー演算子](xref:microsoft.quantum.intrinsic.measure)を実装します。</span><span class="sxs-lookup"><span data-stu-id="183c8-151">Q# implements a [Measure operator](xref:microsoft.quantum.intrinsic.measure) for this purpose.</span></span>
<span data-ttu-id="183c8-152">詳細については、[測定に関するセクション](xref:microsoft.quantum.libraries.standard.prelude#measurements)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="183c8-152">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="183c8-153">同様に、サブサーキット</span><span class="sxs-lookup"><span data-stu-id="183c8-153">Similarly, the subcircuit</span></span>

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_8.png)

<span data-ttu-id="183c8-154">クラシックデプロイ制御ゲートを提供します。 $G $ は、$1 $ という従来の制御ビットで条件付きで適用されます。</span><span class="sxs-lookup"><span data-stu-id="183c8-154">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="183c8-155">受付回路の図</span><span class="sxs-lookup"><span data-stu-id="183c8-155">Teleportation circuit diagram</span></span>
<span data-ttu-id="183c8-156">[クォンタム](xref:microsoft.quantum.techniques.puttingittogether)は、これらのコンポーネントを示す最良のクォンタムアルゴリズムであると考えられます。</span><span class="sxs-lookup"><span data-stu-id="183c8-156">[Quantum teleportation](xref:microsoft.quantum.techniques.puttingittogether) is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="183c8-157">クォンタムコンピューター内 (または、quantum ネットワーク内の離れたコンピューター間でも) データを移動する方法としては、結び付き使用と測定を使用します。</span><span class="sxs-lookup"><span data-stu-id="183c8-157">Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="183c8-158">興味深いことに、実際には、qubit の値が何であるかを把握していなくても、特定の qubit の値を1つの qubit から別の値に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="183c8-158">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="183c8-159">これは、プロトコルが量子力学法に従って動作するために必要です。</span><span class="sxs-lookup"><span data-stu-id="183c8-159">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="183c8-160">次に、クォンタムの例を示します。また、クォンタム回線の読み取り方法を示すために、回路の注釈付きバージョンも提供します。</span><span class="sxs-lookup"><span data-stu-id="183c8-160">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<!--- ![](.\media\tp2.svg){ width=50% } --->
![](~/media/concepts_tp2.png)
