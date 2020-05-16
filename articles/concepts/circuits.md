---
title: 量子回路
description: クォンタム回路図を使用して単純で複雑なクォンタム操作を視覚的に表現する方法について説明します。
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 43f14d67db76dabda34bf881ccbfae0bfd1784ff
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426623"
---
# <a name="quantum-circuits"></a><span data-ttu-id="d4f32-103">クォンタム回線</span><span class="sxs-lookup"><span data-stu-id="d4f32-103">Quantum Circuits</span></span>
<span data-ttu-id="d4f32-104">ここでは、ユニタリ変換 $ \ text{CNOT} _ {01} (hotimes 1) $ という点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="d4f32-104">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="d4f32-105">このゲートシーケンスは、下回っありの2つのビット状態を作成するので、クォンタムコンピューティングにとって基本的な意味を持ちます。</span><span class="sxs-lookup"><span data-stu-id="d4f32-105">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="d4f32-106">$ $ \mathrm{CNOT}_ {01} (H-otimes 1) \ket {00} = \ frac {1} {\ sqrt {2} } \ left (\ket {00} + \ket {11} ), $ $</span><span class="sxs-lookup"><span data-stu-id="d4f32-106">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="d4f32-107">このような複雑さを持つ操作は、クォンタムアルゴリズムとクォンタムエラー修正で広く普及しています。そのため、*量子回線図*と呼ばれるシンプルな方法で視覚化を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d4f32-107">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram*.</span></span>
<span data-ttu-id="d4f32-108">この下回っありのクォンタム状態を準備するためのサーキット図は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d4f32-108">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="d4f32-109">![下回っありの2つの状態のサーキット図](~/media/1.svg)</span><span class="sxs-lookup"><span data-stu-id="d4f32-109">![Circuit diagram for a maximally entangled two-qubit state](~/media/1.svg)</span></span>

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="d4f32-110">クォンタム回路図の表記規則</span><span class="sxs-lookup"><span data-stu-id="d4f32-110">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="d4f32-111">このクォンタム操作のビジュアル言語は、クォンタム回線を表現するための規則を理解した後に、同等のマトリックスを書き出すよりも簡単に消化できます。</span><span class="sxs-lookup"><span data-stu-id="d4f32-111">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="d4f32-112">以下の規則を確認します。</span><span class="sxs-lookup"><span data-stu-id="d4f32-112">We review these conventions below.</span></span>

<span data-ttu-id="d4f32-113">回路図では、各実線は qubit レジスタを表しています。</span><span class="sxs-lookup"><span data-stu-id="d4f32-113">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="d4f32-114">慣例として、一番上の行は qubit レジスタ $0 $ で、残りは順番にラベル付けされます。</span><span class="sxs-lookup"><span data-stu-id="d4f32-114">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="d4f32-115">上の例の回線は、2つの qubits (または1つの qubits で構成される2つのレジスタ) で動作しているように表されています。</span><span class="sxs-lookup"><span data-stu-id="d4f32-115">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="d4f32-116">1つ以上の qubit レジスタに作用するゲートは、ボックスとして示されます。</span><span class="sxs-lookup"><span data-stu-id="d4f32-116">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="d4f32-117">たとえば、シンボルは</span><span class="sxs-lookup"><span data-stu-id="d4f32-117">For example, the symbol</span></span>

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="d4f32-118">![シングル qubit レジスタで動作する Hadamard 操作のシンボル](~/media/2.svg)</span><span class="sxs-lookup"><span data-stu-id="d4f32-118">![Symbol for a Hadamard operation acting on a single-qubit register](~/media/2.svg)</span></span>

<span data-ttu-id="d4f32-119">は、シングル qubit レジスタに対して動作する[Hadamard](xref:microsoft.quantum.intrinsic.h)操作です。</span><span class="sxs-lookup"><span data-stu-id="d4f32-119">is a [Hadamard](xref:microsoft.quantum.intrinsic.h) operation acting on a single-qubit register.</span></span>

<span data-ttu-id="d4f32-120">クォンタムゲートは、ゲートが最初に qubits に適用されたときの左端のゲートと共に、時系列順に並べられます。</span><span class="sxs-lookup"><span data-stu-id="d4f32-120">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="d4f32-121">つまり、回線をクォンタム状態のままにしている場合、ワイヤは図の各ゲートを通じて、左から右にクォンタムの状態を取り込みます。</span><span class="sxs-lookup"><span data-stu-id="d4f32-121">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="d4f32-122">つまり、</span><span class="sxs-lookup"><span data-stu-id="d4f32-122">That is to say</span></span> 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="d4f32-123">![左から右に適用されているクォンタムゲートの図](~/media/3.svg)</span><span class="sxs-lookup"><span data-stu-id="d4f32-123">![Diagram of quantum gates being applied left-to-right](~/media/3.svg)</span></span>

<span data-ttu-id="d4f32-124">は、$CBA が $ であることを示します。</span><span class="sxs-lookup"><span data-stu-id="d4f32-124">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="d4f32-125">行列乗算は反対の規則に従います。最初に右端の行列が適用されます。</span><span class="sxs-lookup"><span data-stu-id="d4f32-125">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="d4f32-126">ただし、量子回線図では、最初に一番左のゲートが適用されます。</span><span class="sxs-lookup"><span data-stu-id="d4f32-126">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="d4f32-127">この違いによって混乱が生じる可能性があるため、線形代数の図と量子回線の図の大きな違いに注意することが重要です。</span><span class="sxs-lookup"><span data-stu-id="d4f32-127">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="d4f32-128">クォンタム回線の入力と出力</span><span class="sxs-lookup"><span data-stu-id="d4f32-128">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="d4f32-129">前に示したすべての例では、クォンタムゲートから送信されたワイヤの数とまったく同じ数 (qubits) の入力がクォンタムゲートに含まれていました。</span><span class="sxs-lookup"><span data-stu-id="d4f32-129">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="d4f32-130">最初は、クォンタム回線が一般に入力よりも多くの出力を持つことができると考えられるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="d4f32-130">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="d4f32-131">ただし、これは不可能です。これは、すべてのクォンタム操作、測定値の保存は、すべての処理が行われるためです。</span><span class="sxs-lookup"><span data-stu-id="d4f32-131">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="d4f32-132">同じ数の出力が入力として含まれていなかった場合は、元に戻すことはできず、そのため、不一致になります。</span><span class="sxs-lookup"><span data-stu-id="d4f32-132">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="d4f32-133">このため、サーキット図に描画されるすべてのボックスには、それを終了するときとまったく同じ数のワイヤを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4f32-133">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="d4f32-134">マルチ qubit 回路図は、単 qubit と同様の規則に従います。</span><span class="sxs-lookup"><span data-stu-id="d4f32-134">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="d4f32-135">明確な例として、$ を $ (H & otimes X) $ に $B、2つの qubit のを定義し、次のように回線を表現することができます。</span><span class="sxs-lookup"><span data-stu-id="d4f32-135">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="d4f32-136">![2つの qubit のユニタリ操作のサーキットダイアグラム](~/media/4.svg)</span><span class="sxs-lookup"><span data-stu-id="d4f32-136">![Circuit diagram of a two-qubit unitary operation](~/media/4.svg)</span></span>

<span data-ttu-id="d4f32-137">また、回線が使用されているコンテキストに応じて、2 1-qubit レジスタではなく、1つの2つの2つのビットレジスタに対するアクションを持つ $B $ を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="d4f32-137">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="d4f32-138">このような抽象回路図の中で最も役に立つのは、複雑なクォンタムアルゴリズムを高いレベルで記述し、基本ゲートにコンパイルする必要がない場合などです。</span><span class="sxs-lookup"><span data-stu-id="d4f32-138">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="d4f32-139">これは、アルゴリズム内の各サブルーチンがどのように機能するかについてすべての詳細を理解しなくても、大規模なクォンタムアルゴリズムのデータフローに関する直感を取得できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d4f32-139">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="d4f32-140">制御ゲート</span><span class="sxs-lookup"><span data-stu-id="d4f32-140">Controlled gates</span></span>
<span data-ttu-id="d4f32-141">マルチ qubit クォンタム回路図に組み込まれているもう1つのコンストラクトは制御です。</span><span class="sxs-lookup"><span data-stu-id="d4f32-141">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="d4f32-142">クォンタム片制御ゲートのアクション ($-ラムダ (G) $) を示します。ここでは、1つの qubit の値が $G $ のアプリケーションを制御します。この例では、製品状態入力 $-ラムダ (G) (\ alpha \ket {0} + \ket {1} ) \ket{\psi} = \ alpha \ket {0} \ket{\psi} + \ beta \ket {1} G\ket {\ psi} $ の例を</span><span class="sxs-lookup"><span data-stu-id="d4f32-142">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$.</span></span>
<span data-ttu-id="d4f32-143">つまり、制御されたゲートが $ \ psi $ を含むレジスタに $ $G を適用するのは、コントロールの qubit が値 $1 $ を受け取る場合のみです。</span><span class="sxs-lookup"><span data-stu-id="d4f32-143">That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="d4f32-144">一般に、このような制御された操作を回路図に記述します。</span><span class="sxs-lookup"><span data-stu-id="d4f32-144">In general, we describe such controlled operations in circuit diagrams as</span></span>

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="d4f32-145">![単一制御ゲートのサーキットダイアグラム](~/media/5.svg)</span><span class="sxs-lookup"><span data-stu-id="d4f32-145">![Circuit diagram of a singly controlled gate](~/media/5.svg)</span></span>

<span data-ttu-id="d4f32-146">ここで、黒い円はゲートが制御されているクォンタムビットを表し、垂直方向のワイヤは、コントロール qubit が値 $1 $ を受け取るときに適用されるユニタリを表します。</span><span class="sxs-lookup"><span data-stu-id="d4f32-146">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="d4f32-147">$G = X $ および $G = Z $ の特殊なケースでは、ゲートの制御されたバージョンを記述するために次の表記が導入されます (制御された X ゲートは[$CNOT $ gate](xref:microsoft.quantum.intrinsic.cnot)であることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="d4f32-147">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:microsoft.quantum.intrinsic.cnot)):</span></span>

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="d4f32-148">![特別なケースの制御ゲートの回路図](~/media/6.svg)</span><span class="sxs-lookup"><span data-stu-id="d4f32-148">![Circuit diagram for special cases of controlled gates](~/media/6.svg)</span></span>

<span data-ttu-id="d4f32-149">Q # は、操作の制御されたバージョンを自動的に生成するメソッドを提供します。これにより、プログラマは、これらの操作を手作業でコードに渡す必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="d4f32-149">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="d4f32-150">この例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d4f32-150">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="d4f32-151">測定演算子</span><span class="sxs-lookup"><span data-stu-id="d4f32-151">Measurement operator</span></span>
<span data-ttu-id="d4f32-152">回路図で視覚化する残りの操作は、測定値です。</span><span class="sxs-lookup"><span data-stu-id="d4f32-152">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="d4f32-153">測定は、qubit レジスタを受け取り、それを測定し、その結果を古典的な情報として出力します。</span><span class="sxs-lookup"><span data-stu-id="d4f32-153">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="d4f32-154">測定値はメーター記号で示され、常に入力として qubit レジスタ (実線で示されます) を受け取り、古典的な情報を出力します (2 本の線で示されます)。</span><span class="sxs-lookup"><span data-stu-id="d4f32-154">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="d4f32-155">具体的には、このようなサブサーキットは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d4f32-155">Specifically, such a subcircuit looks like:</span></span>

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="d4f32-156">![測定演算を表すシンボル](~/media/7.svg)</span><span class="sxs-lookup"><span data-stu-id="d4f32-156">![Symbol representing a measurement operation](~/media/7.svg)</span></span>

<span data-ttu-id="d4f32-157">Q # この目的のために[メジャー演算子](xref:microsoft.quantum.intrinsic.measure)を実装します。</span><span class="sxs-lookup"><span data-stu-id="d4f32-157">Q# implements a [Measure operator](xref:microsoft.quantum.intrinsic.measure) for this purpose.</span></span>
<span data-ttu-id="d4f32-158">詳細については、[測定に関するセクション](xref:microsoft.quantum.libraries.standard.prelude#measurements)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4f32-158">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="d4f32-159">同様に、サブサーキット</span><span class="sxs-lookup"><span data-stu-id="d4f32-159">Similarly, the subcircuit</span></span>

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="d4f32-160">![制御された操作を表す回路図](~/media/8.svg)</span><span class="sxs-lookup"><span data-stu-id="d4f32-160">![Circuit diagram representing a controlled operation](~/media/8.svg)</span></span>

<span data-ttu-id="d4f32-161">クラシックデプロイ制御ゲートを提供します。 $G $ は、$1 $ という従来の制御ビットで条件付きで適用されます。</span><span class="sxs-lookup"><span data-stu-id="d4f32-161">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="d4f32-162">受付回路の図</span><span class="sxs-lookup"><span data-stu-id="d4f32-162">Teleportation circuit diagram</span></span>
<span data-ttu-id="d4f32-163">クォンタムは、これらのコンポーネントを示す最良のクォンタムアルゴリズムであると考えられます。</span><span class="sxs-lookup"><span data-stu-id="d4f32-163">Quantum teleportation is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="d4f32-164">対応する[クォンタム kata](xref:microsoft.quantum.overview.katas)クォンタムを使用したハンズオンについては、結び付き使用と測定を使用して、quantum コンピューター内 (または quantum ネットワーク内の離れたコンピューター間) でデータを移動する方法について学ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="d4f32-164">You can learn hands-on with the corresponding [Quantum Kata](xref:microsoft.quantum.overview.katas) Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="d4f32-165">興味深いことに、実際には、qubit の値が何であるかを把握していなくても、特定の qubit の値を1つの qubit から別の値に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="d4f32-165">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="d4f32-166">これは、プロトコルが量子力学法に従って動作するために必要です。</span><span class="sxs-lookup"><span data-stu-id="d4f32-166">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="d4f32-167">次に、クォンタムの例を示します。また、クォンタム回線の読み取り方法を示すために、回路の注釈付きバージョンも提供します。</span><span class="sxs-lookup"><span data-stu-id="d4f32-167">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<!--- ![](.\media\tp2.svg){ width=50% } --->
<span data-ttu-id="d4f32-168">![Quantum の受付回線](~/media/tp2.svg)</span><span class="sxs-lookup"><span data-stu-id="d4f32-168">![Quantum teleportation circuit](~/media/tp2.svg)</span></span>
