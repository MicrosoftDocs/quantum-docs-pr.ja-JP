---
title: QDK の組み込みの操作と関数
description: QDK の組み込みの操作と関数について説明します。これには、従来の関数、ユニタリ、ローテーション、測定演算が含まれます。
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: conceptual
uid: microsoft.quantum.libraries.standard.prelude
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6ed5b1677a204b9425f229a3ea0855bb789f3f75
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857182"
---
# <a name="the-prelude"></a><span data-ttu-id="35fad-103">準備</span><span class="sxs-lookup"><span data-stu-id="35fad-103">The Prelude</span></span> #

<span data-ttu-id="35fad-104">Q#クォンタム開発キットに含まれているコンパイラとターゲットコンピューターには、でクォンタムプログラムを記述するときに使用できる組み込み関数と操作のセットが用意されて Q# います。</span><span class="sxs-lookup"><span data-stu-id="35fad-104">The Q# compiler and the target machines included with the Quantum Development Kit provide a set of intrinsic functions and operations that can be used when writing quantum programs in Q#.</span></span>

## <a name="intrinsic-operations-and-functions"></a><span data-ttu-id="35fad-105">組み込みの操作と関数</span><span class="sxs-lookup"><span data-stu-id="35fad-105">Intrinsic Operations and Functions</span></span> ##

<span data-ttu-id="35fad-106">標準ライブラリで定義されている組み込み操作は、次のいずれかのカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="35fad-106">The intrinsic operations defined in the standard library roughly fall into one of several categories:</span></span>

- <span data-ttu-id="35fad-107">名前空間で収集される、基本的な従来の関数 <xref:Microsoft.Quantum.Core> 。</span><span class="sxs-lookup"><span data-stu-id="35fad-107">Essential classical functions, collected in the <xref:Microsoft.Quantum.Core> namespace.</span></span>
- <span data-ttu-id="35fad-108">[Clifford と $T $ ゲート](xref:microsoft.quantum.concepts.qubit)で構成される unitaries を表す操作。</span><span class="sxs-lookup"><span data-stu-id="35fad-108">Operations representing unitaries composed of [Clifford and $T$ gates](xref:microsoft.quantum.concepts.qubit).</span></span>
- <span data-ttu-id="35fad-109">さまざまな演算子についての回転を表す操作です。</span><span class="sxs-lookup"><span data-stu-id="35fad-109">Operations representing rotations about various operators.</span></span>
- <span data-ttu-id="35fad-110">測定を実装する操作。</span><span class="sxs-lookup"><span data-stu-id="35fad-110">Operations implementing measurements.</span></span>

<span data-ttu-id="35fad-111">Clifford + $T $ gate セットは、クォンタムコンピューティングでは [universal](xref:microsoft.quantum.concepts.multiple-qubits) であるため、これらの操作では negligibly 小規模エラーの中で、クォンタムアルゴリズムをほぼ実装することができます。</span><span class="sxs-lookup"><span data-stu-id="35fad-111">Since the Clifford + $T$ gate set is [universal](xref:microsoft.quantum.concepts.multiple-qubits) for quantum computing, these operations suffice to approximately implement any quantum algorithm within negligibly small error.</span></span>
<span data-ttu-id="35fad-112">また、回転も提供することにより、 Q# プログラマは単一の qubit のユニタリおよび CNOT gate ライブラリ内で作業できるようになります。</span><span class="sxs-lookup"><span data-stu-id="35fad-112">By providing rotations as well, Q# allows the programmer to work within the single qubit unitary and CNOT gate library.</span></span> <span data-ttu-id="35fad-113">このライブラリは、プログラマが Clifford + $T $ 分解を直接表現する必要がないため、また、1つの qubit unitaries を Clifford および $T $ ゲートにコンパイルするための非常に効率的なメソッドが存在するため、より簡単に考えることができます (詳細について [は、こちら](xref:microsoft.quantum.more-information) を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="35fad-113">This library is much easier to think about because it does not  require the programmer to directly express the Clifford + $T$ decomposition and because highly efficient methods exist for compiling single qubit unitaries into Clifford and $T$ gates (see [here](xref:microsoft.quantum.more-information) for more information).</span></span>

<span data-ttu-id="35fad-114">可能であれば、qubits で動作する準備に定義されている操作によって、 `Controlled` ターゲットコンピューターが適切な分解を実行するように、バリアントを適用できます。</span><span class="sxs-lookup"><span data-stu-id="35fad-114">Where possible, the operations defined in the prelude which act on qubits allow for applying the `Controlled` variant, such that the target machine will perform the appropriate decomposition.</span></span>

<span data-ttu-id="35fad-115">準備のこの部分で定義されている関数と操作の多くは @"microsoft.quantum.intrinsic" 名前空間にあります。そのため、ほとんどのソースファイルには、 Q# `open Microsoft.Quantum.Intrinsic;` 最初の名前空間宣言の直後にディレクティブがあります。</span><span class="sxs-lookup"><span data-stu-id="35fad-115">Many of the functions and operations defined in this portion of the prelude are in the @"microsoft.quantum.intrinsic" namespace, such that most Q# source files will have an `open Microsoft.Quantum.Intrinsic;` directive immediately following the initial namespace declaration.</span></span>
<span data-ttu-id="35fad-116"><xref:Microsoft.Quantum.Core>名前空間は自動的に開かれるため、などの関数を <xref:Microsoft.Quantum.Core.Length> ステートメントなしで使用することもでき `open` ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-116">The <xref:Microsoft.Quantum.Core> namespace is automatically opened, so that functions such as <xref:Microsoft.Quantum.Core.Length> can be used without an `open` statement at all.</span></span>

### <a name="common-single-qubit-unitary-operations"></a><span data-ttu-id="35fad-117">一般的な Single-Qubit の、ユニタリ操作</span><span class="sxs-lookup"><span data-stu-id="35fad-117">Common Single-Qubit Unitary Operations</span></span> ###

<span data-ttu-id="35fad-118">準備は、多くの一般的な [シングル qubit 操作](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)も定義します。</span><span class="sxs-lookup"><span data-stu-id="35fad-118">The prelude also defines many common [single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span></span>
<span data-ttu-id="35fad-119">これらの操作では、との両方の機能を使用でき `Controlled` `Adjoint` ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-119">All of these operations allow both the `Controlled` and `Adjoint` functors.</span></span>

#### <a name="pauli-operators"></a><span data-ttu-id="35fad-120">P# li 演算子</span><span class="sxs-lookup"><span data-stu-id="35fad-120">Pauli Operators</span></span> ####

<span data-ttu-id="35fad-121">操作は、 <xref:Microsoft.Quantum.Intrinsic.X> $X $ 演算子を実装します。</span><span class="sxs-lookup"><span data-stu-id="35fad-121">The <xref:Microsoft.Quantum.Intrinsic.X> operation implements the Pauli $X$ operator.</span></span>
<span data-ttu-id="35fad-122">これは、ゲートとも呼ばれ `NOT` ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-122">This is sometimes also known as the `NOT` gate.</span></span>
<span data-ttu-id="35fad-123">署名があり `(Qubit => Unit is Adj + Ctl)` ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-123">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="35fad-124">これは、単一の qubit のユニタリに対応します。</span><span class="sxs-lookup"><span data-stu-id="35fad-124">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="35fad-125">\begin{bmatrix} 0 & 1 \\ \\ % FIXME: 現在、quadwhack ハックを使用しています。</span><span class="sxs-lookup"><span data-stu-id="35fad-125">\begin{equation} \begin{bmatrix} 0 & 1 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="35fad-126">1 & 0 \end{bmatrix} です。</span><span class="sxs-lookup"><span data-stu-id="35fad-126">1 & 0 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="35fad-127">操作は、 <xref:Microsoft.Quantum.Intrinsic.Y> $Y $ 演算子を実装します。</span><span class="sxs-lookup"><span data-stu-id="35fad-127">The <xref:Microsoft.Quantum.Intrinsic.Y> operation implements the Pauli $Y$ operator.</span></span>
<span data-ttu-id="35fad-128">署名があり `(Qubit => Unit is Adj + Ctl)` ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-128">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="35fad-129">これは、単一の qubit のユニタリに対応します。</span><span class="sxs-lookup"><span data-stu-id="35fad-129">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="35fad-130">\begin{bmatrix} 0 &-i \\ \\ % FIXME: 現在、quadwhack ハックを使用しています。</span><span class="sxs-lookup"><span data-stu-id="35fad-130">\begin{equation} \begin{bmatrix} 0 & -i \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="35fad-131">i & 0 \end{bmatrix} です。</span><span class="sxs-lookup"><span data-stu-id="35fad-131">i & 0 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="35fad-132">操作は、 <xref:Microsoft.Quantum.Intrinsic.Z> $Z $ 演算子を実装します。</span><span class="sxs-lookup"><span data-stu-id="35fad-132">The <xref:Microsoft.Quantum.Intrinsic.Z> operation implements the Pauli $Z$ operator.</span></span>
<span data-ttu-id="35fad-133">署名があり `(Qubit => Unit is Adj + Ctl)` ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-133">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="35fad-134">これは、単一の qubit のユニタリに対応します。</span><span class="sxs-lookup"><span data-stu-id="35fad-134">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="35fad-135">\begin{bmatrix} 1 & 0 \\ \\ % FIXME: 現在、quadwhack ハックが使用されています。</span><span class="sxs-lookup"><span data-stu-id="35fad-135">\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="35fad-136">0 &-1 \end{bmatrix} です。</span><span class="sxs-lookup"><span data-stu-id="35fad-136">0 & -1 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="35fad-137">次の例では、これらの変換を [Bloch 球](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) にマップしています (各ケースの回転軸は赤で強調表示されています)。</span><span class="sxs-lookup"><span data-stu-id="35fad-137">Below we see these transformations mapped to the [Bloch sphere](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (the rotation axis in each case is highlighted red):</span></span>

![Bloch 球にマップされた p# li 操作](~/media/prelude_pauliBloch.png)

<span data-ttu-id="35fad-139">同じ PBloch Li ゲートを同じ qubit に2回適用することは、操作を取り消すことに注意してください (これにより、表面上で2π (360 °) の完全なローテーションが実行され、その結果、開始点に戻ります)。</span><span class="sxs-lookup"><span data-stu-id="35fad-139">It is important to note that applying the same Pauli gate twice to the same qubit cancels out the operation (because you have now performed a full rotation of 2π (360°) over the surface to the Bloch Sphere, thus arriving back at the starting point).</span></span> <span data-ttu-id="35fad-140">これにより、次の id が表示されます。</span><span class="sxs-lookup"><span data-stu-id="35fad-140">This brings us to the following identity:</span></span>

<span data-ttu-id="35fad-141">$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \ bold 完了 $ $</span><span class="sxs-lookup"><span data-stu-id="35fad-141">$$ X^2=Y^2=Z^2=\boldone $$</span></span>

<span data-ttu-id="35fad-142">これは、Bloch 球でビジュアルにすることができます。</span><span class="sxs-lookup"><span data-stu-id="35fad-142">This can be visualised on the Bloch sphere:</span></span>

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a><span data-ttu-id="35fad-144">その他の Single-Qubit Cliffords</span><span class="sxs-lookup"><span data-stu-id="35fad-144">Other Single-Qubit Cliffords</span></span> ####

<span data-ttu-id="35fad-145">操作は、 <xref:Microsoft.Quantum.Intrinsic.H> Hadamard ゲートを実装します。</span><span class="sxs-lookup"><span data-stu-id="35fad-145">The <xref:Microsoft.Quantum.Intrinsic.H> operation implements the Hadamard gate.</span></span>
<span data-ttu-id="35fad-146">このインターチェンジは、target qubit の P\ket Li $X $ 軸と $Z $ 軸を $H、 {0} \ket {0} + \ket {1} )/\ sqrt {2} $ と $H \ket{+} = \ket $ というように {0} なります。</span><span class="sxs-lookup"><span data-stu-id="35fad-146">This interchanges the Pauli $X$ and $Z$ axes of the target qubit, such that $H\ket{0} = \ket{+} \mathrel{:=} (\ket{0} + \ket{1}) / \sqrt{2}$ and $H\ket{+} = \ket{0}$.</span></span>
<span data-ttu-id="35fad-147">このファイルにはシグネチャがあり、 `(Qubit => Unit is Adj + Ctl)` 1 つの qubit の場合に対応します。</span><span class="sxs-lookup"><span data-stu-id="35fad-147">It has signature `(Qubit => Unit is Adj + Ctl)`, and corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="35fad-148">\ begin{FIXME}/frac {1} {\ sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ %: 現在、quadwhack ハックが使用されています。</span><span class="sxs-lookup"><span data-stu-id="35fad-148">\begin{equation} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="35fad-149">1 &-1 \end{bmatrix}/end{-1</span><span class="sxs-lookup"><span data-stu-id="35fad-149">1 & -1 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="35fad-150">Hadamard ゲートは、$ \ket {0} $ と $ \ket $ の状態の法則を作成するために使用できるため、特に重要です {1} 。</span><span class="sxs-lookup"><span data-stu-id="35fad-150">The Hadamard gate is particularly important as it can be used to create a superposition of the $\ket{0}$ and $\ket{1}$ states.</span></span> <span data-ttu-id="35fad-151">Bloch 球表現では、これは、$-pi $ ラジアン ($ 180 ^-circ $) によって x 軸を中心とした $ \ket{\psi} $ の回転で、$ pi/2 $ ラジアン ($ 90 ^-circ $) で y 軸を中心とする (時計回りの) 回転であると考えるのが最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="35fad-151">In the Bloch sphere representation, it is easiest to think of this as a rotation of $\ket{\psi}$ around the x-axis by $\pi$ radians ($180^\circ$) followed by a (clockwise) rotation around the y-axis by $\pi/2$ radians ($90^\circ$):</span></span>

![Bloch 球にマップされた Hadamard 操作](~/media/prelude_hadamardBloch.png)

<span data-ttu-id="35fad-153">操作は、 <xref:Microsoft.Quantum.Intrinsic.S> $ $S フェーズゲートを実装します。</span><span class="sxs-lookup"><span data-stu-id="35fad-153">The <xref:Microsoft.Quantum.Intrinsic.S> operation implements the phase gate $S$.</span></span>
<span data-ttu-id="35fad-154">これは、P# li $Z $ 操作の行列二乗ルートです。</span><span class="sxs-lookup"><span data-stu-id="35fad-154">This is the matrix square root of the Pauli $Z$ operation.</span></span>
<span data-ttu-id="35fad-155">つまり、$S ^ 2 = Z $ です。</span><span class="sxs-lookup"><span data-stu-id="35fad-155">That is, $S^2 = Z$.</span></span>
<span data-ttu-id="35fad-156">このファイルにはシグネチャがあり、 `(Qubit => Unit is Adj + Ctl)` 1 つの qubit の場合に対応します。</span><span class="sxs-lookup"><span data-stu-id="35fad-156">It has signature `(Qubit => Unit is Adj + Ctl)`, and corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="35fad-157">\begin{bmatrix} 1 & 0 \\ \\ % FIXME: 現在、quadwhack ハックが使用されています。</span><span class="sxs-lookup"><span data-stu-id="35fad-157">\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="35fad-158">0 & i \end{bmatrix} です。</span><span class="sxs-lookup"><span data-stu-id="35fad-158">0 & i \end{bmatrix} \end{equation}</span></span>

#### <a name="rotations"></a><span data-ttu-id="35fad-159">ローテーション</span><span class="sxs-lookup"><span data-stu-id="35fad-159">Rotations</span></span> ####

<span data-ttu-id="35fad-160">上記の P準備 Li および Clifford 操作に加えて、 Q# 回転を表現するさまざまな方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="35fad-160">In addition to the Pauli and Clifford operations above, the Q# prelude provides a variety of ways of expressing rotations.</span></span>
<span data-ttu-id="35fad-161">「 [シングル qubit 操作](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)」で説明されているように、ローテーションすることは、クォンタムアルゴリズムにとって重要です。</span><span class="sxs-lookup"><span data-stu-id="35fad-161">As described in [single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations), the ability to rotate is critical to quantum algorithms.</span></span>

<span data-ttu-id="35fad-162">最初に、$H $ と $T $ ゲートを使用して任意の1つの Hadamard 操作を表すことができることを呼び出します。ここで、$H $ は操作、where は \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ % FIXME: 現在は quad back たたくハックを使用します。</span><span class="sxs-lookup"><span data-stu-id="35fad-162">We start by recalling that we can express any single-qubit operation using the $H$ and $T$ gates, where $H$ is the Hadamard operation, and where \begin{equation} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quad back whack hack.</span></span>
<span data-ttu-id="35fad-163">0 & e^{i \pi / 4} \end{bmatrix} \end{equation} This is the square root of the <xref:Microsoft.Quantum.Intrinsic.S> operation, such that $T^2 = S$.</span><span class="sxs-lookup"><span data-stu-id="35fad-163">0 & e^{i \pi / 4} \end{bmatrix} \end{equation} This is the square root of the <xref:Microsoft.Quantum.Intrinsic.S> operation, such that $T^2 = S$.</span></span>
<span data-ttu-id="35fad-164">$T $ gate は、操作によって実装されてい <xref:Microsoft.Quantum.Intrinsic.T> `(Qubit => Unit is Adj + Ctl)` ます。また、このメソッドは、単一の qubit に対する1つのユニタリ操作であることを示すシグネチャを持っています。</span><span class="sxs-lookup"><span data-stu-id="35fad-164">The $T$ gate is in turn implemented by the <xref:Microsoft.Quantum.Intrinsic.T> operation, and has signature `(Qubit => Unit is Adj + Ctl)`, indicating that it is a unitary operation on a single-qubit.</span></span>

<span data-ttu-id="35fad-165">これは、任意のシングル qubit 操作を記述するのに十分な原則ですが、準備には、このような回転を実現するさまざまな方法が用意されているため、異なるターゲットコンピューターでは、Pauthentication Li 演算子についての回転をより効率的に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="35fad-165">Even though this is in principle sufficient to describe any arbitrary single-qubit operation, different target machines may have more efficient representations for rotations about Pauli operators, such that the prelude includes a variety of ways to convienently express such rotations.</span></span>
<span data-ttu-id="35fad-166">これらの最も基本的な操作は、 <xref:Microsoft.Quantum.Intrinsic.R> 指定された P# li 軸を中心とした回転を実装する操作です。 \mathrel{: =} \ exp (-i/phi/シグマ/2),、\ end{の場合は、$/シグマ $ は角度、$ \、$ $ $ exp $ は指数を表します。 $/を指定します (& a) (& a)。</span><span class="sxs-lookup"><span data-stu-id="35fad-166">The most basic of these is the <xref:Microsoft.Quantum.Intrinsic.R> operation, which implements a rotation around a specified Pauli axis, \begin{equation} R(\sigma, \phi) \mathrel{:=} \exp(-i \phi \sigma / 2), \end{equation} where $\sigma$ is a Pauli operator, $\phi$ is an angle, and where $\exp$ represents the matrix exponential.</span></span>
<span data-ttu-id="35fad-167">これにはシグネチャがあります `((Pauli, Double, Qubit) => Unit is Adj + Ctl)` 。ここで、入力の最初の2つの部分は、(-シグマ, + phi) $ という、ユニタリ演算子 $R を指定するために必要な従来の引数 $/シグマ $ と $ ¥ phi $ を表します。</span><span class="sxs-lookup"><span data-stu-id="35fad-167">It has signature `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`, where the first two parts of the input represent the classical arguments $\sigma$ and $\phi$ needed to specify the unitary operator $R(\sigma, \phi)$.</span></span>
<span data-ttu-id="35fad-168">$-シグマ $ と $/phi $ を部分的に適用して、1つの型が単一の qubit の読み込み操作を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="35fad-168">We can partially apply $\sigma$ and $\phi$ to obtain an operation whose type is that of a single-qubit unitary.</span></span>
<span data-ttu-id="35fad-169">たとえば、に `R(PauliZ, PI() / 4, _)` は型があり `(Qubit => Unit is Adj + Ctl)` ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-169">For example, `R(PauliZ, PI() / 4, _)` has type `(Qubit => Unit is Adj + Ctl)`.</span></span>

> [!NOTE]
> <span data-ttu-id="35fad-170">この操作では、 <xref:Microsoft.Quantum.Intrinsic.R> 入力角度を2で除算し、-1 で乗算します。</span><span class="sxs-lookup"><span data-stu-id="35fad-170">The <xref:Microsoft.Quantum.Intrinsic.R> operation divides the input angle by 2 and multiplies it by -1.</span></span>
> <span data-ttu-id="35fad-171">$Z $ ローテーションの場合、これは $ \ket {0} $ eigenstate が $--phi/$2 で回転し、$ \ket $ eigenstate が $/phi/$2 によってローテーションされることを意味し {1} ます。これにより、$ \ket $ eigenstate は $ {1} \ket {0} $ eigenstate に対して相対的に $/phi $ で</span><span class="sxs-lookup"><span data-stu-id="35fad-171">For $Z$ rotations, this means that the $\ket{0}$ eigenstate is rotated by $-\phi / 2$ and the $\ket{1}$ eigenstate is rotated by $\phi / 2$, so that the $\ket{1}$ eigenstate is rotated by $\phi$ relative to the $\ket{0}$ eigenstate.</span></span>
>
> <span data-ttu-id="35fad-172">特に、 `T` とは無関係な `R(PauliZ, PI() / 8, _)` [グローバルフェーズ](xref:microsoft.quantum.glossary#global-phase)によってのみ異なることを意味します。</span><span class="sxs-lookup"><span data-stu-id="35fad-172">In particular, this means that `T` and `R(PauliZ, PI() / 8, _)` differ only by an irrelevant [global phase](xref:microsoft.quantum.glossary#global-phase).</span></span>
> <span data-ttu-id="35fad-173">このため、$T $ は $ \frac{\pi} $-gate と呼ばれることもあり {8} ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-173">For this reason, $T$ is sometimes known as the $\frac{\pi}{8}$-gate.</span></span>
>
> <span data-ttu-id="35fad-174">また、回転によって `PauliI` 、単に $/phi/$2 のグローバルフェーズが適用されることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="35fad-174">Note also that rotating around `PauliI` simply applies a global phase of $\phi / 2$.</span></span> <span data-ttu-id="35fad-175">このようなフェーズは、 [概念的なドキュメント](xref:microsoft.quantum.concepts.qubit)の場合とは無関係ですが、制御された回転に関連し `PauliI` ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-175">While such phases are irrelevant, as argued in [the conceptual documents](xref:microsoft.quantum.concepts.qubit), they are relevant for controlled `PauliI` rotations.</span></span>

<span data-ttu-id="35fad-176">クォンタムアルゴリズムでは、多くの場合、\mathbb{Z} $ と \mathbb{N} $ での一部の $k \ に対して $-phi = \ pi k/2 ^ n $ $n というように、回転を dyadic の分数として表現すると便利です。</span><span class="sxs-lookup"><span data-stu-id="35fad-176">Within quantum algorithms, it is often useful to express rotations as dyadic fractions, such that $\phi = \pi k / 2^n$ for some $k \in \mathbb{Z}$ and $n \in \mathbb{N}$.</span></span>
<span data-ttu-id="35fad-177">操作は、 <xref:Microsoft.Quantum.Intrinsic.RFrac> この規則を使用して、指定された P# li 軸を中心とした回転を実装します。</span><span class="sxs-lookup"><span data-stu-id="35fad-177">The <xref:Microsoft.Quantum.Intrinsic.RFrac> operation implements a rotation around a specified Pauli axis using this convention.</span></span>
<span data-ttu-id="35fad-178">これは、 <xref:Microsoft.Quantum.Intrinsic.R> 回転角度が、 `Int` dyadic の割合として解釈される型の2つの入力として指定されている点で異なります。</span><span class="sxs-lookup"><span data-stu-id="35fad-178">It differs from <xref:Microsoft.Quantum.Intrinsic.R> in that the rotation angle is specified as two inputs of type `Int`, interpreted as a dyadic fraction.</span></span>
<span data-ttu-id="35fad-179">このため、に `RFrac` はシグネチャがあり `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)` ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-179">Thus, `RFrac` has signature `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="35fad-180">シングル qubit のユニタリ $ \ exp (i-pi k-シグマ/2 ^ n) $ を実装します。 $-シグマ $ は、最初の $k 引数に対応する Pforce Li 行列、$ は2番目の引数、$n $ は3番目の引数です。</span><span class="sxs-lookup"><span data-stu-id="35fad-180">It implements the single-qubit unitary $\exp(i \pi k \sigma / 2^n)$, where $\sigma$ is the Pauli matrix corresponding to the first argument, $k$ is the second argument, and $n$ is the third argument.</span></span>
<span data-ttu-id="35fad-181">`RFrac(_,k,n,_)` はと同じです。 `R(_,-πk/2^n,_)` 角度は分数の負の *値* であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="35fad-181">`RFrac(_,k,n,_)` is the same as `R(_,-πk/2^n,_)`; note that the angle is the *negative* of the fraction.</span></span>

<span data-ttu-id="35fad-182">操作は、 <xref:Microsoft.Quantum.Intrinsic.Rx> $X $ 軸に対する回転を実装します。</span><span class="sxs-lookup"><span data-stu-id="35fad-182">The <xref:Microsoft.Quantum.Intrinsic.Rx> operation implements a rotation around the Pauli $X$ axis.</span></span>
<span data-ttu-id="35fad-183">署名があり `((Double, Qubit) => Unit is Adj + Ctl)` ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-183">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="35fad-184">`Rx(_, _)` は `R(PauliX, _, _)` と同じです。</span><span class="sxs-lookup"><span data-stu-id="35fad-184">`Rx(_, _)` is the same as `R(PauliX, _, _)`.</span></span>

<span data-ttu-id="35fad-185">操作は、 <xref:Microsoft.Quantum.Intrinsic.Ry> $Y $ 軸に対する回転を実装します。</span><span class="sxs-lookup"><span data-stu-id="35fad-185">The <xref:Microsoft.Quantum.Intrinsic.Ry> operation implements a rotation around the Pauli $Y$ axis.</span></span>
<span data-ttu-id="35fad-186">署名があり `((Double, Qubit) => Unit is Adj + Ctl)` ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-186">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="35fad-187">`Ry(_, _)` は `R(PauliY,_ , _)` と同じです。</span><span class="sxs-lookup"><span data-stu-id="35fad-187">`Ry(_, _)` is the same as `R(PauliY,_ , _)`.</span></span>

<span data-ttu-id="35fad-188">操作は、 <xref:Microsoft.Quantum.Intrinsic.Rz> $Z $ 軸に対する回転を実装します。</span><span class="sxs-lookup"><span data-stu-id="35fad-188">The <xref:Microsoft.Quantum.Intrinsic.Rz> operation implements a rotation around the Pauli $Z$ axis.</span></span>
<span data-ttu-id="35fad-189">署名があり `((Double, Qubit) => Unit is Adj + Ctl)` ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-189">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="35fad-190">`Rz(_, _)` は `R(PauliZ, _, _)` と同じです。</span><span class="sxs-lookup"><span data-stu-id="35fad-190">`Rz(_, _)` is the same as `R(PauliZ, _, _)`.</span></span>

<span data-ttu-id="35fad-191">操作は、$ <xref:Microsoft.Quantum.Intrinsic.R1> \ket $ に対して指定された量の回転を実装し {1} ます。これは $Z $ の $-$1 eigenstate です。</span><span class="sxs-lookup"><span data-stu-id="35fad-191">The <xref:Microsoft.Quantum.Intrinsic.R1> operation implements a rotation by the given amount around $\ket{1}$, the $-1$ eigenstate of $Z$.</span></span>
<span data-ttu-id="35fad-192">署名があり `((Double, Qubit) => Unit is Adj + Ctl)` ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-192">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="35fad-193">`R1(phi,_)` は、の `R(PauliZ,phi,_)` 後に続くと同じです `R(PauliI,-phi,_)` 。</span><span class="sxs-lookup"><span data-stu-id="35fad-193">`R1(phi,_)` is the same as `R(PauliZ,phi,_)` followed by `R(PauliI,-phi,_)`.</span></span>

<span data-ttu-id="35fad-194">操作は、 <xref:Microsoft.Quantum.Intrinsic.R1Frac> Z = 1 eigenstate に対して指定された量だけ、小数部の回転を実装します。</span><span class="sxs-lookup"><span data-stu-id="35fad-194">The <xref:Microsoft.Quantum.Intrinsic.R1Frac> operation implements a fractional rotation by the given amount around the Z=1 eigenstate.</span></span>
<span data-ttu-id="35fad-195">署名があり `((Int,Int, Qubit) => Unit is Adj + Ctl)` ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-195">It has signature `((Int,Int, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="35fad-196">`R1Frac(k,n,_)` は、の `RFrac(PauliZ,-k.n+1,_)` 後に続くと同じです `RFrac(PauliI,k,n+1,_)` 。</span><span class="sxs-lookup"><span data-stu-id="35fad-196">`R1Frac(k,n,_)` is the same as `RFrac(PauliZ,-k.n+1,_)` followed by `RFrac(PauliI,k,n+1,_)`.</span></span>

<span data-ttu-id="35fad-197">Bloch 球にマップされた (このインスタンスの p Li $Z $ axis を中心とした) 回転操作の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="35fad-197">An example of a rotation operation (around the Pauli $Z$ axis, in this instance) mapped onto the Bloch sphere is shown below:</span></span>

![Bloch 球にマップされた回転操作](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a><span data-ttu-id="35fad-199">マルチ Qubit 操作</span><span class="sxs-lookup"><span data-stu-id="35fad-199">Multi-Qubit Operations</span></span> ####

<span data-ttu-id="35fad-200">準備では、上記のシングル qubit 操作に加えて、複数のマルチ qubit 操作も定義します。</span><span class="sxs-lookup"><span data-stu-id="35fad-200">In addition to the single-qubit operations above, the prelude also defines several multi-qubit operations.</span></span>

<span data-ttu-id="35fad-201">1つ目の操作では、標準の制御され <xref:Microsoft.Quantum.Intrinsic.CNOT> た `NOT` ゲート、& begin{\mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 & \\ \\ 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}. を実行します。</span><span class="sxs-lookup"><span data-stu-id="35fad-201">First, the <xref:Microsoft.Quantum.Intrinsic.CNOT> operation performs a standard controlled-`NOT` gate, \begin{equation} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}.</span></span>
<span data-ttu-id="35fad-202">\ end{eation} 署名が含ま `((Qubit, Qubit) => Unit is Adj + Ctl)` れています。これは、$-unitarily name{cnot} $ が2つの個別の qubits で動作することを表します。</span><span class="sxs-lookup"><span data-stu-id="35fad-202">\end{equation} It has signature `((Qubit, Qubit) => Unit is Adj + Ctl)`, representing that $\operatorname{CNOT}$ acts unitarily on two individual qubits.</span></span>
<span data-ttu-id="35fad-203">`CNOT(q1, q2)` は `(Controlled X)([q1], q2)` と同じです。</span><span class="sxs-lookup"><span data-stu-id="35fad-203">`CNOT(q1, q2)` is the same as `(Controlled X)([q1], q2)`.</span></span>
<span data-ttu-id="35fad-204">`Controlled`ファンクタではレジスタの制御が可能であるため、配列リテラルを使用して `[q1]` 、1つのコントロールのみが必要であることを示します。</span><span class="sxs-lookup"><span data-stu-id="35fad-204">Since the `Controlled` functor allows for controlling on a register, we use the array literal `[q1]` to indicate that we want only the one control.</span></span>

<span data-ttu-id="35fad-205">この <xref:Microsoft.Quantum.Intrinsic.CCNOT> 操作は、二重制御された NOT gate (Toffoli ゲートとも呼ばれます) を実行します。</span><span class="sxs-lookup"><span data-stu-id="35fad-205">The <xref:Microsoft.Quantum.Intrinsic.CCNOT> operation performs doubly-controlled NOT gate, sometimes also known as the Toffoli gate.</span></span>
<span data-ttu-id="35fad-206">署名があり `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)` ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-206">It has signature `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="35fad-207">`CCNOT(q1, q2, q3)` は `(Controlled X)([q1, q2], q3)` と同じです。</span><span class="sxs-lookup"><span data-stu-id="35fad-207">`CCNOT(q1, q2, q3)` is the same as `(Controlled X)([q1, q2], q3)`.</span></span>

<span data-ttu-id="35fad-208">操作は、 <xref:Microsoft.Quantum.Intrinsic.SWAP> 2 つの qubits のクォンタムの状態を交換します。</span><span class="sxs-lookup"><span data-stu-id="35fad-208">The <xref:Microsoft.Quantum.Intrinsic.SWAP> operation swaps the quantum states of two qubits.</span></span>
<span data-ttu-id="35fad-209">つまり、このメソッドは、ユニタリ行列を実装します。 \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 0 & \\ \\ 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{bmatrix}. です。</span><span class="sxs-lookup"><span data-stu-id="35fad-209">That is, it implements the unitary matrix \begin{equation} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}.</span></span>
<span data-ttu-id="35fad-210">(& a)、署名が含まれてい `((Qubit, Qubit) => Unit is Adj + Ctl)` ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-210">\end{equation} It has signature `((Qubit, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="35fad-211">`SWAP(q1,q2)` は `CNOT(q1, q2)` 、との後に続くと同じです `CNOT(q2, q1)` `CNOT(q1, q2)` 。</span><span class="sxs-lookup"><span data-stu-id="35fad-211">`SWAP(q1,q2)` is equivalent to `CNOT(q1, q2)` followed by `CNOT(q2, q1)` and then `CNOT(q1, q2)`.</span></span>

> [!NOTE]
> <span data-ttu-id="35fad-212">スワップゲートは、変数の要素を型で再配置するのと同じでは *ありません* `Qubit[]` 。</span><span class="sxs-lookup"><span data-stu-id="35fad-212">The SWAP gate is *not* the same as rearranging the elements of a variable with type `Qubit[]`.</span></span>
> <span data-ttu-id="35fad-213">を適用する `SWAP(q1, q2)` と、とによって参照される qubits の状態が変更されますが、は `q1` これらの `q2` `let swappedRegister = [q2, q1];` qubits を参照する方法にのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="35fad-213">Applying `SWAP(q1, q2)` causes a change to the state of the qubits referred to by `q1` and `q2`, while `let swappedRegister = [q2, q1];` only affects how we refer to those qubits.</span></span>
> <span data-ttu-id="35fad-214">さらに、は、 `(Controlled SWAP)([q0], (q1, q2))` `SWAP` 要素の並べ替えによっては表現できない3番目の qubit の状態に対して条件を設定できます。</span><span class="sxs-lookup"><span data-stu-id="35fad-214">Moreover, `(Controlled SWAP)([q0], (q1, q2))` allows for `SWAP` to be conditioned on the state of a third qubit, which we cannot represent by rearranging elements.</span></span>
> <span data-ttu-id="35fad-215">Fredkin gate とも呼ばれる、制御されたスワップゲートは、すべての従来の計算を含めるのに十分な性能を備えています。</span><span class="sxs-lookup"><span data-stu-id="35fad-215">The controlled-SWAP gate, also known as the Fredkin gate, is powerful enough to include all classical computation.</span></span>

<span data-ttu-id="35fad-216">最後に、準備には、マルチ qubit の指数演算子を表す2つの操作が用意されています。</span><span class="sxs-lookup"><span data-stu-id="35fad-216">Finally, the prelude provides two operations for representing exponentials of multi-qubit Pauli operators.</span></span>
<span data-ttu-id="35fad-217">この <xref:Microsoft.Quantum.Intrinsic.Exp> 操作は、複数の Pforce li マトリックスの製品に基づいて回転を実行します。これは、マルチ qubit の場合は、(-vec{/sigma}) によって表されます。 \ phi) \mathrel{: =} \ left (i/phi \ sigma_0/otimes \ sigma_1 \ sigma_n)、\ end{-& lt; & lt; & lt; & lt; & lt; & lt; & lt; & lt; & lt; & lt; & lt; $ & lt; sigma_0 \ sigma_1, \ ドット, \ sigma_n) $ は、single qubit の一連の演算子で、$ \ phi $ は角度を表します。</span><span class="sxs-lookup"><span data-stu-id="35fad-217">The <xref:Microsoft.Quantum.Intrinsic.Exp> operation performs a rotation based on a tensor product of Pauli matrices, as represented by the multi-qubit unitary \begin{equation} \operatorname{Exp}(\vec{\sigma}, \phi) \mathrel{:=} \exp\left(i \phi \sigma_0 \otimes \sigma_1 \otimes \cdots \otimes \sigma_n \right), \end{equation} where $\vec{\sigma} = (\sigma_0, \sigma_1, \dots, \sigma_n)$ is a sequence of single-qubit Pauli operators, and where $\phi$ is an angle.</span></span>
<span data-ttu-id="35fad-218">回転は、 `Exp` $ \ vec{-sigma} $ を要素の配列として表し `Pauli` 、署名があることを意味し `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-218">The `Exp` rotation represents $\vec{\sigma}$ as an array of `Pauli` elements, such that it has signature `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="35fad-219">操作は、 <xref:Microsoft.Quantum.Intrinsic.ExpFrac> 上記の dyadic の小数点表記を使用して、同じローテーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="35fad-219">The <xref:Microsoft.Quantum.Intrinsic.ExpFrac> operation performs the same rotation, using the dyadic fraction notation discussed above.</span></span>
<span data-ttu-id="35fad-220">署名があり `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)` ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-220">It has signature `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`.</span></span>

> [!WARNING]
> <span data-ttu-id="35fad-221">指数演算子のすべての操作は、指数または p Li オペレーターのの製品と同じではありません。</span><span class="sxs-lookup"><span data-stu-id="35fad-221">Exponentials of the tensor product of Pauli operators are not the same as tensor products of the exponentials of Pauli operators.</span></span>
> <span data-ttu-id="35fad-222">つまり、$e ^ {i (Z/otimes Z) \phi} \n e e ^ {i Z \phi}/otimes e ^ {i Z \phi} $。</span><span class="sxs-lookup"><span data-stu-id="35fad-222">That is, $e^{i (Z \otimes Z) \phi} \ne e^{i Z \phi} \otimes e^{i Z \phi}$.</span></span>

### <a name="measurements"></a><span data-ttu-id="35fad-223">測定</span><span class="sxs-lookup"><span data-stu-id="35fad-223">Measurements</span></span> ###

<span data-ttu-id="35fad-224">測定する場合、測定される演算子の + 1 eigenvalue は結果に対応 `Zero` し、-1 eigenvalue が結果になり `One` ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-224">When measuring, the +1 eigenvalue of the operator being measured corresponds to a `Zero` result, and the -1 eigenvalue to a `One` result.</span></span>

> [!NOTE]
> <span data-ttu-id="35fad-225">この規則は奇妙に見えるかもしれませんが、非常に便利な2つの利点があります。</span><span class="sxs-lookup"><span data-stu-id="35fad-225">While this convention might seem odd, it has two very nice advantages.</span></span>
> <span data-ttu-id="35fad-226">まず、$ \ket $ {0} `Result` を観察すると、$ `Zero` \ket $ が {1} に相当する値で表され `One` ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-226">First, observing the outcome $\ket{0}$ is represented by the `Result` value `Zero`, while observing $\ket{1}$ corresponds to `One`.</span></span>
> <span data-ttu-id="35fad-227">2つ目の方法として、結果に対応する eigenvalue $/ラムダ $ を、$ is $ \ ラムダ = (-1) ^ r $ という $r に記述できます。</span><span class="sxs-lookup"><span data-stu-id="35fad-227">Second, we can write out that the eigenvalue $\lambda$ corresponding to a result $r$ is $\lambda = (-1)^r$.</span></span>

<span data-ttu-id="35fad-228">測定演算では、もファンクタもサポートされて `Adjoint` `Controlled` いません。</span><span class="sxs-lookup"><span data-stu-id="35fad-228">Measurement operations support neither the `Adjoint` nor the `Controlled` functor.</span></span>

<span data-ttu-id="35fad-229">操作は、 <xref:Microsoft.Quantum.Intrinsic.Measure> 指定された P# li 演算子の積で1つ以上の qubits の結合測定を実行します。</span><span class="sxs-lookup"><span data-stu-id="35fad-229">The <xref:Microsoft.Quantum.Intrinsic.Measure> operation performs a joint measurement of one or more qubits in the specified product of Pauli operators.</span></span>
<span data-ttu-id="35fad-230">P# li 配列と qubit 配列の長さが異なる場合、操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="35fad-230">If the Pauli array and qubit array are different lengths, then the operation fails.</span></span>
<span data-ttu-id="35fad-231">`Measure` に署名があり `((Pauli[], Qubit[]) => Result)` ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-231">`Measure` has signature `((Pauli[], Qubit[]) => Result)`.</span></span>

<span data-ttu-id="35fad-232">ジョイント測定は、各 qubit を個別に測定するのと同じではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="35fad-232">Note that a joint measurement is not the same as measuring each qubit individually.</span></span>
<span data-ttu-id="35fad-233">たとえば、$ \ket {11} = \ket/ {1} otimes \Ket {1} = Xotimes X \ket $ という状態を考えてみ {00} ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-233">For example, consider the state $\ket{11} = \ket{1} \otimes \ket{1} = X\otimes X \ket{00}$.</span></span>
<span data-ttu-id="35fad-234">各 $Z 0 $ と $Z _1 $ を個別に測定すると、$r 0 = $1 および $r _1 = $1 の結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="35fad-234">Measuring $Z_0$ and $Z_1$ each individually, we get the results $r_0 = 1$ and $r_1 = 1$.</span></span>
<span data-ttu-id="35fad-235">$Z 0 Z_1 $ を測定すると、$ \ket $ の pairity が正であることを表す _ {\textrm{joint}} = $0 という1つの $r 結果が得られ {11} ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-235">Measuring $Z_0 Z_1$, however, we get the single result $r_{\textrm{joint}} = 0$, representing that the pairity of $\ket{11}$ is positive.</span></span>
<span data-ttu-id="35fad-236">異なる形式で、$ (-1) ^ {r_0 + r_1} = (-1) ^ r_ {\textrm{joint}}) $ と指定します。</span><span class="sxs-lookup"><span data-stu-id="35fad-236">Put differently, $(-1)^{r_0 + r_1} = (-1)^r_{\textrm{joint}})$.</span></span>
<span data-ttu-id="35fad-237">非常に大きなことですが、この測定からはパリティを学習する *だけ* なので、法則に示されている、正のパリティの 2 2-qubit の状態間のクォンタム情報 ($ \ket {00} $ と $ \ket {11} $) は保持されます。</span><span class="sxs-lookup"><span data-stu-id="35fad-237">Critically, since we *only* learn the parity from this measurement, any quantum information represented in the superposition between the two two-qubit states of positive parity, $\ket{00}$ and $\ket{11}$, is preserved.</span></span>
<span data-ttu-id="35fad-238">このプロパティは、エラー修正について説明するため、後で必要になります。</span><span class="sxs-lookup"><span data-stu-id="35fad-238">This property will be essential later, as we discuss error correction.</span></span>

<span data-ttu-id="35fad-239">便宜上、準備には、qubits を測定するための他の2つの操作も用意されています。</span><span class="sxs-lookup"><span data-stu-id="35fad-239">For convenience, the prelude also provides two other operations for measuring qubits.</span></span>
<span data-ttu-id="35fad-240">まず、single qubit の測定を実行するのは非常に一般的であるため、準備はこの場合の短縮形を定義します。</span><span class="sxs-lookup"><span data-stu-id="35fad-240">First, since performing single-qubit measurements is quite common, the prelude defines a shorthand for this case.</span></span>
<span data-ttu-id="35fad-241">この操作では、 <xref:Microsoft.Quantum.Intrinsic.M> 1 つの qubit に対して P# li $Z $ 演算子を測定し、シグネチャを持ち `(Qubit => Result)` ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-241">The <xref:Microsoft.Quantum.Intrinsic.M> operation measures the Pauli $Z$ operator on a single qubit, and has signature `(Qubit => Result)`.</span></span>
<span data-ttu-id="35fad-242">`M(q)` は `Measure([PauliZ], [q])` に相当します。</span><span class="sxs-lookup"><span data-stu-id="35fad-242">`M(q)` is equivalent to `Measure([PauliZ], [q])`.</span></span>

<span data-ttu-id="35fad-243">は、 <xref:Microsoft.Quantum.Measurement.MultiM> qubits の各配列で *個別* に $Z $ 演算子を測定し、qubits ごとに取得された値の *配列* を返し `Result` ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-243">The <xref:Microsoft.Quantum.Measurement.MultiM> measures the Pauli $Z$ operator *separately* on each of an array of qubits, returning the *array* of `Result` values obtained for each qubit.</span></span>
<span data-ttu-id="35fad-244">場合によっては、これを最適化することができます。</span><span class="sxs-lookup"><span data-stu-id="35fad-244">In some cases this can be optimized.</span></span> <span data-ttu-id="35fad-245">シグネチャ () があり `Qubit[] => Result[])` ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-245">It has signature (`Qubit[] => Result[])`.</span></span>
<span data-ttu-id="35fad-246">`MultiM(qs)` は、次の場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="35fad-246">`MultiM(qs)` is equivalent to:</span></span>

```qsharp
mutable rs = new Result[Length(qs)];
for (index in 0..Length(qs)-1)
{
    set rs[index] = M(qs[index]);
}
return rs;
```

## <a name="extension-functions-and-operations"></a><span data-ttu-id="35fad-247">拡張関数と操作</span><span class="sxs-lookup"><span data-stu-id="35fad-247">Extension Functions and Operations</span></span> ##

<span data-ttu-id="35fad-248">また、準備は、コード内で使用するために、.NET レベルで数学的および型変換関数の豊富なセットを定義し Q# ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-248">In addition, the prelude defines a rich set of mathematical and type conversion functions at the .NET level for use within Q# code.</span></span>
<span data-ttu-id="35fad-249">たとえば、名前空間は、やなどの <xref:Microsoft.Quantum.Math> 便利な操作を定義し <xref:Microsoft.Quantum.Math.Sin> <xref:Microsoft.Quantum.Math.Log> ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-249">For instance, the <xref:Microsoft.Quantum.Math> namespace defines useful operations such as <xref:Microsoft.Quantum.Math.Sin> and <xref:Microsoft.Quantum.Math.Log>.</span></span>
<span data-ttu-id="35fad-250">Quantum 開発キットによって提供される実装では、従来の .NET 基底クラスライブラリを使用します。そのため、quantum プログラムとその典型的なドライバーの間で、追加の通信ラウンドトリップが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="35fad-250">The implementation provided by the Quantum Development Kit uses the classical .NET base class library, and thus may involve an additional communications round trip between quantum programs and their classical drivers.</span></span>
<span data-ttu-id="35fad-251">これによってローカルシミュレーターに問題が発生することはありませんが、リモートシミュレーターまたは実際のハードウェアをターゲットコンピューターとして使用すると、パフォーマンスの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="35fad-251">While this does not present a problem for a local simulator, this can be a performance issue when using a remote simulator or actual hardware as a target machine.</span></span>
<span data-ttu-id="35fad-252">ただし、個々のターゲットコンピューターは、このような操作を特定のシステムにとってより効率的なバージョンで上書きすることによって、このパフォーマンスへの影響を軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="35fad-252">That said, an individual target machine may mitigate this performance impact by overriding these operations with versions that are more efficient for that particular system.</span></span>

### <a name="math"></a><span data-ttu-id="35fad-253">数値演算</span><span class="sxs-lookup"><span data-stu-id="35fad-253">Math</span></span> ###

<span data-ttu-id="35fad-254">名前空間には、 <xref:Microsoft.Quantum.Math> .net 基底クラスライブラリの[ `System.Math` クラス](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1&preserve-view=true)の便利な関数が多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="35fad-254">The <xref:Microsoft.Quantum.Math> namespace provides many useful functions from the .NET base class library's [`System.Math` class](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1&preserve-view=true).</span></span>
<span data-ttu-id="35fad-255">これらの関数は、他の関数と同じ方法で使用でき Q# ます。</span><span class="sxs-lookup"><span data-stu-id="35fad-255">These functions can be used in the same manner as any other Q# functions:</span></span>

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

<span data-ttu-id="35fad-256">.NET の静的メソッドが引数の型に基づいてオーバーロードされている場合、対応する Q# 関数には、入力の型を示すサフィックスで注釈が付けられます。</span><span class="sxs-lookup"><span data-stu-id="35fad-256">Where a .NET static method has been overloaded based on the type of its arguments, the corresponding Q# function is annotated with a suffix indicating the type of its input:</span></span>

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a><span data-ttu-id="35fad-257">ビットごとの演算</span><span class="sxs-lookup"><span data-stu-id="35fad-257">Bitwise Operations</span></span> ###

<span data-ttu-id="35fad-258">最後に、 <xref:Microsoft.Quantum.Bitwise> 名前空間には、ビットごとの演算子で整数を操作するための便利な関数がいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="35fad-258">Finally, the <xref:Microsoft.Quantum.Bitwise> namespace provides several useful functions for manipulating integers through bitwise operators.</span></span>
<span data-ttu-id="35fad-259">たとえば、は、 <xref:Microsoft.Quantum.Bitwise.Parity> 整数のビットごとのパリティを別の整数として返します。</span><span class="sxs-lookup"><span data-stu-id="35fad-259">For instance, <xref:Microsoft.Quantum.Bitwise.Parity> returns the bitwise parity of an integer as another integer.</span></span>
