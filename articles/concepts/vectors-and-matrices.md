---
title: 量子コンピューティングのベクトルと行列
description: ベクターとマトリックスを操作する方法の基本について説明します。
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
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
ms.openlocfilehash: 6c09531cd8bee8f5efb472c95c575daed04d3040
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630197"
---
# <a name="vectors-and-matrices"></a><span data-ttu-id="eb2f0-103">ベクターと行列</span><span class="sxs-lookup"><span data-stu-id="eb2f0-103">Vectors and Matrices</span></span>

<span data-ttu-id="eb2f0-104">ベクターとマトリックスについては、クォンタムコンピューティングを理解するために重要な知識があります。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-104">Some familiarity with vectors and matrices is essential to understand quantum computing.</span></span> <span data-ttu-id="eb2f0-105">次の簡単な概要を説明します。また、読者には、 *Strang、G. (1993) などの線形代数の標準参照を読むことをお勧めします。線形代数 (Vol. 3) の概要。Wellesley、MA: Wellesley を押す*か、[線形代数](http://joshua.smcvt.edu/linearalgebra/)などのオンライン参照をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-105">We provide a brief introduction below and interested readers are recommended to read a standard reference on linear algebra such as *Strang, G. (1993). Introduction to linear algebra (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* or an online reference such as [Linear Algebra](http://joshua.smcvt.edu/linearalgebra/).</span></span>

<span data-ttu-id="eb2f0-106">次元 (またはサイズ $n) の列ベクター (または単に[*ベクター*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v $ は、 $ $ 列として配置される $n 複素数 $ (v_1、v_2、\ lドット、v_n) $ のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-106">A column vector (or simply [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v$ of dimension (or size) $n$ is a collection of $n$ complex numbers $(v_1,v_2,\ldots,v_n)$ arranged as a column:</span></span>

<span data-ttu-id="eb2f0-107">$ $v = \ begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-107">$$v =\begin{bmatrix}</span></span>
<span data-ttu-id="eb2f0-108">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="eb2f0-108">v_1\\\\</span></span>
<span data-ttu-id="eb2f0-109">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="eb2f0-109">v_2\\\\</span></span>
<span data-ttu-id="eb2f0-110">\ vドット\\\\</span><span class="sxs-lookup"><span data-stu-id="eb2f0-110">\vdots\\\\</span></span>
<span data-ttu-id="eb2f0-111">v_n & end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="eb2f0-111">v_n \end{bmatrix}$$</span></span>

<span data-ttu-id="eb2f0-112">ベクター $v の基準は、 $ $-sqrt { \ sum \_ i | v \_ i | ^ 2 $ として定義されてい } ます。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-112">The norm of a vector $v$ is defined as $\sqrt{\sum\_i |v\_i|^2}$.</span></span> <span data-ttu-id="eb2f0-113">ベクターは、標準が $1 の場合には単位基準 (または[*単位ベクトル*](https://en.wikipedia.org/wiki/Unit_vector)と呼ばれます) と呼ばれ $ ます。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-113">A vector is said to be of unit norm (or alternatively it is called a [*unit vector*](https://en.wikipedia.org/wiki/Unit_vector)) if its norm is $1$.</span></span> <span data-ttu-id="eb2f0-114">[*ベクター $v の adjoint*](https://en.wikipedia.org/wiki/Adjoint_matrix)は、 $ $v ^ に示され、 $ 次の行ベクトルとして定義されています。 $ \* $ は複雑な共役を表します。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-114">The [*adjoint of a vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ is denoted $v^\dagger$ and is defined to be the following row vector where $\*$ denotes the complex conjugate,</span></span>

<span data-ttu-id="eb2f0-115">$ $ \ begin{ bmatrix } v_1 \\ \\ \ vドット \\ \\ v_n \ end{ bmatrix } ^ \ ダガー = \ begin{ bmatrix } v_1 ^ \* &/cドット & v_n ^ \* & end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="eb2f0-115">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}^\dagger = \begin{bmatrix}v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span></span>

<span data-ttu-id="eb2f0-116">2つのベクトルを乗算する最も一般的な方法は、[*内部製品*](https://en.wikipedia.org/wiki/Inner_product_space)(ドット積とも呼ばれます) を使用することです。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-116">The most common way to multiply two vectors together is through the [*inner product*](https://en.wikipedia.org/wiki/Inner_product_space), also known as a dot product.</span></span>  <span data-ttu-id="eb2f0-117">内側の製品は、あるベクターの射影を別のベクターに提供し、1つのベクターを他のより単純なベクターの合計として表現する方法を説明するうえで非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-117">The inner product gives the projection of one vector onto another and is invaluable in describing how to express one vector as a sum of other simpler vectors.</span></span>  <span data-ttu-id="eb2f0-118">$U と $v 間の内部積。ここで $ $ は $ left \langle u, v \right \rangle $ はとして定義されています。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-118">The inner product between $u$ and $v$, denoted $\left\langle u, v\right\rangle$ is defined as</span></span>

<span data-ttu-id="eb2f0-119">$ $ \ langle u, v \rangle = u ^ \ ダガー v = u \_ 1 ^ { \* } v_1 + \ cドット + u \_ n ^ { \* } v \_ n</span><span class="sxs-lookup"><span data-stu-id="eb2f0-119">$$ \langle u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.</span></span>
$$

<span data-ttu-id="eb2f0-120">この表記法を使用すると、ベクターの $v $ を $-sqrt { \ langle v, v $ として記述することもでき \rangle } ます。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-120">This notation also allows the norm of a vector $v$ to be written as $\sqrt{\langle v, v\rangle}$.</span></span>

<span data-ttu-id="eb2f0-121">ベクターと数値 $c を乗算して、 $ $c によってエントリに乗算される新しいベクターを形成でき $ ます。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-121">We can multiply a vector with a number $c$ to form a new vector whose entries are multiplied by $c$.</span></span> <span data-ttu-id="eb2f0-122">また、2つのベクター $u $ を追加 $v して、 $ $u と $v のエントリを加算したエントリを持つ新しいベクターを作成することもでき $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-122">We can also add two vectors $u$ and $v$ to form a new vector whose entries are the sum of the entries of $u$ and $v$.</span></span> <span data-ttu-id="eb2f0-123">これらの操作を次に示します。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-123">These operations are depicted below:</span></span>

<span data-ttu-id="eb2f0-124">$ $ \mathrm{If } ~ u = \ begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-124">$$\mathrm{If}~u =\begin{bmatrix}</span></span>
<span data-ttu-id="eb2f0-125">u_1\\\\</span><span class="sxs-lookup"><span data-stu-id="eb2f0-125">u_1\\\\</span></span>
<span data-ttu-id="eb2f0-126">u_2\\\\</span><span class="sxs-lookup"><span data-stu-id="eb2f0-126">u_2\\\\</span></span>
<span data-ttu-id="eb2f0-127">\ vドット\\\\</span><span class="sxs-lookup"><span data-stu-id="eb2f0-127">\vdots\\\\</span></span>
<span data-ttu-id="eb2f0-128">u_n \ end{ bmatrix } ~ \mathrm{and } ~ v = \ begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-128">u_n \end{bmatrix}~\mathrm{and}~ v =\begin{bmatrix}</span></span>
    <span data-ttu-id="eb2f0-129">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="eb2f0-129">v_1\\\\</span></span>
    <span data-ttu-id="eb2f0-130">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="eb2f0-130">v_2\\\\</span></span>
    <span data-ttu-id="eb2f0-131">\ vドット\\\\</span><span class="sxs-lookup"><span data-stu-id="eb2f0-131">\vdots\\\\</span></span>
    <span data-ttu-id="eb2f0-132">v_n \ end{ bmatrix } , ~ \mathrm{then } ~ au + bv = \ begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-132">v_n \end{bmatrix},~\mathrm{then}~ au+bv =\begin{bmatrix}</span></span>
<span data-ttu-id="eb2f0-133">au_1 + bv_1\\\\</span><span class="sxs-lookup"><span data-stu-id="eb2f0-133">au_1+bv_1\\\\</span></span>
<span data-ttu-id="eb2f0-134">au_2 + bv_2\\\\</span><span class="sxs-lookup"><span data-stu-id="eb2f0-134">au_2+bv_2\\\\</span></span>
<span data-ttu-id="eb2f0-135">\ vドット\\\\</span><span class="sxs-lookup"><span data-stu-id="eb2f0-135">\vdots\\\\</span></span>
<span data-ttu-id="eb2f0-136">au_n + bv_n \ end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="eb2f0-136">au_n+bv_n \end{bmatrix}.</span></span>
$$

<span data-ttu-id="eb2f0-137">次[*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics))のように $ $m の $ $ 行と $n の列に配置された $mn 複素数のコレクションは、サイズ $m/倍 n です $ 。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-137">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) of size $m \times n$ is a collection of $mn$ complex numbers arranged in $m$ rows and $n$ columns as shown below:</span></span>

<span data-ttu-id="eb2f0-138">$ $M = \ begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-138">$$M = \begin{bmatrix}</span></span>
<span data-ttu-id="eb2f0-139">M_ {11 } ~ ~ M_ {12 } ~ ~ \ ドット ~ ~ M_ {1n } \\ \\ M_ {21 } ~ ~ M_ {22 } ~ ~ \ ドット ~ ~ M_ {2n } \\ \\\\\\</span><span class="sxs-lookup"><span data-stu-id="eb2f0-139">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\ M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="eb2f0-140">M_ {m1 } ~ ~ M_ {m2 } ~ ~-cドット ~ ~ M_ { } \\ \\ bmatrix } . $ $</span><span class="sxs-lookup"><span data-stu-id="eb2f0-140">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}\\\\ \end{bmatrix}.$$</span></span>

<span data-ttu-id="eb2f0-141">Dimension $n のベクター $ は、単に size $n の1倍の行列であることに注意して $ ください。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-141">Note that a vector of dimension $n$ is simply a matrix of size $n \times 1$.</span></span> <span data-ttu-id="eb2f0-142">ベクターの場合と同様に、マトリックスと数値 $c を乗算して、 $ すべてのエントリが $c と乗算される新しい行列を取得できます $ 。また、同じサイズの2つのマトリックスを追加して、2つの行列の各エントリの合計を入力する新しい行列を生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-142">As with vectors, we can multiply a matrix with a number $c$ to obtain a new matrix where every entry is multiplied with $c$, and we can add two matrices of the same size to produce a new matrix whose entries are the sum of the respective entries of the two matrices.</span></span> 

## <a name="matrix-multiplication-and-tensor-products"></a><span data-ttu-id="eb2f0-143">マトリックス乗算とその他の製品</span><span class="sxs-lookup"><span data-stu-id="eb2f0-143">Matrix Multiplication and Tensor Products</span></span>

<span data-ttu-id="eb2f0-144">また、次のように、次元の2つの行列 $M $ $m \times n $ と $n 次元の $N を乗算することによって、ディメンションの $P の $ $ 新しいマトリックス $m を取得することもでき $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-144">We can also multiply two matrices $M$ of dimension $m\times n$ and $N$ of dimension $n \times p$ to get a new matrix $P$ of dimension $m \times p$ as follows:</span></span>

<span data-ttu-id="eb2f0-145">& i)}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-145">\begin{align}</span></span>
<span data-ttu-id="eb2f0-146">& \ begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-146">&\begin{bmatrix}</span></span>
    <span data-ttu-id="eb2f0-147">M_ {11 } ~ ~ M_ {12 } ~ ~ \ ドット ~ ~ M_ {1n } \\ \\ M_ {21 } ~ ~ M_ {22 } ~ ~ \ ドット ~ ~ M_ {2n } \\ \\\\\\</span><span class="sxs-lookup"><span data-stu-id="eb2f0-147">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\ M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\ \ddots\\\\</span></span>
    <span data-ttu-id="eb2f0-148">M_ {m1 } ~ ~ M_ {m2 } ~ ~-cドット ~ ~ M_ {になります}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-148">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}</span></span>
<span data-ttu-id="eb2f0-149">エンドbmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-149">\end{bmatrix}</span></span>
<span data-ttu-id="eb2f0-150">初めbmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-150">\begin{bmatrix}</span></span>
<span data-ttu-id="eb2f0-151">N_ {11 } ~ ~ N_ {12 } ~ ~ \ ドット ~ ~ N_ {1p } \\ \\ N_ {21 } ~ ~ N_ {22 } ~ ~/cドット ~ ~ N_ {2p } \\ \\\\\\</span><span class="sxs-lookup"><span data-stu-id="eb2f0-151">N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\ N_{21} ~~ N_{22} ~~ \cdots ~~ N_{2p}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="eb2f0-152">N_ {n1 } ~ ~ N_ {n2 } ~ ~ \ N_ {np}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-152">N_{n1} ~~ N_{n2} ~~ \cdots ~~ N_{np}</span></span>
<span data-ttu-id="eb2f0-153">\ end{ bmatrix } = \ begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-153">\end{bmatrix}=\begin{bmatrix}</span></span>
<span data-ttu-id="eb2f0-154">P_ {11 } ~ ~ P_ {12 } ~ ~ \ ドット ~ ~ P_ {1p } \\ \\ P_ {21 } ~ ~ P_ {22 } ~ ~/cドット ~ ~ P_ {2p } \\ \\\\\\</span><span class="sxs-lookup"><span data-stu-id="eb2f0-154">P_{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\ P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="eb2f0-155">P_ {m1 ~ } ~ P_ {m2 } ~ ~ \ P_ {mp}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-155">P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp}</span></span>
<span data-ttu-id="eb2f0-156">エンドbmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-156">\end{bmatrix}</span></span>
<span data-ttu-id="eb2f0-157">& end{align}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-157">\end{align}</span></span>

<span data-ttu-id="eb2f0-158">$P のエントリ $ は $P _ {ik } = \ sum_j M_ {ij} N_ {jk } $ です。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-158">where the entries of $P$ are $P_{ik} = \sum_j M_{ij}N_{jk}$.</span></span> <span data-ttu-id="eb2f0-159">たとえば $P _ {11 $ というエントリは、 } $ $N の最初の列を $M の最初の行の内部積です $ 。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-159">For example, the entry $P_{11}$ is the inner product of the first row of $M$ with the first column of $N$.</span></span> <span data-ttu-id="eb2f0-160">ベクターは単にマトリックスの特殊なケースであるため、この定義はマトリックスベクトル乗算まで拡張されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-160">Note that since a vector is simply a special case of a matrix, this definition extends to matrix-vector multiplication.</span></span> 

<span data-ttu-id="eb2f0-161">考慮するすべてのマトリックスは、行と列の数が等しいか、またはベクトルであり、$1 列にのみ対応する正方形のマトリックス $ です。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-161">All the matrices we consider will either be square matrices, where the number of rows and columns are equal, or vectors, which corresponds to only $1$ column.</span></span> <span data-ttu-id="eb2f0-162">1つの特殊な正方形の行列は、 [*id 行列*](https://en.wikipedia.org/wiki/Identity_matrix)です $ 。これは、すべての対角線の要素が $1 と等しく、残りの要素が $0 であることを $ 示してい $ ます。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-162">One special square matrix is the [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix), denoted $\boldone$, which has all its diagonal elements equal to $1$ and the remaining elements equal to $0$:</span></span>

<span data-ttu-id="eb2f0-163">$ $ > bold 完了 = \ begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-163">$$\boldone=\begin{bmatrix}</span></span>
<span data-ttu-id="eb2f0-164">1 ~ ~ 0 ~ ~ \ 300 ドット ~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="eb2f0-164">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="eb2f0-165">0 ~ ~ 1 ~ ~ \ 300 ドット ~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="eb2f0-165">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="eb2f0-166">~ ~ \ dドット\\\\</span><span class="sxs-lookup"><span data-stu-id="eb2f0-166">~~ \ddots\\\\</span></span>
<span data-ttu-id="eb2f0-167">0 ~ ~ 0 ~ ~ (cドット) ~ ~ 1 & end{ bmatrix } . $ $</span><span class="sxs-lookup"><span data-stu-id="eb2f0-167">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="eb2f0-168">$A の正方形行列の $ $ 場合、$AB = BA =/$B が行われた場合、行列は[*逆*](https://en.wikipedia.org/wiki/Invertible_matrix)に $ なります。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-168">For a square matrix $A$, we say a matrix $B$ is its [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) if $AB = BA = \boldone$.</span></span> <span data-ttu-id="eb2f0-169">マトリックスの逆も存在している必要はありませんが、存在する場合は一意であり、^ {-1 $ $A ことを意味し } ます。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-169">The inverse of a matrix need not exist, but when it exists it is unique and we denote it $A^{-1}$.</span></span> 

<span data-ttu-id="eb2f0-170">マトリックス $M の場合 $ 、$M の adjoint または共役転置はマトリックス $N であり、 $ $ $N _ {ij } = M_ {ji } ^ \* $ です。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-170">For any matrix $M$, the adjoint or conjugate transpose of $M$ is a matrix $N$ such that $N_{ij} = M_{ji}^\*$.</span></span> <span data-ttu-id="eb2f0-171">$M の adjoint $ は、通常、$M ^ \ ダガーに示され $ ます。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-171">The adjoint of $M$ is usually denoted $M^\dagger$.</span></span> <span data-ttu-id="eb2f0-172">ここでは、" $ ^ [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) & $UU = u ^ \ ダガー u = \" $ を $U ^ {-1 } = u ^ \ ダガーと同等であるかどうかに関係ない場合は、"$U" という行列が付いてい $ ます。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-172">We say a matrix $U$ is [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) if $UU^\dagger = U^\dagger U = \boldone$ or equivalently, $U^{-1} = U^\dagger$.</span></span>  <span data-ttu-id="eb2f0-173">たとえば、最も重要なのは、ベクトルの基準を維持することです。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-173">Perhaps the most important property of unitary matrices is that they preserve the norm of a vector.</span></span>  <span data-ttu-id="eb2f0-174">これは、</span><span class="sxs-lookup"><span data-stu-id="eb2f0-174">This happens because</span></span> 

<span data-ttu-id="eb2f0-175">$ $ \ langle v, v \rangle = v ^-ダガー v = v ^ \ ダガー U ^ {-1 } u v = v ^-ダガー u ^ \ ダガー u v = \ langle u v, U v \rangle . $ $</span><span class="sxs-lookup"><span data-stu-id="eb2f0-175">$$\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$</span></span>  

<span data-ttu-id="eb2f0-176">マトリックスの $M $ は、$M = M ^ [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix)の場合は、"" と呼ばれ $ ます。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-176">A matrix $M$ is said to be [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) if $M=M^\dagger$.</span></span>

<span data-ttu-id="eb2f0-177">最後に、2つの $M マトリックスの[*Kronecker (また*](https://en.wikipedia.org/wiki/Tensor_product)は nq product) のサイズが $ $m \times n で、サイズが $N の $p のサイズが大きい場合、 $ $ q はより大きなマトリックスとして $P $mp $ \otimes $ $ から取得され、次の $M から取得され $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-177">Finally, the [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (or Kronecker product) of two matrices $M$ of size $m\times n$ and $N$ of size $p \times q$ is a larger matrix $P=M\otimes N$ of size $mp \times nq$, and is obtained from $M$ and $N$ as follows:</span></span>

<span data-ttu-id="eb2f0-178">& i)}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-178">\begin{align}</span></span>
    <span data-ttu-id="eb2f0-179">M/otimes N &= \ begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-179">M \otimes N &= \begin{bmatrix}</span></span>
        <span data-ttu-id="eb2f0-180">M_ {11 } ~ ~ \ cドット ~ ~ M_ {1n } \\ \\ \ dドット\\\\</span><span class="sxs-lookup"><span data-stu-id="eb2f0-180">M_{11} ~~ \cdots ~~ M_{1n} \\\\ \ddots\\\\</span></span>
        <span data-ttu-id="eb2f0-181">M_ {m1 } ~ ~ \ cドット ~ ~ M_ {になります}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-181">M_{m1}  ~~ \cdots ~~ M_{mn}</span></span>
    <span data-ttu-id="eb2f0-182">エンドbmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-182">\end{bmatrix}</span></span>
    <span data-ttu-id="eb2f0-183">\ otimes \ begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-183">\otimes \begin{bmatrix}</span></span>
        <span data-ttu-id="eb2f0-184">N_ {11 } ~ ~ \ cドット ~ ~ N_ {1q } \\ \\ \ dドット\\\\</span><span class="sxs-lookup"><span data-stu-id="eb2f0-184">N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\</span></span>
        <span data-ttu-id="eb2f0-185">N_ {p1 } ~ ~ \ cドット ~ ~ N_ {pq}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-185">N_{p1} ~~ \cdots ~~ N_{pq}</span></span>
    <span data-ttu-id="eb2f0-186">\ end{ bmatrix } \\ \\ &= \ begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-186">\end{bmatrix}\\\\ &= \begin{bmatrix}</span></span>
        <span data-ttu-id="eb2f0-187">M_ {11 } \ begin{ bmatrix } N_ {11 } ~ ~-cドット ~ ~ N_ {1q } \\ \\ \ dドット \\\\ N_ {p1 } ~ ~-cドット ~ ~ N_ {pq } \ end{~ bmatrix } ~-cドット ~ ~ M_ {1q } \ begin{ bmatrix } N_ {11 } ~ ~ \ cドット ~ ~ N_ {1q/ } \\ \\ dドット \\\\ N_ {p1 } ~ ~-cドット ~ ~ N_ {pq } \ end{/ bmatrix } \\ \\ dドット\\\\</span><span class="sxs-lookup"><span data-stu-id="eb2f0-187">M_{11} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~ M_{1n} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\ \ddots\\\\</span></span>
        <span data-ttu-id="eb2f0-188">M_ {m1 } \ begin{ bmatrix } N_ {11 } ~ ~-cドット ~ ~ N_ {1q } \\ \\ \ dドット \\\\ N_ {p1 } ~ ~-cドット ~ ~ N_ {pq } \ end{ bmatrix } ~ ~-cドット ~ ~ M_ { } bmatrix } N_ {11 } ~ ~-cドット ~ ~ N_ {1q } \\ \\ \ dドット \\\\ N_ {p1 } ~ ~-cドット ~ ~ N_ {pq } \ end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-188">M_{m1} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~ M_{mn} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}</span></span>
    <span data-ttu-id="eb2f0-189">\ end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="eb2f0-189">\end{bmatrix}.</span></span>
<span data-ttu-id="eb2f0-190">& end{align}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-190">\end{align}</span></span>

<span data-ttu-id="eb2f0-191">次に例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-191">This is better demonstrated with some examples:</span></span>

<span data-ttu-id="eb2f0-192">$ $ \ begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-192">$$ \begin{bmatrix}</span></span>
        <span data-ttu-id="eb2f0-193">a \\ \\ b & # {/ bmatrix } otimes & begin{ bmatrix } c \\ \\ d \\ \\ e \ end{ bmatrix } = \ begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-193">a \\\\ b  \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} = \begin{bmatrix}</span></span>
        <span data-ttu-id="eb2f0-194">a & begin{ bmatrix } c \\ \\ d \\ \\ e \ end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-194">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span></span>
        <span data-ttu-id="eb2f0-195">\\\\[1.5 em] b & begin{ bmatrix } c \\ \\ d \\ \\ e \end {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-195">\\\\[1.5em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span></span>
    <span data-ttu-id="eb2f0-196">エンドbmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-196">\end{bmatrix}</span></span>
    <span data-ttu-id="eb2f0-197">= \ begin{ bmatrix } a c \\ \\ a d \\ \\ a e \\ \\ b c \\ \\ b d \\ \\ be \end {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-197">= \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end{bmatrix}</span></span>
$$

<span data-ttu-id="eb2f0-198">および</span><span class="sxs-lookup"><span data-stu-id="eb2f0-198">and</span></span>

<span data-ttu-id="eb2f0-199">$ $ \ begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-199">$$ \begin{bmatrix}</span></span>
        <span data-ttu-id="eb2f0-200">a \ b \\ \\ c \ d \ end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-200">a\ b \\\\ c\ d \end{bmatrix}</span></span>
    <span data-ttu-id="eb2f0-201">\ otimes \ begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-201">\otimes \begin{bmatrix}</span></span>
        <span data-ttu-id="eb2f0-202">e \ f \\ \\ g \ h \ end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-202">e\ f\\\\g\ h \end{bmatrix}</span></span>
     <span data-ttu-id="eb2f0-203">= \ begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-203">= \begin{bmatrix}</span></span>
    <span data-ttu-id="eb2f0-204">a \begin {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-204">a\begin{bmatrix}</span></span>
    <span data-ttu-id="eb2f0-205">e \ f \\\\ g \ h \ end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-205">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="eb2f0-206">b \begin {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-206">b\begin{bmatrix}</span></span>
    <span data-ttu-id="eb2f0-207">e \ f \\\\ g \ h \ end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-207">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="eb2f0-208">\\\\[1em] c \begin {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-208">\\\\[1em] c\begin{bmatrix}</span></span>
    <span data-ttu-id="eb2f0-209">e \ f \\\\ g \ h \ end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-209">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="eb2f0-210">d \begin {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-210">d\begin{bmatrix}</span></span>
    <span data-ttu-id="eb2f0-211">e \ f \\\\ g \ h \ end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-211">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="eb2f0-212">エンドbmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-212">\end{bmatrix}</span></span>
    <span data-ttu-id="eb2f0-213">= \ begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-213">= \begin{bmatrix}</span></span>
    <span data-ttu-id="eb2f0-214">ae \ af \、\\ bf \\ \\ ag \ ah \ bg \ bh \\ \\ ce \ cf \ \\ \\ bmatrix (&)、df cg } \、& lt; グループ名 \。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-214">ae\ af\ be\ bf \\\\ ag\ ah\ bg\ bh \\\\ ce\ cf\ de\ df \\\\ cg\ ch\ dg\ dh \end{bmatrix}.</span></span>
$$

<span data-ttu-id="eb2f0-215">数値表記と製品を囲む最後の便利な方法として、ベクター $v $ またはマトリックス $M については、 $ $v ^ {/otimes n $ } または $M ^ {/otimes n } $ は、$n $ フォールドで繰り返されていたすべての製品に対して短縮されます。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-215">A final useful notational convention surrounding tensor products is that, for any vector $v$ or matrix $M$, $v^{\otimes n}$ or $M^{\otimes n}$ is short hand for an $n$-fold repeated tensor product.</span></span>  <span data-ttu-id="eb2f0-216">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="eb2f0-216">For example:</span></span>

<span data-ttu-id="eb2f0-217">& i)}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-217">\begin{align}</span></span>
<span data-ttu-id="eb2f0-218">& \ begin{ bmatrix } 1 \\ \\ 0 \ end{ bmatrix } ^ {\ otimes 1 } = \ begin{ bmatrix } 1 \\ \\ 0 \ end{, \qquad {1 0 \ end{ bmatrix } \begin bmatrix } \\ \\ bmatrix } ^ {/otimes 2 } = \ begin{ bmatrix } 1 0 0 & \\ \\ \\ \\ \\ \\ end{ bmatrix } , \qquad \begin { bmatrix } 1 \\ \\ -1 \ end{ bmatrix } ^ {/otimes 2 } = \ begin{ bmatrix } 1 \\ \\ -1 \\ \\ -1- \\ \\ end{ bmatrix } , \\ \\ & \ begin{ bmatrix } 0 & 1 \\ \\ 1 0 & & end{ bmatrix } ^ {/otimes 1 } = \ begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \ end{ bmatrix } , \qquad \begin { bmatrix } 0 & 1 \\ \\ 1 & 0 \ end{ bmatrix } ^ {\ otimes 2 } = \ begin{ bmatrix } 0 &0&0&1 \\ \\ 0 &0&1&0 \\ \\ 0 &1&0&0 \\\\ 1 &0&\end bmatrix } 0&0 {.</span><span class="sxs-lookup"><span data-stu-id="eb2f0-218">&\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ -1 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ -1 \\\\-1 \\\\1 \end{bmatrix}, \\\\ &\begin{bmatrix}  0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 1}= \begin{bmatrix}    0& 1 \\\\ 1& 0  \end{bmatrix},  \qquad\begin{bmatrix} 0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 2}= \begin{bmatrix} 0 &0&0&1 \\\\ 0 &0&1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0\end{bmatrix}.</span></span>
<span data-ttu-id="eb2f0-219">& end{align}</span><span class="sxs-lookup"><span data-stu-id="eb2f0-219">\end{align}</span></span>
