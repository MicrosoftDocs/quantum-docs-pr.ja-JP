---
title: 高度な行列の概念
description: クォンタムアルゴリズムの記述とシミュレーションに使用される基本的なツールである固有ベクトル、eigenvalues、および matrix 指数について説明します。
author: QuantumWriter
uid: microsoft.quantum.concepts.matrix-advanced
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
ms.openlocfilehash: 8d3c646715f13c454e51b9295cbfdabf6a236ffc
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630147"
---
# <a name="advanced-matrix-concepts"></a><span data-ttu-id="5b670-103">高度なマトリックスの概念</span><span class="sxs-lookup"><span data-stu-id="5b670-103">Advanced Matrix Concepts</span></span> #

<span data-ttu-id="5b670-104">マトリックスの操作を[*Eigenvalues、固有ベクトル*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)、[*指数*](https://en.wikipedia.org/wiki/Matrix_exponential)に拡張しました。これにより、クォンタムアルゴリズムの記述と実装に必要なツールの基本的なセットが形成されます。</span><span class="sxs-lookup"><span data-stu-id="5b670-104">We now extend our manipulation of Matrices to [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) and [*Exponentials*](https://en.wikipedia.org/wiki/Matrix_exponential) which form a fundamental set of tools we need to describe and implement quantum algorithms.</span></span>

## <a name="eigenvalues-and-eigenvectors"></a><span data-ttu-id="5b670-105">Eigenvalues と固有ベクトル</span><span class="sxs-lookup"><span data-stu-id="5b670-105">Eigenvalues and Eigenvectors</span></span> ##

<span data-ttu-id="5b670-106">$M $ 正方形の行列にし、 $ すべてのゼロベクトルではないベクター (つまり、すべてのエントリが $0 であるベクトル) にする $v $ ます。</span><span class="sxs-lookup"><span data-stu-id="5b670-106">Let $M$ be a square matrix and $v$ be a vector that is not the all zeros vector (i.e., the vector with all entries equal to $0$).</span></span>

<span data-ttu-id="5b670-107">$ [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) $ $Mv = cv が $ いくつかの $c である場合、$v は $M の eigenvector であると言い $ ます。</span><span class="sxs-lookup"><span data-stu-id="5b670-107">We say $v$ is an [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) of  $M$ if $Mv = cv$ for some number $c$.</span></span> <span data-ttu-id="5b670-108">$C $ は、eigenvector $v に対応する[*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)です $ 。</span><span class="sxs-lookup"><span data-stu-id="5b670-108">We say $c$ is the [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) corresponding to the eigenvector $v$.</span></span> <span data-ttu-id="5b670-109">一般に、マトリックス $M は $ ベクターを他のベクターに変換することがありますが、eigenvector は特殊なので、数値で乗算される点を除いて、変更されません。</span><span class="sxs-lookup"><span data-stu-id="5b670-109">In general a matrix $M$ may transform a vector into any other vector, but an eigenvector is special because it is left unchanged except for being multiplied by a number.</span></span> <span data-ttu-id="5b670-110">$V $ が eigenvalue $c の eigenvector である場合 $ 、$av も、 $ 同じ eigenvalue を持つ eigenvector (0 以外のすべての $a) になり $ ます。</span><span class="sxs-lookup"><span data-stu-id="5b670-110">Note that if $v$ is an eigenvector with eigenvalue $c$, then $av$ is also an eigenvector (for any nonzero $a$) with the same eigenvalue.</span></span>

<span data-ttu-id="5b670-111">たとえば、id 行列の場合、すべてのベクター $v $ は eigenvalue $1 の eigenvector になり $ ます。</span><span class="sxs-lookup"><span data-stu-id="5b670-111">For example, for the identity matrix, every vector $v$ is an eigenvector with eigenvalue $1$.</span></span>

<span data-ttu-id="5b670-112">もう1つの例として、対角線に0以外のエントリのみがある[*対角線行列*](https://en.wikipedia.org/wiki/Diagonal_matrix)$D を考えてみ $ ます。</span><span class="sxs-lookup"><span data-stu-id="5b670-112">As another example, consider a [*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D$ which only has nonzero entries on the diagonal:</span></span>

<span data-ttu-id="5b670-113">$ $ \ begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="5b670-113">$$ \begin{bmatrix}</span></span>
<span data-ttu-id="5b670-114">d_1 & 0 & 0 \\ \\ 0 & d_2 & 0 \\ \\ 0 & 0 & d_3 \ end{ bmatrix } です。</span><span class="sxs-lookup"><span data-stu-id="5b670-114">d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="5b670-115">ベクター</span><span class="sxs-lookup"><span data-stu-id="5b670-115">The vectors</span></span>

<span data-ttu-id="5b670-116">$ $ \ begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \ end{ bmatrix } , & begin{ bmatrix } 0 \\ \\ 1 \\ \\ 0 \end { bmatrix } および \ begin{ bmatrix } 0 \\ \\ 0 \\ \\ 1 \end {bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="5b670-116">$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0\end{bmatrix} and \begin{bmatrix}0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span></span>

<span data-ttu-id="5b670-117">このマトリックスの固有ベクトルは、固有値 $d _1 $ 、$d _2 $ 、および $d、それぞれ3つ $ です。</span><span class="sxs-lookup"><span data-stu-id="5b670-117">are eigenvectors of this matrix with eigenvalues  $d_1$, $d_2$, and $d_3$, respectively.</span></span> <span data-ttu-id="5b670-118">$D _1 $ 、$d _2 $ 、および $d (_d $ ) が個別の数値の場合、これらのベクター (およびそのマルチプル) はマトリックス $D の唯一の固有ベクトル $ です。</span><span class="sxs-lookup"><span data-stu-id="5b670-118">If $d_1$, $d_2$, and $d_3$ are distinct numbers, then these vectors (and their multiples) are the only eigenvectors of the matrix $D$.</span></span> <span data-ttu-id="5b670-119">一般に、対角線マトリックスの場合は、固有値と固有ベクトルを簡単に読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="5b670-119">In general, for a diagonal matrix it is easy to read off the eigenvalues and eigenvectors.</span></span> <span data-ttu-id="5b670-120">固有値は、対角線に表示されるすべての数値であり、それぞれの固有ベクトルは1つのエントリが $1 $ 、残りのエントリが $0 に等しい単位ベクトルです $ 。</span><span class="sxs-lookup"><span data-stu-id="5b670-120">The eigenvalues are all the numbers appearing on the diagonal, and their respective eigenvectors are the unit vectors with one entry equal to $1$ and the remaining entries equal to $0$.</span></span>

<span data-ttu-id="5b670-121">上の例では、$D の固有ベクトルが $ $3 次元ベクターの基礎を形成していることに注意して $ ください。</span><span class="sxs-lookup"><span data-stu-id="5b670-121">Note in the above example that the eigenvectors of $D$ form a basis for $3$-dimensional vectors.</span></span> <span data-ttu-id="5b670-122">ベースはベクターのセットであり、ベクターを線形の組み合わせとして書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="5b670-122">A basis is a set of vectors such that any vector can be written as a linear combination of them.</span></span> <span data-ttu-id="5b670-123">より明示的には、$v _1 $ 、$v _2 $ 、および $v は、 $ $v 任意 $ $ の数の数値 $v _1 $ 、a_1 _2 $ 、v_1 として a_2 v_2 = a_3 v_3 + $a $a + $a として記述することができ $ ます。</span><span class="sxs-lookup"><span data-stu-id="5b670-123">More explicitly, $v_1$, $v_2$, and $v_3$ form a basis if any vector $v$ can be written as $v=a_1 v_1 + a_2 v_2 + a_3 v_3$ for some numbers $a_1$, $a_2$, and $a_3$.</span></span>

<span data-ttu-id="5b670-124">Hermitian matrix (自己 adjoint とも呼ばれます) は、独自の複雑な共役に相当する複雑な正方形行列であることを思い出してください。これに対して、1つのユニタリ行列は複雑な共役と同じ逆の四角形行列です。</span><span class="sxs-lookup"><span data-stu-id="5b670-124">Recall that a Hermitian matrix (also called self-adjoint) is a complex square matrix equal to its own complex conjugate, while a unitary matrix is a complex square matrix whose inverse is equal to its complex conjugate.</span></span>
<span data-ttu-id="5b670-125">実質的には、Hermitian およびユニタリマトリックスの場合は、クォンタムコンピューティングで検出された唯一のマトリックスで、次のことをアサートする、[*スペクトル定理*](https://en.wikipedia.org/wiki/Spectral_theorem)と呼ばれる一般的な結果があります。 Hermitian またはの $M マトリックスの場合は、 $ $ $M = U ^-ダガー D U ( $ 斜めのマトリックスの $D) が存在 $U し $ ます。</span><span class="sxs-lookup"><span data-stu-id="5b670-125">For Hermitian and unitary matrices, which are essentially the only matrices encountered in quantum computing, there is a general result known as the [*spectral theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), which asserts the following: For any Hermitian or unitary matrix $M$, there exists a unitary $U$ such that $M=U^\dagger D U$ for some diagonal matrix $D$.</span></span> <span data-ttu-id="5b670-126">さらに、$D の対角線のエントリは、 $ $M の値になり $ ます。</span><span class="sxs-lookup"><span data-stu-id="5b670-126">Furthermore, the diagonal entries of $D$ will be the eigenvalues of $M$.</span></span>

<span data-ttu-id="5b670-127">固有ベクトルの固有値とを計算する方法については既に説明して $ います $D。</span><span class="sxs-lookup"><span data-stu-id="5b670-127">We already know how to compute the eigenvalues and eigenvectors of a diagonal matrix $D$.</span></span> <span data-ttu-id="5b670-128">この定理を使用すると、$v $ が $ eigenvalue $c を持つ $D の場合 $ ($Dv = cv の場合)、$U $ ^ $ eigenvector は $ eigenvalue $M を持つ $c のになり $ ます。</span><span class="sxs-lookup"><span data-stu-id="5b670-128">Using this theorem we know that if $v$ is an eigenvector of $D$ with eigenvalue $c$, i.e., $Dv = cv$, then $U^\dagger v$ will be an eigenvector of $M$ with eigenvalue $c$.</span></span> <span data-ttu-id="5b670-129">これは、</span><span class="sxs-lookup"><span data-stu-id="5b670-129">This is because</span></span>

<span data-ttu-id="5b670-130">$ $M (U ^ \ ダガー v) = U ^ \ ダガー D U (U ^-ダガー v) = U ^ \ ダガー D (U U ^-ダガー) v = U ^-ダガー D v = c U ^ \ ダガー v. $ $</span><span class="sxs-lookup"><span data-stu-id="5b670-130">$$M(U^\dagger v) = U^\dagger D U  (U^\dagger v) =U^\dagger D (U  U^\dagger) v = U^\dagger D v = c U^\dagger v.$$</span></span>

## <a name="matrix-exponentials"></a><span data-ttu-id="5b670-131">マトリックス指数</span><span class="sxs-lookup"><span data-stu-id="5b670-131">Matrix Exponentials</span></span>
<span data-ttu-id="5b670-132">指数関数と完全に同じように[*行列指数*](https://en.wikipedia.org/wiki/Matrix_exponential)を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="5b670-132">A [*matrix exponential*](https://en.wikipedia.org/wiki/Matrix_exponential) can also be defined in exact analogy to the exponential function.</span></span>  <span data-ttu-id="5b670-133">マトリックス $A の行列指数は、 $ として表すことができます。</span><span class="sxs-lookup"><span data-stu-id="5b670-133">The matrix exponential of a matrix $A$ can be expressed as</span></span>

<span data-ttu-id="5b670-134">$ $ e ^ A/ = bold 完了 + A + \frac{A ^ 2 } {2!}+ \frac{A ^ 3 } {3!}+ \ cドット $ $</span><span class="sxs-lookup"><span data-stu-id="5b670-134">$$ e^A=\boldone + A + \frac{A^2}{2!}+\frac{A^3}{3!}+\cdots $$</span></span>

<span data-ttu-id="5b670-135">このことが重要なのは、クォンタムの機械的時間の進化は、$e ^ {iB } $ For Hermitian matrix $B という形式の1つの要素で構成され $ ます。</span><span class="sxs-lookup"><span data-stu-id="5b670-135">This is important because quantum mechanical time evolution is described by a unitary matrix of the form $e^{iB}$ for Hermitian matrix $B$.</span></span>  <span data-ttu-id="5b670-136">このため、matrix 指数の実行はクォンタムコンピューティングの基本的な部分であり、そのような Q # はこれらの操作を記述するための組み込みルーチンを提供しています。</span><span class="sxs-lookup"><span data-stu-id="5b670-136">For this reason, performing matrix exponentials is a fundamental part of quantum computing and as such Q# offers intrinsic routines for describing these operations.</span></span>
<span data-ttu-id="5b670-137">従来のコンピューターで行列指数を計算するには、多くの方法がありますが、通常は数値の近い数値でしかしが発生します。</span><span class="sxs-lookup"><span data-stu-id="5b670-137">There are many ways in practice to compute a matrix exponential on a classical computer, and in general numerically approximating such an exponential is fraught with peril.</span></span>  <span data-ttu-id="5b670-138">「 [*Cleve Moler とチャールズ Van ローン」を参照してください。"Nineteen あいまいにより、マトリックスの指数を計算することができます。"関連する課題の詳細については、「SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b670-138">See [*Cleve Moler and Charles Van Loan. "Nineteen dubious ways to compute the exponential of a matrix." SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) for more information about the challenges involved.</span></span>

<span data-ttu-id="5b670-139">マトリックスの指数を計算する方法を理解する最も簡単な方法は、そのマトリックスの固有値と固有ベクトルを使用することです。</span><span class="sxs-lookup"><span data-stu-id="5b670-139">The easiest way to understand how to compute the exponential of a matrix is through the eigenvalues and eigenvectors of that matrix.</span></span>  <span data-ttu-id="5b670-140">具体的に言うと、前に説明したスペクトル定理は、すべての Hermitian またはマトリックスに対して、$A の $U が存在し、 $ $ 斜線マトリックス $D $ $A = U ^-ダガー D U になっていることを示して $ います。 Unitarity ティのプロパティにより、$A ^ 2 = U ^ \ ダガー D ^ 2 U $ と同様に、任意の power $p $ $A ^ p = u ^ \ ダガー d ^ p u と同様になり $ ます。 これを演算子指数の演算子定義に置き換えると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5b670-140">Specifically, the spectral theorem discussed above says that for every Hermitian or unitary matrix $A$ there exists a unitary matrix $U$ and a diagonal matrix $D$ such that $A=U^\dagger D U$.  Because of the properties of unitarity we have that $A^2 = U^\dagger D^2 U$ and similarly for any power $p$ $A^p = U^\dagger D^p U$.  If we substitute this into the operator definition of the operator exponential we obtain:</span></span>

<span data-ttu-id="5b670-141">$ $ e ^ A = U ^ \ (& A)-左 (\ bold 完了 + D + \frac{D ^ 2 } {2!})+/cドット \ 右) U = u ^ & # 1 & 1 bmatrix } ; \ exp (D_ {11 } ) & 0 &/cdpi &0 \\\\ 0 & \ exp (D_ {22 } ) &/cドット 0 \ &/vドット & (& a) & & \\\\ \\\\ & & (&{NN } ) \ end{ bmatrix } U. $ $</span><span class="sxs-lookup"><span data-stu-id="5b670-141">$$ e^A= U^\dagger \left(\boldone +D +\frac{D^2}{2!}+\cdots \right)U= U^\dagger \begin{bmatrix}\exp(D_{11}) & 0 &\cdots &0\\\\ 0 & \exp(D_{22})&\cdots& 0\\\\ \vdots &\vdots &\ddots &\vdots\\\\ 0&0&\cdots&\exp(D_{NN}) \end{bmatrix} U. $$</span></span>

<span data-ttu-id="5b670-142">つまり、マトリックスの eigenbasis に変換する場合 $A 行列 $ 指数を計算することは、マトリックスの eigenbasis の通常の指数を計算することと同じです。</span><span class="sxs-lookup"><span data-stu-id="5b670-142">In other words, if you transform to the eigenbasis of the matrix $A$ then computing the matrix exponential is equivalent to computing the ordinary exponential of the eigenvalues of the matrix.</span></span>  <span data-ttu-id="5b670-143">クォンタムコンピューティングにおける多くの操作には、matrix 指数の実行が含まれています。そのため、マトリックスの eigenbasis に変換することにより、演算子指数が頻繁に表示されるようになり、このガイドの後半で説明する Trotter – Suzuki-スタイルのクォンタムシミュレーションメソッドなど、多くのクォンタムアルゴリズムが基礎となります。</span><span class="sxs-lookup"><span data-stu-id="5b670-143">As many operations in quantum computing involve performing matrix exponentials, this trick of transforming into the eigenbasis of a matrix to simplify performing the operator exponential appears frequently and is the basis behind many quantum algorithms such as Trotter–Suzuki-style quantum simulation methods discussed later in this guide.</span></span>

<span data-ttu-id="5b670-144">$B がユニタリと Hermitian の両方である場合は、もう1つの便利なプロパティがあり $ ます。つまり、$B = B ^ {-1 } = b ^ \ ダガーの $ 後 $B ^ 2/ = bold が終了 $ します。</span><span class="sxs-lookup"><span data-stu-id="5b670-144">Another useful property is if $B$ is both unitary and Hermitian, i.e., $B=B^{-1}=B^\dagger$ then $B^2=\boldone$.</span></span> <span data-ttu-id="5b670-145">上記のマトリックス指数の展開にこのルールを適用することにより、$/bold と $B の用語をまとめてグループ化することで $ $ 、id $x の任意の実数の値を確認できます。 $</span><span class="sxs-lookup"><span data-stu-id="5b670-145">By applying this rule to the above expansion of the matrix exponential and by grouping the $\boldone$ and the $B$ terms together, it can be see that for any real value $x$ the identity</span></span>

<span data-ttu-id="5b670-146">$ $e ^ {iBx } = \ bold 完了 \ cos (x) + ibx sin (x) $ $</span><span class="sxs-lookup"><span data-stu-id="5b670-146">$$e^{iBx}=\boldone \cos(x)+ iB\sin(x)$$</span></span>


<span data-ttu-id="5b670-147">収容.</span><span class="sxs-lookup"><span data-stu-id="5b670-147">holds.</span></span> <span data-ttu-id="5b670-148">この方法は特に便利です。これは、$B の次元が指数関数的に大きい場合でも、$B が Hermitian である場合に、特殊なケースでは、matrix 指数の操作に関する理由を理解できるためです $ $ 。</span><span class="sxs-lookup"><span data-stu-id="5b670-148">This trick is especially useful because it allows to reason about the actions matrix exponentials have, even if the dimension of $B$ is exponentially large, for the special case when $B$ is both unitary and Hermitian.</span></span>
