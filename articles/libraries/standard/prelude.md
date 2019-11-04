---
title: 'Q # 標準ライブラリ-準備 |Microsoft Docs'
description: 'Q # 標準ライブラリ-準備'
author: QuantumWriter
uid: microsoft.quantum.libraries.standard.prelude
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: dddb3d4a5ebcdca16da41a5ae5520d98ea900a7f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73183235"
---
# <a name="the-prelude"></a><span data-ttu-id="3279f-103">準備</span><span class="sxs-lookup"><span data-stu-id="3279f-103">The Prelude</span></span> #

<span data-ttu-id="3279f-104">このクォンタム開発キットに含まれる Q # コンパイラとターゲットコンピューターには、Q # でクォンタムプログラムを記述するときに使用できる組み込み関数と操作のセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="3279f-104">The Q# compiler and the target machines included with the Quantum Development Kit provide a set of intrinsic functions and operations that can be used when writing quantum programs in Q#.</span></span>

## <a name="intrinsic-operations-and-functions"></a><span data-ttu-id="3279f-105">組み込みの操作と関数</span><span class="sxs-lookup"><span data-stu-id="3279f-105">Intrinsic Operations and Functions</span></span> ##

<span data-ttu-id="3279f-106">標準ライブラリで定義されている組み込み操作は、次のいずれかのカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="3279f-106">The intrinsic operations defined in the standard library roughly fall into one of several categories:</span></span>

- <span data-ttu-id="3279f-107"><xref:microsoft.quantum.core> 名前空間で収集される、重要なクラシック関数。</span><span class="sxs-lookup"><span data-stu-id="3279f-107">Essential classical functions, collected in the <xref:microsoft.quantum.core> namespace.</span></span>
- <span data-ttu-id="3279f-108">[Clifford と $T $ ゲート](xref:microsoft.quantum.concepts.qubit)で構成される unitaries を表す操作。</span><span class="sxs-lookup"><span data-stu-id="3279f-108">Operations representing unitaries composed of [Clifford and $T$ gates](xref:microsoft.quantum.concepts.qubit).</span></span>
- <span data-ttu-id="3279f-109">さまざまな演算子についての回転を表す操作です。</span><span class="sxs-lookup"><span data-stu-id="3279f-109">Operations representing rotations about various operators.</span></span>
- <span data-ttu-id="3279f-110">測定を実装する操作。</span><span class="sxs-lookup"><span data-stu-id="3279f-110">Operations implementing measurements.</span></span>

<span data-ttu-id="3279f-111">Clifford + $T $ gate セットは、クォンタムコンピューティングでは[universal](xref:microsoft.quantum.concepts.multiple-qubits)であるため、これらの操作では negligibly 小規模エラーの中で、クォンタムアルゴリズムをほぼ実装することができます。</span><span class="sxs-lookup"><span data-stu-id="3279f-111">Since the Clifford + $T$ gate set is [universal](xref:microsoft.quantum.concepts.multiple-qubits) for quantum computing, these operations suffice to approximately implement any quantum algorithm within negligibly small error.</span></span>
<span data-ttu-id="3279f-112">また、回転を提供することにより、プログラマは単一の qubit のユニタリおよび CNOT gate ライブラリ内で作業できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3279f-112">By providing rotations as well, Q# allows the programmer to work within the single qubit unitary and CNOT gate library.</span></span> <span data-ttu-id="3279f-113">このライブラリは、プログラマが Clifford + $T $ 分解を直接表現する必要がなく、1つの qubit unitaries を Clifford および $T $ ゲートにコンパイルするための非常に効率的なメソッドが存在するため、より簡単に考えることができます ([こちら](xref:microsoft.quantum.more-information)を参照してください)。を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="3279f-113">This library is much easier to think about because it does not  require the programmer to directly express the Clifford + $T$ decomposition and because highly efficient methods exist for compiling single qubit unitaries into Clifford and $T$ gates (see [here](xref:microsoft.quantum.more-information) for more information).</span></span>

<span data-ttu-id="3279f-114">可能であれば、qubits で動作する準備に定義されている操作によって、ターゲットコンピューターが適切な分解を実行するように `Controlled` variant を適用できます。</span><span class="sxs-lookup"><span data-stu-id="3279f-114">Where possible, the operations defined in the prelude which act on qubits allow for applying the `Controlled` variant, such that the target machine will perform the appropriate decomposition.</span></span>

<span data-ttu-id="3279f-115">準備のこの部分で定義されている関数と操作の多くは、@"microsoft.quantum.intrinsic" 名前空間にあります。そのため、ほとんどの Q # ソースファイルには、最初の名前空間宣言の直後にある `open Microsoft.Quantum.Intrinsic;` ディレクティブがあります。</span><span class="sxs-lookup"><span data-stu-id="3279f-115">Many of the functions and operations defined in this portion of the prelude are in the @"microsoft.quantum.intrinsic" namespace, such that most Q# source files will have an `open Microsoft.Quantum.Intrinsic;` directive immediately following the initial namespace declaration.</span></span>
<span data-ttu-id="3279f-116"><xref:microsoft.quantum.core> 名前空間が自動的に開かれるため、<xref:microsoft.quantum.core.length> などの関数は、`open` ステートメントをまったく使用せずに使用できます。</span><span class="sxs-lookup"><span data-stu-id="3279f-116">The <xref:microsoft.quantum.core> namespace is automatically opened, so that functions such as <xref:microsoft.quantum.core.length> can be used without an `open` statement at all.</span></span>

### <a name="common-single-qubit-unitary-operations"></a><span data-ttu-id="3279f-117">共通の単一 Qubit の解析操作</span><span class="sxs-lookup"><span data-stu-id="3279f-117">Common Single-Qubit Unitary Operations</span></span> ###

<span data-ttu-id="3279f-118">準備は、多くの一般的な[シングル qubit 操作](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)も定義します。</span><span class="sxs-lookup"><span data-stu-id="3279f-118">The prelude also defines many common [single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span></span>
<span data-ttu-id="3279f-119">これらの操作はすべて、`Controlled` と `Adjoint` の両方の機能を許可します。</span><span class="sxs-lookup"><span data-stu-id="3279f-119">All of these operations allow both the `Controlled` and `Adjoint` functors.</span></span>

#### <a name="pauli-operators"></a><span data-ttu-id="3279f-120">P# li 演算子</span><span class="sxs-lookup"><span data-stu-id="3279f-120">Pauli Operators</span></span> ####

<span data-ttu-id="3279f-121"><xref:microsoft.quantum.intrinsic.x> 操作は、p Li $X $ 演算子を実装します。</span><span class="sxs-lookup"><span data-stu-id="3279f-121">The <xref:microsoft.quantum.intrinsic.x> operation implements the Pauli $X$ operator.</span></span>
<span data-ttu-id="3279f-122">これは、`NOT` ゲートとも呼ばれることもあります。</span><span class="sxs-lookup"><span data-stu-id="3279f-122">This is sometimes also known as the `NOT` gate.</span></span>
<span data-ttu-id="3279f-123">署名には `(Qubit => Unit is Adj + Ctl)`があります。</span><span class="sxs-lookup"><span data-stu-id="3279f-123">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="3279f-124">これは、単一の qubit のユニタリに対応します。</span><span class="sxs-lookup"><span data-stu-id="3279f-124">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="3279f-125">\ begin{FIXME} \begin{bmatrix} 0 & 1 \\\\%: 現在、quadwhack ハックが使用されています。</span><span class="sxs-lookup"><span data-stu-id="3279f-125">\begin{equation} \begin{bmatrix} 0 & 1 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="3279f-126">1 & 0 \end{bmatrix} です。</span><span class="sxs-lookup"><span data-stu-id="3279f-126">1 & 0 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="3279f-127"><xref:microsoft.quantum.intrinsic.y> 操作は、p Li $Y $ 演算子を実装します。</span><span class="sxs-lookup"><span data-stu-id="3279f-127">The <xref:microsoft.quantum.intrinsic.y> operation implements the Pauli $Y$ operator.</span></span>
<span data-ttu-id="3279f-128">署名には `(Qubit => Unit is Adj + Ctl)`があります。</span><span class="sxs-lookup"><span data-stu-id="3279f-128">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="3279f-129">これは、単一の qubit のユニタリに対応します。</span><span class="sxs-lookup"><span data-stu-id="3279f-129">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="3279f-130">\ begin{FIXME} \begin{bmatrix} 0 &-i \\\\%: 現在、quadwhack ハックが使用されています。</span><span class="sxs-lookup"><span data-stu-id="3279f-130">\begin{equation} \begin{bmatrix} 0 & -i \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="3279f-131">i & 0 \end{bmatrix} です。</span><span class="sxs-lookup"><span data-stu-id="3279f-131">i & 0 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="3279f-132"><xref:microsoft.quantum.intrinsic.z> 操作は、p Li $Z $ 演算子を実装します。</span><span class="sxs-lookup"><span data-stu-id="3279f-132">The <xref:microsoft.quantum.intrinsic.z> operation implements the Pauli $Z$ operator.</span></span>
<span data-ttu-id="3279f-133">署名には `(Qubit => Unit is Adj + Ctl)`があります。</span><span class="sxs-lookup"><span data-stu-id="3279f-133">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="3279f-134">これは、単一の qubit のユニタリに対応します。</span><span class="sxs-lookup"><span data-stu-id="3279f-134">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="3279f-135">\ begin{FIXME} \begin{bmatrix} 1 & 0 \\\\%: 現在、quadwhack ハックが使用されています。</span><span class="sxs-lookup"><span data-stu-id="3279f-135">\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="3279f-136">0 &-1 \end{bmatrix} です。</span><span class="sxs-lookup"><span data-stu-id="3279f-136">0 & -1 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="3279f-137">次の例では、これらの変換を[Bloch 球](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere)にマップしています (各ケースの回転軸は赤で強調表示されています)。</span><span class="sxs-lookup"><span data-stu-id="3279f-137">Below we see these transformations mapped to the [Bloch sphere](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (the rotation axis in each case is highlighted red):</span></span>

![Bloch 球にマップされた p# li 操作](~/media/prelude_pauliBloch.png)

<span data-ttu-id="3279f-139">同じ PBloch Li ゲートを同じ qubit に2回適用することは、操作を取り消すことに注意してください (これにより、表面上で2π (360 °) の完全なローテーションが実行され、その結果、開始点に戻ります)。</span><span class="sxs-lookup"><span data-stu-id="3279f-139">It is important to note that applying the same Pauli gate twice to the same qubit cancels out the operation (because you have now performed a full rotation of 2π (360°) over the surface to the Bloch Sphere, thus arriving back at the starting point).</span></span> <span data-ttu-id="3279f-140">これにより、次の id が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3279f-140">This brings us to the following identity:</span></span>

<span data-ttu-id="3279f-141">$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \ bold 完了 $ $</span><span class="sxs-lookup"><span data-stu-id="3279f-141">$$ X^2=Y^2=Z^2=\boldone $$</span></span>

<span data-ttu-id="3279f-142">これは、Bloch 球でビジュアルにすることができます。</span><span class="sxs-lookup"><span data-stu-id="3279f-142">This can be visualised on the Bloch sphere:</span></span>

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a><span data-ttu-id="3279f-144">その他のシングル Qubit Cliffords</span><span class="sxs-lookup"><span data-stu-id="3279f-144">Other Single-Qubit Cliffords</span></span> ####

<span data-ttu-id="3279f-145"><xref:microsoft.quantum.intrinsic.h> 操作は、Hadamard ゲートを実装します。</span><span class="sxs-lookup"><span data-stu-id="3279f-145">The <xref:microsoft.quantum.intrinsic.h> operation implements the Hadamard gate.</span></span>
<span data-ttu-id="3279f-146">このインターチェンジでは、ターゲットの qubit の P\ket Li $X $ 軸と $Z $ 軸が $H{0} = \ket{+} \mathrel{: =} (\ket{0} + \ket{1})/\ sqrt{2}$ および $H \ket{+} = \ket{0}$ となります。</span><span class="sxs-lookup"><span data-stu-id="3279f-146">This interchanges the Pauli $X$ and $Z$ axes of the target qubit, such that $H\ket{0} = \ket{+} \mathrel{:=} (\ket{0} + \ket{1}) / \sqrt{2}$ and $H\ket{+} = \ket{0}$.</span></span>
<span data-ttu-id="3279f-147">シグネチャは `(Qubit => Unit is Adj + Ctl)`であり、単一の qubit の場合に対応します。</span><span class="sxs-lookup"><span data-stu-id="3279f-147">It has signature `(Qubit => Unit is Adj + Ctl)`, and corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="3279f-148">\ begin{FIXME}/frac{1}{\ sqrt{2}} \begin{bmatrix} 1 & 1 \\\\%: 現在、quadwhack ハックが使用されています。</span><span class="sxs-lookup"><span data-stu-id="3279f-148">\begin{equation} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="3279f-149">1 &-1 \end{bmatrix}/end{-1</span><span class="sxs-lookup"><span data-stu-id="3279f-149">1 & -1 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="3279f-150">Hadamard ゲートは、$ \ket{0}$ と $ \ket{1}$ states の法則を作成するために使用できるため、特に重要です。</span><span class="sxs-lookup"><span data-stu-id="3279f-150">The Hadamard gate is particularly important as it can be used to create a superposition of the $\ket{0}$ and $\ket{1}$ states.</span></span> <span data-ttu-id="3279f-151">Bloch 球表現では、これは、$-pi $ ラジアン ($ 180 ^-circ $) によって x 軸を中心とした $ \ket{\psi} $ の回転で、$ pi/2 $ ラジアン ($ 90 ^-circ $) で y 軸を中心とする (時計回りの) 回転であると考えるのが最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="3279f-151">In the Bloch sphere representation, it is easiest to think of this as a rotation of $\ket{\psi}$ around the x-axis by $\pi$ radians ($180^\circ$) followed by a (clockwise) rotation around the y-axis by $\pi/2$ radians ($90^\circ$):</span></span>

![Bloch 球にマップされた Hadamard 操作](~/media/prelude_hadamardBloch.png)

<span data-ttu-id="3279f-153"><xref:microsoft.quantum.intrinsic.s> 操作は、$ $S フェーズゲートを実装します。</span><span class="sxs-lookup"><span data-stu-id="3279f-153">The <xref:microsoft.quantum.intrinsic.s> operation implements the phase gate $S$.</span></span>
<span data-ttu-id="3279f-154">これは、P# li $Z $ 操作の行列二乗ルートです。</span><span class="sxs-lookup"><span data-stu-id="3279f-154">This is the matrix square root of the Pauli $Z$ operation.</span></span>
<span data-ttu-id="3279f-155">つまり、$S ^ 2 = Z $ です。</span><span class="sxs-lookup"><span data-stu-id="3279f-155">That is, $S^2 = Z$.</span></span>
<span data-ttu-id="3279f-156">シグネチャは `(Qubit => Unit is Adj + Ctl)`であり、単一の qubit の場合に対応します。</span><span class="sxs-lookup"><span data-stu-id="3279f-156">It has signature `(Qubit => Unit is Adj + Ctl)`, and corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="3279f-157">\ begin{FIXME} \begin{bmatrix} 1 & 0 \\\\%: 現在、quadwhack ハックが使用されています。</span><span class="sxs-lookup"><span data-stu-id="3279f-157">\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="3279f-158">0 & i \end{bmatrix} です。</span><span class="sxs-lookup"><span data-stu-id="3279f-158">0 & i \end{bmatrix} \end{equation}</span></span>

#### <a name="rotations"></a><span data-ttu-id="3279f-159">中心</span><span class="sxs-lookup"><span data-stu-id="3279f-159">Rotations</span></span> ####

<span data-ttu-id="3279f-160">上記の P準備 Li および Clifford 操作に加えて、Q # のには、回転を表すさまざまな方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="3279f-160">In addition to the Pauli and Clifford operations above, the Q# prelude provides a variety of ways of expressing rotations.</span></span>
<span data-ttu-id="3279f-161">「[シングル qubit 操作](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)」で説明されているように、ローテーションすることは、クォンタムアルゴリズムにとって重要です。</span><span class="sxs-lookup"><span data-stu-id="3279f-161">As described in [single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations), the ability to rotate is critical to quantum algorithms.</span></span>

<span data-ttu-id="3279f-162">最初に、$H $ と $T $ ゲートを使用して任意の1つのシングル qubit 操作を表すことができることを呼び出します。ここで、$H $ は Hadamard 操作、where は \mathrel{: =} \begin{bmatrix} 1 & 0 \\\\% FIXME: 現在はクワッドバックを使用します。たたくハック。</span><span class="sxs-lookup"><span data-stu-id="3279f-162">We start by recalling that we can express any single-qubit operation using the $H$ and $T$ gates, where $H$ is the Hadamard operation, and where \begin{equation} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quad back whack hack.</span></span>
<span data-ttu-id="3279f-163">0 & e ^ {i \ pi/4} \end{bmatrix} です。これは、$T ^ 2 = S $ のような <xref:microsoft.quantum.intrinsic.s> 操作の平方根です。</span><span class="sxs-lookup"><span data-stu-id="3279f-163">0 & e^{i \pi / 4} \end{bmatrix} \end{equation} This is the square root of the <xref:microsoft.quantum.intrinsic.s> operation, such that $T^2 = S$.</span></span>
<span data-ttu-id="3279f-164">$T $ gate は、<xref:microsoft.quantum.intrinsic.t> 操作によって実装されています。また、`(Qubit => Unit is Adj + Ctl)`シグネチャがあります。これは、これが単一の qubit に対する1回の処理であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="3279f-164">The $T$ gate is in turn implemented by the <xref:microsoft.quantum.intrinsic.t> operation, and has signature `(Qubit => Unit is Adj + Ctl)`, indicating that it is a unitary operation on a single-qubit.</span></span>

<span data-ttu-id="3279f-165">これは、任意のシングル qubit 操作を記述するのに十分な原理ですが、準備にはさまざまな方法があるため、さまざまなターゲットマシンで Pauthentication Li 演算子についての回転をより効率的に行うことができます。このような回転を高速にします。</span><span class="sxs-lookup"><span data-stu-id="3279f-165">Even though this is in principle sufficient to describe any arbitrary single-qubit operation, different target machines may have more efficient representations for rotations about Pauli operators, such that the prelude includes a variety of ways to convienently express such rotations.</span></span>
<span data-ttu-id="3279f-166">これらの最も基本的な操作は、<xref:microsoft.quantum.intrinsic.r> 操作です。指定された P\mathrel{の軸の周りの回転を実装する、\ begin{? ation} R (-σ、\ phi): =} \ exp (-i/phi/シグマ/2)、\ end{の場合は、$/シグマ $ は、角度、$、および $\ exp $ は、行列指数を表します。</span><span class="sxs-lookup"><span data-stu-id="3279f-166">The most basic of these is the <xref:microsoft.quantum.intrinsic.r> operation, which implements a rotation around a specified Pauli axis, \begin{equation} R(\sigma, \phi) \mathrel{:=} \exp(-i \phi \sigma / 2), \end{equation} where $\sigma$ is a Pauli operator, $\phi$ is an angle, and where $\exp$ represents the matrix exponential.</span></span>
<span data-ttu-id="3279f-167">これには `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`のシグネチャがあります。ここで、入力の最初の2つの部分は、$R (-シグマ, \ phi) $ のように、最も前の引数 $-シグマ $ と $/phi $ を表します。</span><span class="sxs-lookup"><span data-stu-id="3279f-167">It has signature `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`, where the first two parts of the input represent the classical arguments $\sigma$ and $\phi$ needed to specify the unitary operator $R(\sigma, \phi)$.</span></span>
<span data-ttu-id="3279f-168">$-シグマ $ と $/phi $ を部分的に適用して、1つの型が単一の qubit の読み込み操作を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="3279f-168">We can partially apply $\sigma$ and $\phi$ to obtain an operation whose type is that of a single-qubit unitary.</span></span>
<span data-ttu-id="3279f-169">たとえば、`R(PauliZ, PI() / 4, _)` には `(Qubit => Unit is Adj + Ctl)`型があります。</span><span class="sxs-lookup"><span data-stu-id="3279f-169">For example, `R(PauliZ, PI() / 4, _)` has type `(Qubit => Unit is Adj + Ctl)`.</span></span>

> [!NOTE]
> <span data-ttu-id="3279f-170"><xref:microsoft.quantum.intrinsic.r> 操作では、入力角度を2で除算し、-1 で乗算します。</span><span class="sxs-lookup"><span data-stu-id="3279f-170">The <xref:microsoft.quantum.intrinsic.r> operation divides the input angle by 2 and multiplies it by -1.</span></span>
> <span data-ttu-id="3279f-171">$Z $ ローテーションでは、$ \ket{0}$ eigenstate が $--phi/{1}$2 によって回転され、$ \ket{1}$ eigenstate が $/phi/$2 によって回転されます。これにより、$ $ eigenstate が $ \ket{0}$ eigenstate に対して相対的に $/phi $</span><span class="sxs-lookup"><span data-stu-id="3279f-171">For $Z$ rotations, this means that the $\ket{0}$ eigenstate is rotated by $-\phi / 2$ and the $\ket{1}$ eigenstate is rotated by $\phi / 2$, so that the $\ket{1}$ eigenstate is rotated by $\phi$ relative to the $\ket{0}$ eigenstate.</span></span>
>
> <span data-ttu-id="3279f-172">特に、`T` と `R(PauliZ, PI() / 8, _)` は、無関係の[グローバルフェーズ](xref:microsoft.quantum.glossary#global-phase)によってのみ異なることを意味します。</span><span class="sxs-lookup"><span data-stu-id="3279f-172">In particular, this means that `T` and `R(PauliZ, PI() / 8, _)` differ only by an irrelevant [global phase](xref:microsoft.quantum.glossary#global-phase).</span></span>
> <span data-ttu-id="3279f-173">このため、$T $ は $ \frac{\pi}{8}$-gate とも呼ばれることがあります。</span><span class="sxs-lookup"><span data-stu-id="3279f-173">For this reason, $T$ is sometimes known as the $\frac{\pi}{8}$-gate.</span></span>
>
> <span data-ttu-id="3279f-174">また、`PauliI` を回転させると、単純に $-phi/$2 のグローバルフェーズが適用されることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="3279f-174">Note also that rotating around `PauliI` simply applies a global phase of $\phi / 2$.</span></span> <span data-ttu-id="3279f-175">このようなフェーズは関係ありませんが、[概念ドキュメント](xref:microsoft.quantum.concepts.qubit)では、制御された `PauliI` のローテーションに関連します。</span><span class="sxs-lookup"><span data-stu-id="3279f-175">While such phases are irrelevant, as argued in [the conceptual documents](xref:microsoft.quantum.concepts.qubit), they are relevant for controlled `PauliI` rotations.</span></span>

<span data-ttu-id="3279f-176">クォンタムアルゴリズムでは、多くの場合、\mathbb{Z} $ と \mathbb{N} $ での一部の $k \ に対して $-phi = \ pi k/2 ^ n $ $n というように、回転を dyadic の分数として表現すると便利です。</span><span class="sxs-lookup"><span data-stu-id="3279f-176">Within quantum algorithms, it is often useful to express rotations as dyadic fractions, such that $\phi = \pi k / 2^n$ for some $k \in \mathbb{Z}$ and $n \in \mathbb{N}$.</span></span>
<span data-ttu-id="3279f-177"><xref:microsoft.quantum.intrinsic.rfrac> 操作では、この規則を使用して、指定した P# li 軸の周りの回転を実装します。</span><span class="sxs-lookup"><span data-stu-id="3279f-177">The <xref:microsoft.quantum.intrinsic.rfrac> operation implements a rotation around a specified Pauli axis using this convention.</span></span>
<span data-ttu-id="3279f-178">これは、回転角度が `Int`型の2つの入力として指定され、dyadic の分数として解釈されるという点で <xref:microsoft.quantum.intrinsic.r> とは異なります。</span><span class="sxs-lookup"><span data-stu-id="3279f-178">It differs from <xref:microsoft.quantum.intrinsic.r> in that the rotation angle is specified as two inputs of type `Int`, interpreted as a dyadic fraction.</span></span>
<span data-ttu-id="3279f-179">したがって、`RFrac` には `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`シグネチャがあります。</span><span class="sxs-lookup"><span data-stu-id="3279f-179">Thus, `RFrac` has signature `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="3279f-180">シングル qubit のユニタリ $ \ exp (i-pi k-シグマ/2 ^ n) $ を実装します。 $-シグマ $ は、最初の $k 引数に対応する Pforce Li 行列、$ は2番目の引数、$n $ は3番目の引数です。</span><span class="sxs-lookup"><span data-stu-id="3279f-180">It implements the single-qubit unitary $\exp(i \pi k \sigma / 2^n)$, where $\sigma$ is the Pauli matrix corresponding to the first argument, $k$ is the second argument, and $n$ is the third argument.</span></span>
<span data-ttu-id="3279f-181">`RFrac(_,k,n,_)` は `R(_,-πk/2^n,_)`と同じです。角度は、分数の*負の値*であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3279f-181">`RFrac(_,k,n,_)` is the same as `R(_,-πk/2^n,_)`; note that the angle is the *negative* of the fraction.</span></span>

<span data-ttu-id="3279f-182"><xref:microsoft.quantum.intrinsic.rx> 操作は、$X $ 軸を中心とした回転を実装します。</span><span class="sxs-lookup"><span data-stu-id="3279f-182">The <xref:microsoft.quantum.intrinsic.rx> operation implements a rotation around the Pauli $X$ axis.</span></span>
<span data-ttu-id="3279f-183">署名には `((Double, Qubit) => Unit is Adj + Ctl)`があります。</span><span class="sxs-lookup"><span data-stu-id="3279f-183">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="3279f-184">`Rx(_, _)` は `R(PauliX, _, _)`と同じです。</span><span class="sxs-lookup"><span data-stu-id="3279f-184">`Rx(_, _)` is the same as `R(PauliX, _, _)`.</span></span>

<span data-ttu-id="3279f-185"><xref:microsoft.quantum.intrinsic.ry> 操作は、$Y $ 軸を中心とした回転を実装します。</span><span class="sxs-lookup"><span data-stu-id="3279f-185">The <xref:microsoft.quantum.intrinsic.ry> operation implements a rotation around the Pauli $Y$ axis.</span></span>
<span data-ttu-id="3279f-186">署名には `((Double, Qubit) => Unit is Adj + Ctl)`があります。</span><span class="sxs-lookup"><span data-stu-id="3279f-186">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="3279f-187">`Ry(_, _)` は `R(PauliY,_ , _)`と同じです。</span><span class="sxs-lookup"><span data-stu-id="3279f-187">`Ry(_, _)` is the same as `R(PauliY,_ , _)`.</span></span>

<span data-ttu-id="3279f-188"><xref:microsoft.quantum.intrinsic.rz> 操作は、$Z $ 軸を中心とした回転を実装します。</span><span class="sxs-lookup"><span data-stu-id="3279f-188">The <xref:microsoft.quantum.intrinsic.rz> operation implements a rotation around the Pauli $Z$ axis.</span></span>
<span data-ttu-id="3279f-189">署名には `((Double, Qubit) => Unit is Adj + Ctl)`があります。</span><span class="sxs-lookup"><span data-stu-id="3279f-189">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="3279f-190">`Rz(_, _)` は `R(PauliZ, _, _)`と同じです。</span><span class="sxs-lookup"><span data-stu-id="3279f-190">`Rz(_, _)` is the same as `R(PauliZ, _, _)`.</span></span>

<span data-ttu-id="3279f-191"><xref:microsoft.quantum.intrinsic.r1> 操作では、$ \ket{1}$ の $Z $-$1 eigenstate を中心に、指定された量の回転を実装します。</span><span class="sxs-lookup"><span data-stu-id="3279f-191">The <xref:microsoft.quantum.intrinsic.r1> operation implements a rotation by the given amount around $\ket{1}$, the $-1$ eigenstate of $Z$.</span></span>
<span data-ttu-id="3279f-192">署名には `((Double, Qubit) => Unit is Adj + Ctl)`があります。</span><span class="sxs-lookup"><span data-stu-id="3279f-192">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="3279f-193">`R1(phi,_)` は `R(PauliZ,phi,_)` の後に続く `R(PauliI,-phi,_)`と同じです。</span><span class="sxs-lookup"><span data-stu-id="3279f-193">`R1(phi,_)` is the same as `R(PauliZ,phi,_)` followed by `R(PauliI,-phi,_)`.</span></span>

<span data-ttu-id="3279f-194"><xref:microsoft.quantum.intrinsic.r1frac> 操作は、Z = 1 eigenstate に対して指定された量だけ、小数部の回転を実装します。</span><span class="sxs-lookup"><span data-stu-id="3279f-194">The <xref:microsoft.quantum.intrinsic.r1frac> operation implements a fractional rotation by the given amount around the Z=1 eigenstate.</span></span>
<span data-ttu-id="3279f-195">署名には `((Int,Int, Qubit) => Unit is Adj + Ctl)`があります。</span><span class="sxs-lookup"><span data-stu-id="3279f-195">It has signature `((Int,Int, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="3279f-196">`R1Frac(k,n,_)` は `RFrac(PauliZ,-k.n+1,_)` の後に続く `RFrac(PauliI,k,n+1,_)`と同じです。</span><span class="sxs-lookup"><span data-stu-id="3279f-196">`R1Frac(k,n,_)` is the same as `RFrac(PauliZ,-k.n+1,_)` followed by `RFrac(PauliI,k,n+1,_)`.</span></span>

<span data-ttu-id="3279f-197">Bloch 球にマップされた (このインスタンスの p Li $Z $ axis を中心とした) 回転操作の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3279f-197">An example of a rotation operation (around the Pauli $Z$ axis, in this instance) mapped onto the Bloch sphere is shown below:</span></span>

![Bloch 球にマップされた回転操作](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a><span data-ttu-id="3279f-199">マルチ Qubit 操作</span><span class="sxs-lookup"><span data-stu-id="3279f-199">Multi-Qubit Operations</span></span> ####

<span data-ttu-id="3279f-200">準備では、上記のシングル qubit 操作に加えて、複数のマルチ qubit 操作も定義します。</span><span class="sxs-lookup"><span data-stu-id="3279f-200">In addition to the single-qubit operations above, the prelude also defines several multi-qubit operations.</span></span>

<span data-ttu-id="3279f-201">最初に、<xref:microsoft.quantum.intrinsic.cnot> 操作は、標準の制御された`NOT` ゲート \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 を実行しています。\\\\ 0 & 0 & 1 & 0 \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="3279f-201">First, the <xref:microsoft.quantum.intrinsic.cnot> operation performs a standard controlled-`NOT` gate, \begin{equation} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}.</span></span>
<span data-ttu-id="3279f-202">& # {unitarily} には、`((Qubit, Qubit) => Unit is Adj + Ctl)`シグネチャがあります。これは、$-name{cnot} $ が2つの個別の qubits で動作することを表します。</span><span class="sxs-lookup"><span data-stu-id="3279f-202">\end{equation} It has signature `((Qubit, Qubit) => Unit is Adj + Ctl)`, representing that $\operatorname{CNOT}$ acts unitarily on two individual qubits.</span></span>
<span data-ttu-id="3279f-203">`CNOT(q1, q2)` は `(Controlled X)([q1], q2)`と同じです。</span><span class="sxs-lookup"><span data-stu-id="3279f-203">`CNOT(q1, q2)` is the same as `(Controlled X)([q1], q2)`.</span></span>
<span data-ttu-id="3279f-204">`Controlled` のファンクタではレジスタの制御が可能であるため、配列リテラル `[q1]` を使用して、1つのコントロールのみが必要であることを示します。</span><span class="sxs-lookup"><span data-stu-id="3279f-204">Since the `Controlled` functor allows for controlling on a register, we use the array literal `[q1]` to indicate that we want only the one control.</span></span>

<span data-ttu-id="3279f-205"><xref:microsoft.quantum.intrinsic.ccnot> 操作では、二重制御された NOT gate (Toffoli ゲートとも呼ばれます) を実行します。</span><span class="sxs-lookup"><span data-stu-id="3279f-205">The <xref:microsoft.quantum.intrinsic.ccnot> operation performs doubly-controlled NOT gate, sometimes also known as the Toffoli gate.</span></span>
<span data-ttu-id="3279f-206">署名には `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`があります。</span><span class="sxs-lookup"><span data-stu-id="3279f-206">It has signature `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="3279f-207">`CCNOT(q1, q2, q3)` は `(Controlled X)([q1, q2], q3)`と同じです。</span><span class="sxs-lookup"><span data-stu-id="3279f-207">`CCNOT(q1, q2, q3)` is the same as `(Controlled X)([q1, q2], q3)`.</span></span>

<span data-ttu-id="3279f-208"><xref:microsoft.quantum.intrinsic.swap> 操作は、2つの qubits のクォンタム状態を交換します。</span><span class="sxs-lookup"><span data-stu-id="3279f-208">The <xref:microsoft.quantum.intrinsic.swap> operation swaps the quantum states of two qubits.</span></span>
<span data-ttu-id="3279f-209">つまり、このメソッドは、ユニタリ行列を実装します。 \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 になり &0 & 0 & 1 \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="3279f-209">That is, it implements the unitary matrix \begin{equation} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}.</span></span>
<span data-ttu-id="3279f-210">& end{の場合は、署名 `((Qubit, Qubit) => Unit is Adj + Ctl)`ます。</span><span class="sxs-lookup"><span data-stu-id="3279f-210">\end{equation} It has signature `((Qubit, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="3279f-211">`SWAP(q1,q2)` は、`CNOT(q1, q2)` の後に `CNOT(q2, q1)` を付けてから `CNOT(q1, q2)`することと同じです。</span><span class="sxs-lookup"><span data-stu-id="3279f-211">`SWAP(q1,q2)` is equivalent to `CNOT(q1, q2)` followed by `CNOT(q2, q1)` and then `CNOT(q1, q2)`.</span></span>

> [!NOTE]
> <span data-ttu-id="3279f-212">スワップゲートは、変数の要素を `Qubit[]`型で再配置するのと同じでは*ありません*。</span><span class="sxs-lookup"><span data-stu-id="3279f-212">The SWAP gate is *not* the same as rearranging the elements of a variable with type `Qubit[]`.</span></span>
> <span data-ttu-id="3279f-213">`SWAP(q1, q2)` を適用すると、`q1` と `q2`によって参照される qubits の状態が変更されますが、`let swappedRegister = [q2, q1];` はこれらの qubits を参照する方法にのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="3279f-213">Applying `SWAP(q1, q2)` causes a change to the state of the qubits referred to by `q1` and `q2`, while `let swappedRegister = [q2, q1];` only affects how we refer to those qubits.</span></span>
> <span data-ttu-id="3279f-214">さらに、`(Controlled SWAP)([q0], (q1, q2))` では、`SWAP` を3番目の qubit の状態に設定できます。これは、要素を再配置することでは表現できません。</span><span class="sxs-lookup"><span data-stu-id="3279f-214">Moreover, `(Controlled SWAP)([q0], (q1, q2))` allows for `SWAP` to be conditioned on the state of a third qubit, which we cannot represent by rearranging elements.</span></span>
> <span data-ttu-id="3279f-215">Fredkin gate とも呼ばれる、制御されたスワップゲートは、すべての従来の計算を含めるのに十分な性能を備えています。</span><span class="sxs-lookup"><span data-stu-id="3279f-215">The controlled-SWAP gate, also known as the Fredkin gate, is powerful enough to include all classical computation.</span></span>

<span data-ttu-id="3279f-216">最後に、準備には、マルチ qubit の指数演算子を表す2つの操作が用意されています。</span><span class="sxs-lookup"><span data-stu-id="3279f-216">Finally, the prelude provides two operations for representing exponentials of multi-qubit Pauli operators.</span></span>
<span data-ttu-id="3279f-217"><xref:microsoft.quantum.intrinsic.exp> 操作は、P# li マトリックスのすべての製品に基づいて回転を実行します。マルチ qubit の検索によって表されるようになりました。-\mathrel{: =} \ (\ vec{-sigma}, \ phi): =} > を実行しています (& o) (& a) (&)、cdots/otimes \sigma_n)、\ end{\sigma_n) $ ここで、$-vec{/sigma} = (-sigma/0, \ sigma_1, \ ドット,) $ は、シングル qubit の p Li 演算子のシーケンスであり、$ + phi $ は角度です。</span><span class="sxs-lookup"><span data-stu-id="3279f-217">The <xref:microsoft.quantum.intrinsic.exp> operation performs a rotation based on a tensor product of Pauli matrices, as represented by the multi-qubit unitary \begin{equation} \operatorname{Exp}(\vec{\sigma}, \phi) \mathrel{:=} \exp\left(i \phi \sigma_0 \otimes \sigma_1 \otimes \cdots \otimes \sigma_n \right), \end{equation} where $\vec{\sigma} = (\sigma_0, \sigma_1, \dots, \sigma_n)$ is a sequence of single-qubit Pauli operators, and where $\phi$ is an angle.</span></span>
<span data-ttu-id="3279f-218">`Exp` ローテーションは、シグネチャ `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`を持つように、`Pauli` 要素の配列として $ \ vec{{sigma} $ を表します。</span><span class="sxs-lookup"><span data-stu-id="3279f-218">The `Exp` rotation represents $\vec{\sigma}$ as an array of `Pauli` elements, such that it has signature `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="3279f-219"><xref:microsoft.quantum.intrinsic.expfrac> 操作では、上で説明した dyadic の小数点表記法を使用して、同じローテーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="3279f-219">The <xref:microsoft.quantum.intrinsic.expfrac> operation performs the same rotation, using the dyadic fraction notation discussed above.</span></span>
<span data-ttu-id="3279f-220">署名には `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`があります。</span><span class="sxs-lookup"><span data-stu-id="3279f-220">It has signature `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`.</span></span>

> [!WARNING]
> <span data-ttu-id="3279f-221">指数演算子のすべての操作は、指数または p Li オペレーターのの製品と同じではありません。</span><span class="sxs-lookup"><span data-stu-id="3279f-221">Exponentials of the tensor product of Pauli operators are not the same as tensor products of the exponentials of Pauli operators.</span></span>
> <span data-ttu-id="3279f-222">つまり、$e ^ {i (Z/otimes Z) \phi} \n e e ^ {i Z \phi}/otimes e ^ {i Z \phi} $。</span><span class="sxs-lookup"><span data-stu-id="3279f-222">That is, $e^{i (Z \otimes Z) \phi} \ne e^{i Z \phi} \otimes e^{i Z \phi}$.</span></span>

### <a name="measurements"></a><span data-ttu-id="3279f-223">測定値</span><span class="sxs-lookup"><span data-stu-id="3279f-223">Measurements</span></span> ###

<span data-ttu-id="3279f-224">測定する場合、測定される演算子の + 1 eigenvalue は、`Zero` の結果に対応し、-1 eigenvalue が `One` の結果になります。</span><span class="sxs-lookup"><span data-stu-id="3279f-224">When measuring, the +1 eigenvalue of the operator being measured corresponds to a `Zero` result, and the -1 eigenvalue to a `One` result.</span></span>

> [!NOTE]
> <span data-ttu-id="3279f-225">この規則は奇妙に見えるかもしれませんが、非常に便利な2つの利点があります。</span><span class="sxs-lookup"><span data-stu-id="3279f-225">While this convention might seem odd, it has two very nice advantages.</span></span>
> <span data-ttu-id="3279f-226">最初に、結果 $ \ket{0}$ が `Result` 値 `Zero`によって表されます。一方、$ \ket{1}$ は `One`に相当します。</span><span class="sxs-lookup"><span data-stu-id="3279f-226">First, observing the outcome $\ket{0}$ is represented by the `Result` value `Zero`, while observing $\ket{1}$ corresponds to `One`.</span></span>
> <span data-ttu-id="3279f-227">2つ目の方法として、結果に対応する eigenvalue $/ラムダ $ を、$ is $ \ ラムダ = (-1) ^ r $ という $r に記述できます。</span><span class="sxs-lookup"><span data-stu-id="3279f-227">Second, we can write out that the eigenvalue $\lambda$ corresponding to a result $r$ is $\lambda = (-1)^r$.</span></span>

<span data-ttu-id="3279f-228">測定操作は、`Adjoint` も `Controlled` のファンクタもサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3279f-228">Measurement operations support neither the `Adjoint` nor the `Controlled` functor.</span></span>

<span data-ttu-id="3279f-229"><xref:microsoft.quantum.intrinsic.measure> 操作では、指定された P# li 演算子の積で1つ以上の qubits の結合測定を実行します。</span><span class="sxs-lookup"><span data-stu-id="3279f-229">The <xref:microsoft.quantum.intrinsic.measure> operation performs a joint measurement of one or more qubits in the specified product of Pauli operators.</span></span>
<span data-ttu-id="3279f-230">P# li 配列と qubit 配列の長さが異なる場合、操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="3279f-230">If the Pauli array and qubit array are different lengths, then the operation fails.</span></span>
<span data-ttu-id="3279f-231">`Measure` に署名 `((Pauli[], Qubit[]) => Result)`があります。</span><span class="sxs-lookup"><span data-stu-id="3279f-231">`Measure` has signature `((Pauli[], Qubit[]) => Result)`.</span></span>

<span data-ttu-id="3279f-232">ジョイント測定は、各 qubit を個別に測定するのと同じではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3279f-232">Note that a joint measurement is not the same as measuring each qubit individually.</span></span>
<span data-ttu-id="3279f-233">たとえば、state $ \ket{11} = \ket{1} \ otimes \ket{1} = xotimes X \ket{00}$ とします。</span><span class="sxs-lookup"><span data-stu-id="3279f-233">For example, consider the state $\ket{11} = \ket{1} \otimes \ket{1} = X\otimes X \ket{00}$.</span></span>
<span data-ttu-id="3279f-234">各 $Z 0 $ と $Z _1 $ を個別に測定すると、$r 0 = $1 および $r _1 = $1 の結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="3279f-234">Measuring $Z_0$ and $Z_1$ each individually, we get the results $r_0 = 1$ and $r_1 = 1$.</span></span>
<span data-ttu-id="3279f-235">ただし $Z 0 Z_1 $ を測定すると、1つの結果 $r _ {\textrm{joint}} = $0 となります。これは、$ \ket{11}$ の pairity が正であることを表します。</span><span class="sxs-lookup"><span data-stu-id="3279f-235">Measuring $Z_0 Z_1$, however, we get the single result $r_{\textrm{joint}} = 0$, representing that the pairity of $\ket{11}$ is positive.</span></span>
<span data-ttu-id="3279f-236">異なる形式で、$ (-1) ^ {r_0 + r_1} = (-1) ^ r_ {\textrm{joint}}) $ と指定します。</span><span class="sxs-lookup"><span data-stu-id="3279f-236">Put differently, $(-1)^{r_0 + r_1} = (-1)^r_{\textrm{joint}})$.</span></span>
<span data-ttu-id="3279f-237">非常に大きなことですが、この測定からはパリティを学習する*だけ*なので、法則に示されている、正のパリティの 2 2-qubit の状態間のクォンタム情報 ($ \ket{00}$ と $ \ket{11}$) は保持されます。</span><span class="sxs-lookup"><span data-stu-id="3279f-237">Critically, since we *only* learn the parity from this measurement, any quantum information represented in the superposition between the two two-qubit states of positive parity, $\ket{00}$ and $\ket{11}$, is preserved.</span></span>
<span data-ttu-id="3279f-238">このプロパティは、エラー修正について説明するため、後で必要になります。</span><span class="sxs-lookup"><span data-stu-id="3279f-238">This property will be essential later, as we discuss error correction.</span></span>

<span data-ttu-id="3279f-239">便宜上、準備には、qubits を測定するための他の2つの操作も用意されています。</span><span class="sxs-lookup"><span data-stu-id="3279f-239">For convenience, the prelude also provides two other operations for measuring qubits.</span></span>
<span data-ttu-id="3279f-240">まず、single qubit の測定を実行するのは非常に一般的であるため、準備はこの場合の短縮形を定義します。</span><span class="sxs-lookup"><span data-stu-id="3279f-240">First, since performing single-qubit measurements is quite common, the prelude defines a shorthand for this case.</span></span>
<span data-ttu-id="3279f-241"><xref:microsoft.quantum.intrinsic.m> 操作では、1つの qubit に対して p Li $Z $ 演算子を測定し、シグネチャ `(Qubit => Result)`を持ちます。</span><span class="sxs-lookup"><span data-stu-id="3279f-241">The <xref:microsoft.quantum.intrinsic.m> operation measures the Pauli $Z$ operator on a single qubit, and has signature `(Qubit => Result)`.</span></span>
<span data-ttu-id="3279f-242">`M(q)` は `Measure([PauliZ], [q])` に相当します。</span><span class="sxs-lookup"><span data-stu-id="3279f-242">`M(q)` is equivalent to `Measure([PauliZ], [q])`.</span></span>

<span data-ttu-id="3279f-243"><xref:microsoft.quantum.measurement.multim> は、qubits の各配列で*個別*に p li $Z $ 演算子を測定し、各 qubits に対して取得された `Result` 値の*配列*を返します。</span><span class="sxs-lookup"><span data-stu-id="3279f-243">The <xref:microsoft.quantum.measurement.multim> measures the Pauli $Z$ operator *separately* on each of an array of qubits, returning the *array* of `Result` values obtained for each qubit.</span></span>
<span data-ttu-id="3279f-244">場合によっては、これを最適化することができます。</span><span class="sxs-lookup"><span data-stu-id="3279f-244">In some cases this can be optimized.</span></span> <span data-ttu-id="3279f-245">署名があります (`Qubit[] => Result[])`。</span><span class="sxs-lookup"><span data-stu-id="3279f-245">It has signature (`Qubit[] => Result[])`.</span></span>
<span data-ttu-id="3279f-246">`MultiM(qs)` は、次の場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="3279f-246">`MultiM(qs)` is equivalent to:</span></span>

```qsharp
mutable rs = new Result[Length(qs)];
for (index in 0..Length(qs)-1)
{
    set rs[index] = M(qs[index]);
}
return rs;
```

## <a name="extension-functions-and-operations"></a><span data-ttu-id="3279f-247">拡張関数と操作</span><span class="sxs-lookup"><span data-stu-id="3279f-247">Extension Functions and Operations</span></span> ##

<span data-ttu-id="3279f-248">さらに、準備は、Q # コード内で使用するために、.NET レベルで数学的および型変換関数の豊富なセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="3279f-248">In addition, the prelude defines a rich set of mathematical and type conversion functions at the .NET level for use within Q# code.</span></span>
<span data-ttu-id="3279f-249">たとえば、<xref:microsoft.quantum.extensions.math> 名前空間は、<xref:microsoft.quantum.extensions.math.sin> や <xref:microsoft.quantum.extensions.math.log>などの便利な操作を定義します。</span><span class="sxs-lookup"><span data-stu-id="3279f-249">For instance, the <xref:microsoft.quantum.extensions.math> namespace defines useful operations such as <xref:microsoft.quantum.extensions.math.sin> and <xref:microsoft.quantum.extensions.math.log>.</span></span>
<span data-ttu-id="3279f-250">Quantum 開発キットによって提供される実装では、従来の .NET 基底クラスライブラリを使用します。そのため、quantum プログラムとその典型的なドライバーの間で、追加の通信ラウンドトリップが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3279f-250">The implementation provided by the Quantum Development Kit uses the classical .NET base class library, and thus may involve an additional communications round trip between quantum programs and their classical drivers.</span></span>
<span data-ttu-id="3279f-251">これによってローカルシミュレーターに問題が発生することはありませんが、リモートシミュレーターまたは実際のハードウェアをターゲットコンピューターとして使用すると、パフォーマンスの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3279f-251">While this does not present a problem for a local simulator, this can be a performance issue when using a remote simulator or actual hardware as a target machine.</span></span>
<span data-ttu-id="3279f-252">ただし、個々のターゲットコンピューターは、このような操作を特定のシステムにとってより効率的なバージョンで上書きすることによって、このパフォーマンスへの影響を軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="3279f-252">That said, an individual target machine may mitigate this performance impact by overriding these operations with versions that are more efficient for that particular system.</span></span>

### <a name="math"></a><span data-ttu-id="3279f-253">数値演算</span><span class="sxs-lookup"><span data-stu-id="3279f-253">Math</span></span> ###

<span data-ttu-id="3279f-254"><xref:microsoft.quantum.extensions.math> 名前空間には、.NET 基本クラスライブラリの[`System.Math` クラス](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1)の便利な関数が多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="3279f-254">The <xref:microsoft.quantum.extensions.math> namespace provides many useful functions from the .NET base class library's [`System.Math` class](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1).</span></span>
<span data-ttu-id="3279f-255">これらの関数は、他の Q # 関数と同じ方法で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3279f-255">These functions can be used in the same manner as any other Q# functions:</span></span>

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

<span data-ttu-id="3279f-256">.NET の静的メソッドが引数の型に基づいてオーバーロードされている場合、対応する Q # 関数には、入力の型を示すサフィックスで注釈が付けられます。</span><span class="sxs-lookup"><span data-stu-id="3279f-256">Where a .NET static method has been overloaded based on the type of its arguments, the corresponding Q# function is annotated with a suffix indicating the type of its input:</span></span>

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a><span data-ttu-id="3279f-257">ビットごとの演算</span><span class="sxs-lookup"><span data-stu-id="3279f-257">Bitwise Operations</span></span> ###

<span data-ttu-id="3279f-258">最後に、<xref:microsoft.quantum.extensions.bitwise> 名前空間には、ビットごとの演算子で整数を操作するための便利な関数がいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="3279f-258">Finally, the <xref:microsoft.quantum.extensions.bitwise> namespace provides several useful functions for manipulating integers through bitwise operators.</span></span>
<span data-ttu-id="3279f-259">たとえば、<xref:microsoft.quantum.extensions.bitwise.parity> は、整数のビットごとのパリティを別の整数として返します。</span><span class="sxs-lookup"><span data-stu-id="3279f-259">For instance, <xref:microsoft.quantum.extensions.bitwise.parity> returns the bitwise parity of an integer as another integer.</span></span>
