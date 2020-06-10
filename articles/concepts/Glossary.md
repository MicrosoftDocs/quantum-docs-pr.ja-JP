---
title: クォンタムコンピューティング用語集
description: クォンタムコンピューティングで使用される一般的な用語、アクション、およびオブジェクトの用語集。
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
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
ms.openlocfilehash: 2a3b1fe480b9886d0c11255bb1b1e01402dce4f7
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630105"
---
# <a name="quantum-computing-glossary"></a><span data-ttu-id="32813-103">クォンタムコンピューティング用語集</span><span class="sxs-lookup"><span data-stu-id="32813-103">Quantum computing glossary</span></span>

## <a name="adjoint"></a><span data-ttu-id="32813-104">Adjoint</span><span class="sxs-lookup"><span data-stu-id="32813-104">Adjoint</span></span>

<span data-ttu-id="32813-105">[操作](xref:microsoft.quantum.glossary#operation)の複素共役転置。</span><span class="sxs-lookup"><span data-stu-id="32813-105">The complex conjugate transpose of an [operation](xref:microsoft.quantum.glossary#operation).</span></span> <span data-ttu-id="32813-106">[ユニタリ](xref:microsoft.quantum.glossary#unitary-operator)演算子を実装する操作の場合、adjoint は演算の逆であり、ダガー記号によって示されます。</span><span class="sxs-lookup"><span data-stu-id="32813-106">For operations that implement a [unitary](xref:microsoft.quantum.glossary#unitary-operator) operator, the adjoint is the inverse of the operation and is indicated by a dagger symbol.</span></span> <span data-ttu-id="32813-107">たとえば、操作が $U の中からの $U を表している場合、は "^" を `U` $ `Adjoint U` 表し $ ます。</span><span class="sxs-lookup"><span data-stu-id="32813-107">For example, if the operation `U` represents the unitary operator $U$, then `Adjoint U` represents $U^\dagger$.</span></span> <span data-ttu-id="32813-108">詳細については、「 [Adjoint](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-108">For more information, see [Adjoint](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span></span>

## <a name="ancilla"></a><span data-ttu-id="32813-109">Ancilla</span><span class="sxs-lookup"><span data-stu-id="32813-109">Ancilla</span></span>

<span data-ttu-id="32813-110">クォンタムコンピューターの一時的なメモリとして機能し、必要に応じて割り当てられ、割り当てが解除される[qubit](xref:microsoft.quantum.glossary#qubit) 。</span><span class="sxs-lookup"><span data-stu-id="32813-110">A [qubit](xref:microsoft.quantum.glossary#qubit) that serves as temporary memory for a quantum computer and is allocated and de-allocated as needed.</span></span>  <span data-ttu-id="32813-111">詳細については、「[複数の qubits](xref:microsoft.quantum.concepts.multiple-qubits)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-111">For more information, see [Multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

## <a name="bell-state"></a><span data-ttu-id="32813-112">ベルの状態</span><span class="sxs-lookup"><span data-stu-id="32813-112">Bell state</span></span>

<span data-ttu-id="32813-113">2つの qubits の下回っ[あり](xref:microsoft.quantum.glossary#entanglement)の4つの[状態](xref:microsoft.quantum.glossary#quantum-state)のうちの1つ。</span><span class="sxs-lookup"><span data-stu-id="32813-113">One of four specific maximally [entangled](xref:microsoft.quantum.glossary#entanglement) [quantum states](xref:microsoft.quantum.glossary#quantum-state) of two qubits.</span></span> <span data-ttu-id="32813-114">4つの状態は、$ \ket { \ beta_ {ij } } = (\mathbb{I/ } otimes X ^ iZ ^ j) (\ket{00 } + \ket{11 } )/\ sqrt{2 $ } と定義されています。</span><span class="sxs-lookup"><span data-stu-id="32813-114">The four states are defined $\ket{\beta_{ij}} = (\mathbb{I} \otimes X^iZ^j) (\ket{00} + \ket{11}) / \sqrt{2}$.</span></span> <span data-ttu-id="32813-115">ベルの状態は、 [EPR ペア](xref:microsoft.quantum.glossary#epr-pair)とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="32813-115">A Bell state is also known as an [EPR pair](xref:microsoft.quantum.glossary#epr-pair).</span></span>

## <a name="bloch-sphere"></a><span data-ttu-id="32813-116">Bloch 球</span><span class="sxs-lookup"><span data-stu-id="32813-116">Bloch sphere</span></span>

<span data-ttu-id="32813-117">3次元の単位球のポイントとしての単一[qubit](xref:microsoft.quantum.glossary#qubit) [クォンタム状態](xref:microsoft.quantum.glossary#quantum-state)のグラフィック表現。</span><span class="sxs-lookup"><span data-stu-id="32813-117">A graphical representation of a single-[qubit](xref:microsoft.quantum.glossary#qubit) [quantum state](xref:microsoft.quantum.glossary#quantum-state) as a point in a three-dimensional unit sphere.</span></span> <span data-ttu-id="32813-118">詳細については、「 [Bloch 球を使用した Qubits と変換の視覚化](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-118">For more information, see  [Visualizing Qubits and Transformations using the Bloch Sphere](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span></span>

## <a name="callable"></a><span data-ttu-id="32813-119">呼び出し可能</span><span class="sxs-lookup"><span data-stu-id="32813-119">Callable</span></span>

<span data-ttu-id="32813-120">Q # 言語の[操作](xref:microsoft.quantum.glossary#operation)または[関数](xref:microsoft.quantum.glossary#function)。</span><span class="sxs-lookup"><span data-stu-id="32813-120">An [operation](xref:microsoft.quantum.glossary#operation) or [function](xref:microsoft.quantum.glossary#function) in the Q# language.</span></span> <span data-ttu-id="32813-121">詳細については、「[操作と関数](xref:microsoft.quantum.guide.operationsfunctions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-121">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="clifford-group"></a><span data-ttu-id="32813-122">Clifford グループ</span><span class="sxs-lookup"><span data-stu-id="32813-122">Clifford group</span></span>

<span data-ttu-id="32813-123">[Bloch 球](xref:microsoft.quantum.glossary#bloch-sphere)の octants と、 [p li 演算子](xref:microsoft.quantum.glossary#pauli-operators)の効果の順列を占有する操作のセット。</span><span class="sxs-lookup"><span data-stu-id="32813-123">The set of operations that occupy the octants of the [Bloch sphere](xref:microsoft.quantum.glossary#bloch-sphere) and effect permutations of the [Pauli operators](xref:microsoft.quantum.glossary#pauli-operators).</span></span> <span data-ttu-id="32813-124">これには、[操作 $ $X](xref:microsoft.quantum.intrinsic.x)、 [$Y $ ](xref:microsoft.quantum.intrinsic.y)、 [ $ $Z](xref:microsoft.quantum.intrinsic.z)、 [ $ $H](xref:microsoft.quantum.intrinsic.h)および[$S $ ](xref:microsoft.quantum.intrinsic.s)が含まれます。</span><span class="sxs-lookup"><span data-stu-id="32813-124">These include the operations [$X$](xref:microsoft.quantum.intrinsic.x), [$Y$](xref:microsoft.quantum.intrinsic.y), [$Z$](xref:microsoft.quantum.intrinsic.z), [$H$](xref:microsoft.quantum.intrinsic.h) and [$S$](xref:microsoft.quantum.intrinsic.s).</span></span>

## <a name="controlled"></a><span data-ttu-id="32813-125">た</span><span class="sxs-lookup"><span data-stu-id="32813-125">Controlled</span></span>

<span data-ttu-id="32813-126">ターゲット操作のイネーブラーとして1つ以上の[qubits](xref:microsoft.quantum.glossary#qubit)を受け取るクォンタム[操作](xref:microsoft.quantum.glossary#operation)。</span><span class="sxs-lookup"><span data-stu-id="32813-126">A quantum [operation](xref:microsoft.quantum.glossary#operation) that takes one or more [qubits](xref:microsoft.quantum.glossary#qubit) as enablers for the target operation.</span></span> <span data-ttu-id="32813-127">詳細については、「[制御対象と adjoint の操作](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-127">For more information, see [Controlled and adjoint operations](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span></span>

## <a name="dirac-notation"></a><span data-ttu-id="32813-128">Dirac 表記</span><span class="sxs-lookup"><span data-stu-id="32813-128">Dirac Notation</span></span>

<span data-ttu-id="32813-129">[クォンタムの状態](xref:microsoft.quantum.glossary#quantum-state)の表現を簡略化するシンボリックな略記 ( *bra k* notation とも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="32813-129">A symbolic shorthand that simplifies the representation of [quantum states](xref:microsoft.quantum.glossary#quantum-state), also called *bra-ket* notation.</span></span>  <span data-ttu-id="32813-130">*Bra*の部分は、行ベクトルを表します。たとえば、$ } _2 と a {_1 {a { bmatrix } _1 } & a { } \ end{ bmatrix } $ と*k*部分は、列ベクター $ \ket{B } = \ begin{ bmatrix } B {_1 } \\ \\ B {_2/ } end{$ を表し bmatrix } ます。</span><span class="sxs-lookup"><span data-stu-id="32813-130">The *bra* portion represents a row vector, for example  $\bra{A} = \begin{bmatrix} A{_1} & A{_2} \end{bmatrix}$ and the *ket* portion represents a column vector, $\ket{B} = \begin{bmatrix} B{_1} \\\\ B{_2} \end{bmatrix}$.</span></span> <span data-ttu-id="32813-131">詳細については、「 [Dirac 表記](xref:microsoft.quantum.concepts.dirac)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-131">For more information, see [Dirac Notation](xref:microsoft.quantum.concepts.dirac).</span></span>

## <a name="eigenvalue"></a><span data-ttu-id="32813-132">Eigenvalue</span><span class="sxs-lookup"><span data-stu-id="32813-132">Eigenvalue</span></span>

<span data-ttu-id="32813-133">変換の適用によって、特定の変換の[eigenvector](xref:microsoft.quantum.glossary#eigenvector)の大きさが変更される要因。</span><span class="sxs-lookup"><span data-stu-id="32813-133">The factor by which the magnitude of an [eigenvector](xref:microsoft.quantum.glossary#eigenvector) of a given transformation is changed by the application of the transformation.</span></span>  <span data-ttu-id="32813-134">Square 行列 $M と eigenvector $v が指定され $ て $ いる場合、$Mv = cv $ になります。ここで $c $ は eigenvalue で、任意の引数の数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="32813-134">Given a square matrix $M$ and an eigenvector $v$, then $Mv = cv$, where $c$ is the eigenvalue and can be a complex number of any argument.</span></span> <span data-ttu-id="32813-135">詳細については、「[高度なマトリックスの概念](xref:microsoft.quantum.concepts.matrix-advanced)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-135">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="eigenvector"></a><span data-ttu-id="32813-136">Eigenvector</span><span class="sxs-lookup"><span data-stu-id="32813-136">Eigenvector</span></span>

<span data-ttu-id="32813-137">指定された変換によって方向が変更されず、そのベクトルの[eigenvalue](xref:microsoft.quantum.glossary#eigenvalue)に対応する係数によって大きさが変更されるベクトル。</span><span class="sxs-lookup"><span data-stu-id="32813-137">A vector whose direction is unchanged by a given transformation and whose magnitude is changed by a factor corresponding to that vector's [eigenvalue](xref:microsoft.quantum.glossary#eigenvalue).</span></span> <span data-ttu-id="32813-138">二乗行列 $M $ と eigenvalue $c を指定した $ 場合、$Mv = cv となります $ 。ここで $v $ はマトリックスの eigenvector であり、任意の数の引数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="32813-138">Given a square matrix $M$ and an eigenvalue $c$, then $Mv = cv$, where $v$ is an eigenvector of the matrix and can be a complex number of any argument.</span></span> <span data-ttu-id="32813-139">詳細については、「[高度なマトリックスの概念](xref:microsoft.quantum.concepts.matrix-advanced)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-139">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="entanglement"></a><span data-ttu-id="32813-140">もつれ</span><span class="sxs-lookup"><span data-stu-id="32813-140">Entanglement</span></span>

<span data-ttu-id="32813-141">[Qubits](xref:microsoft.quantum.glossary#qubit)などのクォンタムパーティクルは、互いに独立して記述できないように、接続するか、または複数の*角度で傾ける*ことができます。</span><span class="sxs-lookup"><span data-stu-id="32813-141">Quantum particles, such as [qubits](xref:microsoft.quantum.glossary#qubit), can be connected or *entangled* such that they cannot be described independently from each other.</span></span> <span data-ttu-id="32813-142">これらの測定結果は、無限に分離されている場合でも相関関係があります。</span><span class="sxs-lookup"><span data-stu-id="32813-142">Their measurement results are correlated even when they are separated infinitely far away.</span></span> <span data-ttu-id="32813-143">Entanglement、qubit の[状態](xref:microsoft.quantum.glossary#quantum-state)を[測定](xref:microsoft.quantum.glossary#measurement)するために不可欠です。</span><span class="sxs-lookup"><span data-stu-id="32813-143">Entanglement is essential to [measuring](xref:microsoft.quantum.glossary#measurement) the [state](xref:microsoft.quantum.glossary#quantum-state) of a qubit.</span></span>  <span data-ttu-id="32813-144">詳細については、「[高度なマトリックスの概念](xref:microsoft.quantum.concepts.matrix-advanced)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-144">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="epr-pair"></a><span data-ttu-id="32813-145">EPR ペア</span><span class="sxs-lookup"><span data-stu-id="32813-145">EPR pair</span></span>

<span data-ttu-id="32813-146">2つの[qubits](xref:microsoft.quantum.glossary#qubit)の下回っありの4つの[状態](xref:microsoft.quantum.glossary#quantum-state)のうちの1つ。</span><span class="sxs-lookup"><span data-stu-id="32813-146">One of four specific maximally entangled [quantum states](xref:microsoft.quantum.glossary#quantum-state) of two [qubits](xref:microsoft.quantum.glossary#qubit).</span></span> <span data-ttu-id="32813-147">4つの状態は、$ \ket { \ beta_ {ij } } = (\mathbb{1/ } otimes X ^ iZ ^ j) (\ket{00 } + \ket{11 } )/\ sqrt{2 $ } と定義されています。</span><span class="sxs-lookup"><span data-stu-id="32813-147">The four states are defined $\ket{\beta_{ij}} = (\mathbb{1} \otimes X^iZ^j) (\ket{00} + \ket{11}) / \sqrt{2}$.</span></span> <span data-ttu-id="32813-148">EPR ペアは[ベル状態](xref:microsoft.quantum.glossary#bell-state)とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="32813-148">An EPR pair is also known as a [Bell state](xref:microsoft.quantum.glossary#bell-state)</span></span>

## <a name="evolution"></a><span data-ttu-id="32813-149">発展</span><span class="sxs-lookup"><span data-stu-id="32813-149">Evolution</span></span>

<span data-ttu-id="32813-150">クォンタムの[状態](xref:microsoft.quantum.glossary#quantum-state)が時間の経過と共にどのように変化するか。</span><span class="sxs-lookup"><span data-stu-id="32813-150">How a [quantum state](xref:microsoft.quantum.glossary#quantum-state) changes over time.</span></span> <span data-ttu-id="32813-151">詳細については、「 [Matrix 指数](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-151">For more information, see [Matrix exponentials](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).</span></span>

## <a name="function"></a><span data-ttu-id="32813-152">関数</span><span class="sxs-lookup"><span data-stu-id="32813-152">Function</span></span>
<span data-ttu-id="32813-153">純粋なクラシック (非クォンタム) の Q # 言語のサブルーチンの種類。</span><span class="sxs-lookup"><span data-stu-id="32813-153">A type of subroutine in the Q# language that is purely classical (non-quantum).</span></span> <span data-ttu-id="32813-154">関数はクォンタムアルゴリズム内で使用されますが、 [qubits](xref:microsoft.quantum.glossary#qubit)または call[操作](xref:microsoft.quantum.glossary#operation)では動作しません。</span><span class="sxs-lookup"><span data-stu-id="32813-154">While functions are used within quantum algorithms, they cannot act on [qubits](xref:microsoft.quantum.glossary#qubit) or call [operations](xref:microsoft.quantum.glossary#operation).</span></span> <span data-ttu-id="32813-155">詳細については、「[操作と関数](xref:microsoft.quantum.guide.operationsfunctions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-155">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="gate"></a><span data-ttu-id="32813-156">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="32813-156">Gate</span></span>

<span data-ttu-id="32813-157">古典的なロジックゲートの概念に基づいた、クォンタム[操作](xref:microsoft.quantum.glossary#operation)の従来の用語。</span><span class="sxs-lookup"><span data-stu-id="32813-157">A legacy term for a quantum [operation](xref:microsoft.quantum.glossary#operation), based on the concept of classical logic gates.</span></span> <span data-ttu-id="32813-158">[クォンタム回線](xref:microsoft.quantum.glossary#quantum-circuit-diagram)は、従来のロジック回線と同様の概念に基づいて、ゲート (または操作) のネットワークです。</span><span class="sxs-lookup"><span data-stu-id="32813-158">A [quantum circuit](xref:microsoft.quantum.glossary#quantum-circuit-diagram) is a network of gates (or operations), based on the similar concept of classical logic circuits.</span></span>

## <a name="global-phase"></a><span data-ttu-id="32813-159">グローバルフェーズ</span><span class="sxs-lookup"><span data-stu-id="32813-159">Global phase</span></span>

<span data-ttu-id="32813-160">2つの[状態](xref:microsoft.quantum.glossary#quantum-state)が1つの複素数の倍数に等しい場合 $e ^ {i \phi } $,、グローバルフェーズが異なると言います。</span><span class="sxs-lookup"><span data-stu-id="32813-160">When two [states](xref:microsoft.quantum.glossary#quantum-state) are identical up to a multiple of a complex number $e^{i\phi}$, they are said to differ up to a global phase.</span></span> <span data-ttu-id="32813-161">ローカルフェーズとは異なり、グローバルフェーズはどの[measurment](xref:microsoft.quantum.glossary#measurement)でも観察できません。</span><span class="sxs-lookup"><span data-stu-id="32813-161">Unlike local phases, global phases cannot be observed through any [measurment](xref:microsoft.quantum.glossary#measurement).</span></span> <span data-ttu-id="32813-162">詳細については、「 [Qubit](xref:microsoft.quantum.concepts.qubit)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-162">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="hadamard"></a><span data-ttu-id="32813-163">Hadamard</span><span class="sxs-lookup"><span data-stu-id="32813-163">Hadamard</span></span>

<span data-ttu-id="32813-164">Hadamard 操作 (Hadamard gate または transform とも呼ばれます) は、1つの[qubit](xref:microsoft.quantum.glossary#qubit)に作用し、 [superposition](xref:microsoft.quantum.glossary#superposition) } } qubit が最初に $ \ket{1 $ 状態にある場合は、$ \ket{0 $ または $ \ket{0 $ の偶数法則に配置し } ます。</span><span class="sxs-lookup"><span data-stu-id="32813-164">The Hadamard operation (also referred to as the Hadamard gate or transform) acts on a single [qubit](xref:microsoft.quantum.glossary#qubit) and puts it in an even [superposition](xref:microsoft.quantum.glossary#superposition) of $\ket{0}$ or $\ket{1}$ if the qubit is initially in the $\ket{0}$ state.</span></span> <span data-ttu-id="32813-165">Q # では、この操作は定義済みの操作によって適用され [`H`](xref:microsoft.quantum.intrinsic.h) ます。</span><span class="sxs-lookup"><span data-stu-id="32813-165">In Q#, this operation is applied by the pre-defined [`H`](xref:microsoft.quantum.intrinsic.h) operation.</span></span>

## <a name="immutable"></a><span data-ttu-id="32813-166">変更不可</span><span class="sxs-lookup"><span data-stu-id="32813-166">Immutable</span></span>

<span data-ttu-id="32813-167">値を変更できない変数。</span><span class="sxs-lookup"><span data-stu-id="32813-167">A variable whose value cannot be changed.</span></span> <span data-ttu-id="32813-168">Q # の変更できない変数は、キーワードを使用して作成され `let` ます。</span><span class="sxs-lookup"><span data-stu-id="32813-168">An immutable variable in Q# is created using the `let` keyword.</span></span> <span data-ttu-id="32813-169">変更*可能*な変数を宣言するには、 [mutable](xref:microsoft.quantum.glossary#immutable)キーワードを使用してを宣言し、キーワードを使用して `set` 値を変更します。</span><span class="sxs-lookup"><span data-stu-id="32813-169">To declare variables that *can* be changed, use the [mutable](xref:microsoft.quantum.glossary#immutable) keyword to declare and the `set` keyword to modify the value.</span></span> 

## <a name="measurement"></a><span data-ttu-id="32813-170">Measurement</span><span class="sxs-lookup"><span data-stu-id="32813-170">Measurement</span></span>

<span data-ttu-id="32813-171">監視の結果を生成する[qubit](xref:microsoft.quantum.glossary#qubit) (または qubit のセット) の操作。従来のビットを取得します。</span><span class="sxs-lookup"><span data-stu-id="32813-171">A manipulation of a [qubit](xref:microsoft.quantum.glossary#qubit) (or set of qubits) that yields the result of an observation, in effect obtaining a classical bit.</span></span> <span data-ttu-id="32813-172">詳細については、「 [Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-172">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).</span></span>

## <a name="mutable"></a><span data-ttu-id="32813-173">変更可能</span><span class="sxs-lookup"><span data-stu-id="32813-173">Mutable</span></span>

<span data-ttu-id="32813-174">値が作成後に変更される可能性がある変数。</span><span class="sxs-lookup"><span data-stu-id="32813-174">A variable whose value may be changed after it is created.</span></span> <span data-ttu-id="32813-175">Q # の変更可能な変数は、キーワードを使用して宣言され、 `mutable` キーワードを使用して変更され `set` ます。</span><span class="sxs-lookup"><span data-stu-id="32813-175">A mutable variable in Q# is declared using the `mutable` keyword and modified using the `set` keyword.</span></span> <span data-ttu-id="32813-176">キーワードを使用して作成された変数 `let` は[不変](xref:microsoft.quantum.glossary#immutable)であり、その値を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="32813-176">Variables created with the `let` keyword are [immutable](xref:microsoft.quantum.glossary#immutable) and their value cannot be changed.</span></span>

## <a name="namespace"></a><span data-ttu-id="32813-177">名前空間</span><span class="sxs-lookup"><span data-stu-id="32813-177">Namespace</span></span>

<span data-ttu-id="32813-178">関連する名前 (つまり、[操作](xref:microsoft.quantum.glossary#operation)、[関数](xref:microsoft.quantum.glossary#function)、および[ユーザー定義型](xref:microsoft.quantum.glossary#user-defined-type)) のコレクションのラベル。</span><span class="sxs-lookup"><span data-stu-id="32813-178">A label for a collection of related names (i.e., [operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function), and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type)).</span></span> <span data-ttu-id="32813-179">たとえば、名前空間は、初期状態の準備に役立つ標準ライブラリで定義されているすべてのシンボルをラベル[付けします](xref:microsoft.quantum.preparation)。</span><span class="sxs-lookup"><span data-stu-id="32813-179">For instance the namespace [Microsoft.Quantum.Preparation](xref:microsoft.quantum.preparation) labels all of the symbols defined in the standard library that help with preparing initial states.</span></span>

## <a name="operation"></a><span data-ttu-id="32813-180">操作</span><span class="sxs-lookup"><span data-stu-id="32813-180">Operation</span></span>

<span data-ttu-id="32813-181">Q # でのクォンタム実行の基本単位。</span><span class="sxs-lookup"><span data-stu-id="32813-181">The basic unit of quantum execution in Q#.</span></span> <span data-ttu-id="32813-182">これは、C、C++、または Python の関数、または C# または Java の静的メソッドとほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="32813-182">It is roughly equivalent to a function in C, C++ or Python, or a static method in C# or Java.</span></span> <span data-ttu-id="32813-183">詳細については、「[操作と関数](xref:microsoft.quantum.guide.operationsfunctions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-183">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="operator-application"></a><span data-ttu-id="32813-184">オペレーターアプリケーション</span><span class="sxs-lookup"><span data-stu-id="32813-184">Operator application</span></span>

<span data-ttu-id="32813-185">クォンタム操作を実行しています。</span><span class="sxs-lookup"><span data-stu-id="32813-185">Performing a quantum operation.</span></span> <span data-ttu-id="32813-186">通常、これは、現在のクォンタム状態ベクトルに対して、通常、ユニタリ行列を適用します。</span><span class="sxs-lookup"><span data-stu-id="32813-186">This typically applies a unitary matrix to the current quantum state vector.</span></span>

## <a name="oracle"></a><span data-ttu-id="32813-187">Oracle</span><span class="sxs-lookup"><span data-stu-id="32813-187">Oracle</span></span>

<span data-ttu-id="32813-188">実行時にクォンタムアルゴリズムにデータ依存の情報を提供するサブルーチン。</span><span class="sxs-lookup"><span data-stu-id="32813-188">A subroutine that provides data-dependent information to a quantum algorithm at runtime.</span></span> <span data-ttu-id="32813-189">通常、目標は、法則内の入力に対応する出力の[法則](xref:microsoft.quantum.glossary#superposition)を提供することです。</span><span class="sxs-lookup"><span data-stu-id="32813-189">Typically, the goal is to provide a [superposition](xref:microsoft.quantum.glossary#superposition) of outputs corresponding to inputs that are in superposition.</span></span> <span data-ttu-id="32813-190">詳細については、「 [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-190">For more information, see [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles).</span></span>

## <a name="partial-application"></a><span data-ttu-id="32813-191">部分アプリケーション</span><span class="sxs-lookup"><span data-stu-id="32813-191">Partial application</span></span>

<span data-ttu-id="32813-192">必須の入力をすべて指定せずに[関数](xref:microsoft.quantum.glossary#function)または[操作](xref:microsoft.quantum.glossary#operation)を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="32813-192">Calling a [function](xref:microsoft.quantum.glossary#function) or [operation](xref:microsoft.quantum.glossary#operation) without all the required inputs.</span></span> <span data-ttu-id="32813-193">これにより、今後のアプリケーションの実行中に、不足しているパラメーター (アンダースコアで示される) のみを必要とする新しい[呼び出し](xref:microsoft.quantum.glossary#callable)可能が返されます。</span><span class="sxs-lookup"><span data-stu-id="32813-193">This returns a new [callable](xref:microsoft.quantum.glossary#callable) that only needs the missing parameters (indicated by an underscore) to be supplied during a future application.</span></span> <span data-ttu-id="32813-194">たとえば、関数を指定する `MyFunc(x : int, y : int) : int {return x + y;}` と、その関数を新しい関数に部分的に適用でき `let NewFunc = MyFunc(_, 3)` ます。</span><span class="sxs-lookup"><span data-stu-id="32813-194">For example, given the function `MyFunc(x : int, y : int) : int {return x + y;}` you can partially apply it to a new function `let NewFunc = MyFunc(_, 3)`.</span></span> <span data-ttu-id="32813-195">その後、 `NewFunc(2)` 値*5*を返すパラメーターを指定しないで、後で新しい関数を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="32813-195">You can then call the new function at a later time with the missing parameter `NewFunc(2)` which returns the value *5*.</span></span>  <span data-ttu-id="32813-196">詳細については、「[部分アプリケーション](xref:microsoft.quantum.guide.operationsfunctions#partial-application)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-196">For more information, see [Partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application).</span></span>

## <a name="pauli-operators"></a><span data-ttu-id="32813-197">P# li 演算子</span><span class="sxs-lookup"><span data-stu-id="32813-197">Pauli operators</span></span>

<span data-ttu-id="32813-198">`X`、、 `Y` およびクォンタム操作として知られる3つの 2 x 2 つのユニタリ行列のセット `Z` 。</span><span class="sxs-lookup"><span data-stu-id="32813-198">A set of three 2 x 2 unitary matrices known as the `X`, `Y` and `Z` quantum operations.</span></span> <span data-ttu-id="32813-199">多くの場合、$I の id 行列 $ もセットに含まれています。</span><span class="sxs-lookup"><span data-stu-id="32813-199">The identity matrix, $I$, is often included in the set as well.</span></span>  <span data-ttu-id="32813-200">$I = \ begin{ bmatrix } 1 & 0 \\ \\ 0 & 1 & end{ bmatrix } $, $X = \ begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \ end{ bmatrix } $, $Y = \ begin{ bmatrix } 0 &-i \\ \\ i & 0 \ end{ bmatrix } $, $Z = \ begin{ bmatrix } 1 & 0 \\ \\ 0 &-1 \ end{ bmatrix } $。</span><span class="sxs-lookup"><span data-stu-id="32813-200">$I = \begin{bmatrix} 1 & 0 \\\\ 0 & 1 \end{bmatrix}$, $X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix}$, $Y = \begin{bmatrix} 0 & -i \\\\ i & 0 \end{bmatrix}$, $Z = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}$.</span></span>   <span data-ttu-id="32813-201">詳細については、「 [Single qubit 操作](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-201">For more information, see [Single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span></span>

## <a name="quantum-circuit-diagram"></a><span data-ttu-id="32813-202">クォンタム回線の図</span><span class="sxs-lookup"><span data-stu-id="32813-202">Quantum circuit diagram</span></span>

<span data-ttu-id="32813-203">単純なクォンタムプログラムの一連の[操作](xref:microsoft.quantum.glossary#operation)(または[ゲート](xref:microsoft.quantum.glossary#gate)) をグラフィカルに表すメソッド。たとえば、</span><span class="sxs-lookup"><span data-stu-id="32813-203">A method to graphically represent the sequence of [operations](xref:microsoft.quantum.glossary#operation) (or [gates](xref:microsoft.quantum.glossary#gate)) for simple quantum programs, for example</span></span> 

![回路図のサンプル](~/media/qpe.png)<span data-ttu-id="32813-205">.</span><span class="sxs-lookup"><span data-stu-id="32813-205">.</span></span> 

<span data-ttu-id="32813-206">詳細については、「[クォンタム回線](xref:microsoft.quantum.concepts.circuits)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-206">For more information, see [Quantum circuits](xref:microsoft.quantum.concepts.circuits).</span></span>

## <a name="quantum-libraries"></a><span data-ttu-id="32813-207">クォンタムライブラリ</span><span class="sxs-lookup"><span data-stu-id="32813-207">Quantum libraries</span></span>

<span data-ttu-id="32813-208">Q # プログラムを作成するための[操作](xref:microsoft.quantum.glossary#operation)、[関数](xref:microsoft.quantum.glossary#function)、および[ユーザー定義型](xref:microsoft.quantum.glossary#user-defined-type)のコレクション。</span><span class="sxs-lookup"><span data-stu-id="32813-208">Collections of [operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function) and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type) for creating Q# programs.</span></span> <span data-ttu-id="32813-209">[標準ライブラリ](xref:microsoft.quantum.libraries.standard.intro)は、既定でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="32813-209">The [Standard library](xref:microsoft.quantum.libraries.standard.intro) is installed by default.</span></span> <span data-ttu-id="32813-210">使用できるその他のライブラリは、[化学ライブラリ](xref:microsoft.quantum.chemistry.concepts.intro)、[数値ライブラリ](xref:microsoft.quantum.numerics.intro)、 [Machine learning ライブラリ](xref:microsoft.quantum.machine-learning.concepts.intro)です。</span><span class="sxs-lookup"><span data-stu-id="32813-210">Other libraries available are the [Chemistry library](xref:microsoft.quantum.chemistry.concepts.intro), the [Numerics library](xref:microsoft.quantum.numerics.intro) and the [Machine learning library](xref:microsoft.quantum.machine-learning.concepts.intro).</span></span>

## <a name="quantum-state"></a><span data-ttu-id="32813-211">クォンタムの状態</span><span class="sxs-lookup"><span data-stu-id="32813-211">Quantum state</span></span>

<span data-ttu-id="32813-212">分離されたクォンタムシステムの正確な状態。[測定](xref:microsoft.quantum.glossary#measurement)確率を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="32813-212">The precise state of an isolated quantum system, from which [measurement](xref:microsoft.quantum.glossary#measurement) probabilities can be extracted.</span></span> <span data-ttu-id="32813-213">クォンタムコンピューティングでは、この情報を使用して、操作に対する qubits の応答方法をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="32813-213">In quantum computing, the quantum simulator uses this information to simulate how qubits respond to operations.</span></span> <span data-ttu-id="32813-214">詳細については、「 [Qubit](xref:microsoft.quantum.concepts.qubit)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-214">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="qubit"></a><span data-ttu-id="32813-215">Qubit</span><span class="sxs-lookup"><span data-stu-id="32813-215">Qubit</span></span>

<span data-ttu-id="32813-216">古典*的なコンピューティングの1つ*の部分に似た、クォンタム情報の基本単位。</span><span class="sxs-lookup"><span data-stu-id="32813-216">A basic unit of quantum information, analogous to a *bit* in classical computing.</span></span> <span data-ttu-id="32813-217">詳細については、「 [Qubit](xref:microsoft.quantum.concepts.qubit)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-217">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="repeat-until-success"></a><span data-ttu-id="32813-218">繰り返し-成功まで</span><span class="sxs-lookup"><span data-stu-id="32813-218">Repeat-until-success</span></span>

<span data-ttu-id="32813-219">見込みが成功するクォンタムアルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="32813-219">A quantum algorithm that probabilistically succeeds.</span></span> <span data-ttu-id="32813-220">エラーが発生すると、ルーチンは成功するまで (または制限に達したときに) 再試行します。</span><span class="sxs-lookup"><span data-stu-id="32813-220">Upon failure, the routine will retry until successful (or a limit has been reached).</span></span> <span data-ttu-id="32813-221">詳細については、「[成功まで繰り返す (RUS)](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-221">For more information, see [Repeat Until Success (RUS)](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)</span></span>

## <a name="standard-libraries"></a><span data-ttu-id="32813-222">標準ライブラリ</span><span class="sxs-lookup"><span data-stu-id="32813-222">Standard libraries</span></span>

<span data-ttu-id="32813-223">インストール時に Q # コンパイラと共にインストールされる[操作](xref:microsoft.quantum.glossary#operation)、[関数](xref:microsoft.quantum.glossary#function)、および[ユーザー定義型](xref:microsoft.quantum.glossary#user-defined-type)。</span><span class="sxs-lookup"><span data-stu-id="32813-223">[Operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function) and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type) that are installed along with the Q# compiler during installation.</span></span> <span data-ttu-id="32813-224">標準ライブラリの実装は、ターゲットコンピューターに対しては依存しません。</span><span class="sxs-lookup"><span data-stu-id="32813-224">The standard library implementation is agnostic with respect to target machines.</span></span> <span data-ttu-id="32813-225">詳細については、「[標準ライブラリ](xref:microsoft.quantum.libraries.standard.intro)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-225">For more information, see [Standard libraries](xref:microsoft.quantum.libraries.standard.intro).</span></span>

## <a name="superposition"></a><span data-ttu-id="32813-226">法則</span><span class="sxs-lookup"><span data-stu-id="32813-226">Superposition</span></span>

<span data-ttu-id="32813-227">量子コンピューティングの概念は、 [qubit](xref:microsoft.quantum.glossary#qubit)が測定されるまでの2つの状態 ($ \ket{0 } $ と $ \ket{1 } $) の[measured](xref:microsoft.quantum.glossary#measurement)線形組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="32813-227">The concept in quantum computing that a [qubit](xref:microsoft.quantum.glossary#qubit) is a linear combination of two states, $\ket{0}$ and $\ket{1}$, until it is [measured](xref:microsoft.quantum.glossary#measurement).</span></span>  <span data-ttu-id="32813-228">詳細については、「[クォンタムコンピューティングについ](xref:microsoft.quantum.overview.understanding)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-228">For more information, see [Understanding quantum computing](xref:microsoft.quantum.overview.understanding).</span></span>

## <a name="target-machine"></a><span data-ttu-id="32813-229">ターゲットコンピューター</span><span class="sxs-lookup"><span data-stu-id="32813-229">Target machine</span></span>

<span data-ttu-id="32813-230">ハードウェアまたはシミュレーションの抽象的なクォンタムプログラムを下げるコンパイルターゲット。</span><span class="sxs-lookup"><span data-stu-id="32813-230">A compilation target that lowers an abstract quantum program towards hardware or simulation.</span></span> <span data-ttu-id="32813-231">これには通常、ゲートの置換、エラー修正のためのエンコード、ジオメトリレイアウトなど、さまざまな目的のための再書き込みが含まれます。</span><span class="sxs-lookup"><span data-stu-id="32813-231">This typically include re-writes for many purposes including gate replacement, encoding for error correction, geometric layout and others.</span></span> <span data-ttu-id="32813-232">詳細については、「[クォンタムシミュレーターとホストアプリケーション](xref:microsoft.quantum.machines)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-232">For more information, see [Quantum simulators and host applications](xref:microsoft.quantum.machines).</span></span>

## <a name="teleportation"></a><span data-ttu-id="32813-233">テレポーテーション</span><span class="sxs-lookup"><span data-stu-id="32813-233">Teleportation</span></span>

<span data-ttu-id="32813-234">[結び付き](xref:microsoft.quantum.glossary#entanglement)[測定と測定](xref:microsoft.quantum.glossary#measurement)を[quantum state](xref:microsoft.quantum.glossary#quantum-state)使用して、qubit を物理的に移動せずに1つの場所から別の場所に1つの[qubit](xref:microsoft.quantum.glossary#qubit)のデータを再生成する方法。</span><span class="sxs-lookup"><span data-stu-id="32813-234">A method for regenerating data, or the [quantum state](xref:microsoft.quantum.glossary#quantum-state), of one [qubit](xref:microsoft.quantum.glossary#qubit) from one place to another without physically moving the qubit, using [entanglement](xref:microsoft.quantum.glossary#entanglement) and [measurement](xref:microsoft.quantum.glossary#measurement).</span></span>  <span data-ttu-id="32813-235">詳細については、「クォンタム[回線](xref:microsoft.quantum.concepts.circuits)」と「 [quantum Katas](xref:microsoft.quantum.overview.katas)の各 kata」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-235">For more information, see [Quantum circuits](xref:microsoft.quantum.concepts.circuits) and the respective kata at [Quantum Katas](xref:microsoft.quantum.overview.katas).</span></span>

## <a name="tuple"></a><span data-ttu-id="32813-236">タプル</span><span class="sxs-lookup"><span data-stu-id="32813-236">Tuple</span></span>

<span data-ttu-id="32813-237">単一の値として機能するコンマ区切り値のコレクション。</span><span class="sxs-lookup"><span data-stu-id="32813-237">A collection of comma-separated values that acts as a single value.</span></span> <span data-ttu-id="32813-238">組の*型*は、その組に含まれる値の型によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="32813-238">The *type* of a tuple is defined by the types of values it contains.</span></span> <span data-ttu-id="32813-239">Q # では、タプルは[不変](xref:microsoft.quantum.glossary#immutable)であり、入れ子にしたり、配列を含めたり、配列で使用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="32813-239">In Q#, tuples are [immutable](xref:microsoft.quantum.glossary#immutable) and can be nested, contain arrays, or used in an array.</span></span> <span data-ttu-id="32813-240">詳細については、「[タプル型](xref:microsoft.quantum.guide.types#tuple-types)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-240">For more information, see [Tuple types](xref:microsoft.quantum.guide.types#tuple-types).</span></span>

## <a name="unitary-operator"></a><span data-ttu-id="32813-241">ユニタリ演算子</span><span class="sxs-lookup"><span data-stu-id="32813-241">Unitary operator</span></span>

<span data-ttu-id="32813-242">逆数が[adjoint](xref:microsoft.quantum.glossary#adjoint)と等しい (つまり、$UU ^ {\ ダガー } = \ id である) $ 演算子。</span><span class="sxs-lookup"><span data-stu-id="32813-242">An operator whose inverse is equal to its [adjoint](xref:microsoft.quantum.glossary#adjoint), i.e., $UU^{\dagger} = \id$.</span></span>

## <a name="user-defined-type"></a><span data-ttu-id="32813-243">ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="32813-243">User-defined type</span></span>

<span data-ttu-id="32813-244">1つの単位として参照される組み込み型または以前に定義された型のコレクション。</span><span class="sxs-lookup"><span data-stu-id="32813-244">A collection of built-in or previously defined types that may be referred to as a single unit.</span></span> <span data-ttu-id="32813-245">詳細については、「[ユーザー定義型](xref:microsoft.quantum.guide.types#user-defined-types)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32813-245">For more information, see [User-defined types](xref:microsoft.quantum.guide.types#user-defined-types).</span></span>