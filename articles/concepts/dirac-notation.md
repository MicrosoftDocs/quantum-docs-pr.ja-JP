---
title: ディラックの記法
description: Dirac 表記を使用して、クォンタムの状態を表し、クォンタム操作をシミュレートする方法について説明します。
author: QuantumWriter
uid: microsoft.quantum.concepts.dirac
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- $
- $
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
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: f9dddfa25e9fd1e3d8aaf92b2e3b17c96ed8b72a
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269508"
---
# <a name="dirac-notation"></a><span data-ttu-id="26d83-103">Dirac 表記</span><span class="sxs-lookup"><span data-stu-id="26d83-103">Dirac Notation</span></span>

<span data-ttu-id="26d83-104">列ベクトル表記は、線形代数では広く使用されていますが、多くの場合、特に複数の qubits を処理する場合、クォンタムコンピューティングでは煩雑です。</span><span class="sxs-lookup"><span data-stu-id="26d83-104">While column vector notation is ubiquitous in linear algebra, it is often cumbersome in quantum computing especially when dealing with multiple qubits.</span></span>  <span data-ttu-id="26d83-105">たとえば、$-psi をベクトルとして定義した場合、 $ $ \ psi $ が行または列のベクターであるかどうかは明示的に明確にはされません。</span><span class="sxs-lookup"><span data-stu-id="26d83-105">For example, when we define $\psi$ to be a vector it is not explicitly clear whether $\psi$ is a row or a column vector.</span></span>  <span data-ttu-id="26d83-106">したがって、$/phi と $-psi がベクターの場合、$ $ $ /phi $ と $-psi の形状が $ コンテキストで不明確になることがあるため、$-phi \ psi が定義されている場合にも、同様に不明確になり $ ます。</span><span class="sxs-lookup"><span data-stu-id="26d83-106">Thus if $\phi$ and $\psi$ are vectors then it is equally unclear if $\phi \psi$ is even defined because the shapes of $\phi$ and $\psi$ may be unclear in the context.</span></span>  <span data-ttu-id="26d83-107">ベクターの形状についてはあいまいではなく、前に紹介した線形代数表記を使用して単純なベクターを表現することは非常に面倒です。</span><span class="sxs-lookup"><span data-stu-id="26d83-107">Beyond the ambiguity about the shapes of vectors, expressing even simple vectors using the linear algebraic notation introduced earlier can be very cumbersome.</span></span> <span data-ttu-id="26d83-108">たとえば、 $ 各 qubit が値 $0 を受け取る $n qubit 状態を記述する場合は、 $ 状態を正式に次のように表現します。</span><span class="sxs-lookup"><span data-stu-id="26d83-108">For example, if we wish to describe an $n$-qubit state where each qubit takes the value $0$ then we would formally express the state as</span></span> 

<span data-ttu-id="26d83-109">$ $ \ begin{ bmatrix } 1 \\ \\ 0 & end{ bmatrix } \begin bmatrix } 1 \\ \\ 0 \ end{ bmatrix } です (& o)。</span><span class="sxs-lookup"><span data-stu-id="26d83-109">$$\begin{bmatrix}1 \\\\  0 \end{bmatrix}\otimes \cdots \otimes\begin{bmatrix}1 \\\\  0 \end{bmatrix}.</span></span> $$  

<span data-ttu-id="26d83-110">ベクターは指数関数的に大きくなるため、このような製品を評価するのは現実的ではありません。この表記は、実際には、前の表記法を使用して指定できる状態の最適な説明です。</span><span class="sxs-lookup"><span data-stu-id="26d83-110">Of course evaluating this tensor product is impractical because the vector lies in an exponentially large space and so this notation is in fact the best description of the state that can be given using the previous notation.</span></span>  

<span data-ttu-id="26d83-111">[*Dirac 表記*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation)では、クォンタム機構の正確なニーズに合わせて新しい言語を提示することで、これらの問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="26d83-111">[*Dirac notation*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) solves these issues by presenting a new language to fit the precise needs of quantum mechanics.</span></span>  <span data-ttu-id="26d83-112">このため、このセクションの例は、クォンタムの状態を記述する方法を厳密に説明することをお勧めしませんが、クォンタムのアイデアを簡潔に表現するための提案として閲覧者に伝えることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="26d83-112">For this reason, we recommend the reader not view the examples in this section as a rigid prescription of how to describe quantum states, but rather encourage the reader to view these as suggestions that can be used to concisely express quantum ideas.</span></span>

<span data-ttu-id="26d83-113">Dirac 表記には、 *bra* vector と*k* vector という2種類のベクトルがあります。これは、一緒に配置すると、 *braket*または内部の製品を形成するためです。</span><span class="sxs-lookup"><span data-stu-id="26d83-113">There are two types of vectors in Dirac notation: the *bra* vector and the *ket* vector, so named because when put together they form a *braket* or inner product.</span></span>  <span data-ttu-id="26d83-114">$ \ Psi $ が列ベクターの場合は、Dirac 表記で $ \ket \ psi $ として書き込むことができます { } 。 $ \ket/ { cdot $ は、 } これが unit 列ベクトル (つまり、 *k* vector) であることを示します。</span><span class="sxs-lookup"><span data-stu-id="26d83-114">If $\psi$ is a column vector then we can write it in Dirac notation as $\ket{\psi}$, where the $\ket{\cdot}$ denotes that it is a unit column vector, i.e., a *ket* vector.</span></span>  <span data-ttu-id="26d83-115">同様に、行ベクター $ \ psi ^ \ ダガー $ は $ \bra/psi $ として表され { } ます。</span><span class="sxs-lookup"><span data-stu-id="26d83-115">Similarly, the row vector $\psi^\dagger$ is expressed as $\bra{\psi}$.</span></span> <span data-ttu-id="26d83-116">つまり、$-psi $ の転置の要素にエントリごとに複雑な活用形を適用することで、$/psi ^ を取得 $ できます。</span><span class="sxs-lookup"><span data-stu-id="26d83-116">In other words, $\psi^\dagger$ is obtained by applying entry-wise complex conjugation to the elements of the transpose of $\psi$.</span></span> <span data-ttu-id="26d83-117">Bra k 記法は、$ \braket-psi { | \ psi } $ がそれ自体を持つ vector $ \ psi の内部積であることを意味し $ ます。これは、定義 $1 によって決まり $ ます。</span><span class="sxs-lookup"><span data-stu-id="26d83-117">The bra-ket notation directly implies that $\braket{\psi|\psi}$ is the inner product of vector $\psi$ with itself, which is by definition $1$.</span></span>  

<span data-ttu-id="26d83-118">一般的に、$ \ psi $ と $/phi $ がクォンタム状態ベクトルの場合、内部製品は $ \braket { \ phi | \ psi } $ となります。これは、state $ \ket { \ psi } $ を $ \ket/phi $ に測定する確率が { } $ | \braket/ { phi | } | ^ 2 $ であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="26d83-118">More generally, if $\psi$ and $\phi$ are quantum state vectors their inner product is $\braket{\phi|\psi}$ which implies that the probability of measuring the state $\ket{\psi}$ to be $\ket{\phi}$ is $|\braket{\phi|\psi}|^2$.</span></span>  

<span data-ttu-id="26d83-119">次の規則は、0と1の値をエンコードするクォンタムの状態を記述するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="26d83-119">The following convention is used to describe the quantum states that encode the values of zero and one (the single-qubit computational basis states):</span></span>

<span data-ttu-id="26d83-120">$ $ \ begin{ bmatrix } 1 \\ \\ 0 \ end{ bmatrix } = \ket{0 } , \qquad \ begin{ bmatrix } 0 \\ \\ 1 \ end{ bmatrix } = \ket{1 } .</span><span class="sxs-lookup"><span data-stu-id="26d83-120">$$ \begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \ket{0},\qquad \begin{bmatrix} 0 \\\\  1 \end{bmatrix} = \ket{1}.</span></span>
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a><span data-ttu-id="26d83-121">例: Dirac 表記を使用した Hadamard 操作の表現</span><span class="sxs-lookup"><span data-stu-id="26d83-121">Example: representing the Hadamard operation with Dirac notation</span></span>

<span data-ttu-id="26d83-122">次の表記は、Hadamard ゲートを $ \ket{0 $ および $ \ket{1 $ に適用した結果として得られる状態を示すためによく使用され } } ます (これは、Bloch 球の $ + x と $ x の方向の単位ベクトルに対応し $ $ ます)。</span><span class="sxs-lookup"><span data-stu-id="26d83-122">The following notation is often used to describe the states that result from applying the Hadamard gate to $\ket{0}$ and $\ket{1}$ (which correspond to the unit vectors in the $+x$ and $-x$ directions on the Bloch sphere):</span></span>

<span data-ttu-id="26d83-123">$ $ \frac{1 } {\ sqrt{2 } } \ begin{ bmatrix } 1 \\ \\ 1 & end{ bmatrix } = h \ket {0 } = \ket { +}, \qquad \frac{1 } {\ sqrt{2 } } \ begin{ bmatrix } 1 \\ \\ -1, end{ bmatrix } = H \ket {1 } = \ket { }.</span><span class="sxs-lookup"><span data-stu-id="26d83-123">$$ \frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  1 \end{bmatrix}=H\ket{0} = \ket{+},\qquad \frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  -1 \end{bmatrix} =H\ket{1} = \ket{-} .</span></span>
$$

<span data-ttu-id="26d83-124">これらの状態は、Dirac 表記を使用して、$ \ket{0 } $ と $ \ket{1 $ の合計として拡張することもでき } ます。</span><span class="sxs-lookup"><span data-stu-id="26d83-124">These states can also be expanded using Dirac notation as sums of $\ket{0}$ and $\ket{1}$:</span></span>

<span data-ttu-id="26d83-125">$ $ \ket { +} = \frac{1 } {\ sqrt{2 } } (\ket{0 } + \ket{1 } )、\qquad \ket { -} = \frac{1 } {\ sqrt{2 } } (\ket{0 } -\ket{1 } )。</span><span class="sxs-lookup"><span data-stu-id="26d83-125">$$ \ket{+} = \frac{1}{\sqrt{2}}(\ket{0} + \ket{1}),\qquad \ket{-} = \frac{1}{\sqrt{2}}(\ket{0} - \ket{1}).</span></span>
$$

### <a name="computational-basis-vectors"></a><span data-ttu-id="26d83-126">計算ベースベクター</span><span class="sxs-lookup"><span data-stu-id="26d83-126">Computational basis vectors</span></span>
<span data-ttu-id="26d83-127">これは、これらの状態がしばしば*コンピューティングベース*と呼ばれる理由を示しています。すべてのクォンタム状態は常に計算ベースベクターの合計として表現でき、そのような合計は dirac 表記を使用して簡単に表現できます。</span><span class="sxs-lookup"><span data-stu-id="26d83-127">This demonstrates why these states are often called a *computational basis*: every quantum state can always be expressed as sums of computational basis vectors and such sums are easily expressed using Dirac notation.</span></span>  <span data-ttu-id="26d83-128">また、この逆も同様です。これは、 { "$ \ket +} $ { " と "$ \ket-} $" がクォンタム状態の基準となることもあります。</span><span class="sxs-lookup"><span data-stu-id="26d83-128">The converse is also true in that the states $\ket{+}$ and $\ket{-}$ also form a basis for quantum states.</span></span>  <span data-ttu-id="26d83-129">これは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="26d83-129">You can see this from the fact that</span></span>

<span data-ttu-id="26d83-130">$ $ \ket{0 } = \frac{1 } {\ sqrt{2 } } (\ket { +} + \ket { -})、\qquad \ket{1 } = \frac{1 } {\ sqrt{2 } } (\ket { +}-\ket { -})。</span><span class="sxs-lookup"><span data-stu-id="26d83-130">$$ \ket{0} = \frac{1}{\sqrt{2}}(\ket{+} + \ket{-}),\qquad \ket{1} = \frac{1}{\sqrt{2}}(\ket{+} - \ket{-}).</span></span>
$$

<span data-ttu-id="26d83-131">Dirac 表記の例として、$0 ~ $1 の内部積である braket $ \braket{0 | 1 $ について考えてみ } $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="26d83-131">As an example of Dirac notation, consider the braket $\braket{0 | 1}$, which is the inner product between $0$ and $1$.</span></span>  <span data-ttu-id="26d83-132">このファイルは、</span><span class="sxs-lookup"><span data-stu-id="26d83-132">It can be written as</span></span> 

<span data-ttu-id="26d83-133">$ $ \braket{0 | 1 } = \ begin{ bmatrix } 1 & 0 \ end{ bmatrix } \ begin{ bmatrix } 0 \\\\ 1 \end{bmatrix} = 0. $ $</span><span class="sxs-lookup"><span data-stu-id="26d83-133">$$\braket{0 | 1}=\begin{bmatrix} 1 & 0 \end{bmatrix}\begin{bmatrix}0\\\\ 1\end{bmatrix}=0.$$</span></span>

<span data-ttu-id="26d83-134">これは、$ \ket{0 } $ と $ \ket{1 } $ が直交ベクトルであることを示しています。これは、$ \braket{0 | 1 } = \braket{1 | 0 = 0 であることを意味 } $ します。</span><span class="sxs-lookup"><span data-stu-id="26d83-134">This says that $\ket{0}$ and $\ket{1}$ are orthogonal vectors, meaning that $\braket{0 | 1} = \braket{1 | 0} =0$.</span></span>  <span data-ttu-id="26d83-135">また、definition $ \braket{0 | 0 } = \braket{1 | 1 } = 1 でもあり $ ます。これは、2つの計算ベースベクトルを*orthonormal*として呼び出すことができることを意味します。</span><span class="sxs-lookup"><span data-stu-id="26d83-135">Also by definition $\braket{0 | 0} = \braket{1 | 1}=1$, which means that the two computational basis vectors can also be called *orthonormal*.</span></span>
<span data-ttu-id="26d83-136">これらの orthonormal プロパティは、次の例で役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="26d83-136">These orthonormal properties will be useful in the following example.</span></span> <span data-ttu-id="26d83-137">状態が $ \ket { \ psi } = {\frac{3 } {5} } \ket{1 } + {\frac{4 } {5 } } \ket{0 } $ の場合、$ \braket{1 | 0 = 0 であるため } $ 、$1 を測定する確率 $ は</span><span class="sxs-lookup"><span data-stu-id="26d83-137">If we have a state $\ket{\psi} = {\frac{3}{5}} \ket{1} + {\frac{4}{5}} \ket{0}$ then because $\braket{1 | 0} =0$ the probability of measuring $1$  is</span></span>  

<span data-ttu-id="26d83-138">$ $ \ big | \braket{1 | \ psi } \ big | ^ 2 = \ left | \frac{3 } {5 } \braket{1 | 1 } + \frac{4 } {5 } \braket{1 | 0 } \ right | ^ 2 = \frac{9 } {25 } . $ $</span><span class="sxs-lookup"><span data-stu-id="26d83-138">$$\big|\braket{1 | \psi}\big|^2= \left|\frac{3}{5}\braket{1 | 1} +\frac{4}{5}\braket{1 | 0}\right|^2=\frac{9}{25}.$$</span></span> 

### <a name="tensor-product-notation"></a><span data-ttu-id="26d83-139">その他の製品表記</span><span class="sxs-lookup"><span data-stu-id="26d83-139">Tensor product notation</span></span>
<span data-ttu-id="26d83-140">Dirac 表記には、その中に、暗黙的な、または製品構造も含まれています。</span><span class="sxs-lookup"><span data-stu-id="26d83-140">Dirac notation also includes an implicit tensor product structure within it.</span></span>  <span data-ttu-id="26d83-141">これは、クォンタムコンピューティングでは、2つの非相関クォンタムレジスタによって記述された状態ベクトルが2つの状態ベクトルの3つの状態ベクトルに含まれるため、重要です。</span><span class="sxs-lookup"><span data-stu-id="26d83-141">This is important because in quantum computing, the state vector described by two uncorrelated quantum registers is the tensor products of the two state vectors.</span></span>  <span data-ttu-id="26d83-142">クォンタムの計算について説明する場合は、その製品構造を簡潔に説明したり、その構造を簡潔に記述したりすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="26d83-142">Concisely describing the tensor product structure, or lack thereof, is vital if you want to explain a quantum computation.</span></span>  <span data-ttu-id="26d83-143">これは、 $ すべての2つのクォンタム状態ベクトル $ $ /phi と $/psi を $ \ket/psi \ket として作成できることを意味し $ ます。ただし、$ \ket/psi/phi $ として明示的に記述されている場合も { } { } あり { } { } $ ますが、ベクター間での $ otimes の記述は不要です。</span><span class="sxs-lookup"><span data-stu-id="26d83-143">The tensor product structure implies that we can write $\psi \otimes \phi$ for any two quantum state vectors $\phi$ and $\psi$ as $\ket{\psi} \ket{\phi}$, sometimes explicitly written as $\ket{\psi} \otimes \ket{\phi}$, however by convention writing $\otimes$ in between the vectors is unnecessary.</span></span>  <span data-ttu-id="26d83-144">たとえば、2つの qubits がゼロ状態に初期化された状態は、</span><span class="sxs-lookup"><span data-stu-id="26d83-144">For example, the state with two qubits initialized to the zero state is given by</span></span>

<span data-ttu-id="26d83-145">$ $ \ begin{ bmatrix } 1 \\ \\ 0 0 \\ \\ \\ \\ 0 \ end{ bmatrix } = \ begin{ bmatrix } 1 \\ \\ 0 & end{/ bmatrix } otimes \ begin{ bmatrix } 1 \\ \\ 0 \ end{ bmatrix } = \ket{0/ } otimes \ket{0 } = \ket{0 } \ket{0 } です。</span><span class="sxs-lookup"><span data-stu-id="26d83-145">$$ \begin{bmatrix} 1 \\\\  0 \\\\  0 \\\\  0 \end{bmatrix}= \begin{bmatrix} 1 \\\\  0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \ket{0} \otimes \ket{0}= \ket{0} \ket{0}.</span></span>
$$

<span data-ttu-id="26d83-146">同様に、整数 $p の状態 $ \ket{p $ は、 } $ $p 整数をバイナリ表現でエンコードするクォンタム状態を表し $ ます。</span><span class="sxs-lookup"><span data-stu-id="26d83-146">Similarly,  the state $\ket{p}$ for integer $p$ represents a quantum state that encodes in binary representation the integer $p$.</span></span>  <span data-ttu-id="26d83-147">たとえば、 $ 符号なしのバイナリエンコーディングを使用して数値 $5 を表現する場合は、次のように表現することもできます。</span><span class="sxs-lookup"><span data-stu-id="26d83-147">For example, if we wish to express the number $5$ using an unsigned binary encoding we could equally express it as</span></span>

<span data-ttu-id="26d83-148">$ $ \ket{1 } \ket{0 } \ket{1 } = \ket{101 } = \ket{5 } .</span><span class="sxs-lookup"><span data-stu-id="26d83-148">$$ \ket{1}\ket{0}\ket{1} = \ket{101} = \ket{5}.</span></span>
$$

<span data-ttu-id="26d83-149">この記法では、$ \ket{0 } $ は単 qubit 状態を参照する必要はありませんが、$0 のバイナリエンコードを格納する*qubit レジスタ*を必要とし $ ます。</span><span class="sxs-lookup"><span data-stu-id="26d83-149">Within this notation $\ket{0}$ need not refer to a single-qubit state but rather a *qubit register* storing a binary encoding of $0$.</span></span>  <span data-ttu-id="26d83-150">これら2つの表記の違いは、通常、コンテキストから明らかになります。</span><span class="sxs-lookup"><span data-stu-id="26d83-150">The differences between these two notations is usually clear from the context.</span></span>  <span data-ttu-id="26d83-151">この規則は、次のいずれかの方法で記述できる最初の例を簡略化するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="26d83-151">This convention is useful for simplifying the first example which can be written in any of the following ways:</span></span>

<span data-ttu-id="26d83-152">$ $ \ begin{ bmatrix } 1 \\ \\ 0 & end{ bmatrix } \ otimes \ cドット/otimes \begin { bmatrix } 1 \\ \\ 0 \ end{ bmatrix } = \ket{0 } \ket{0 } = | 0 \cdots 0 \rangle = \ket{0 } ^ {/otimes n } = \ket{0 } です (& o)。</span><span class="sxs-lookup"><span data-stu-id="26d83-152">$$ \begin{bmatrix}1 \\\\  0 \end{bmatrix}\otimes \cdots \otimes\begin{bmatrix}1 \\\\  0 \end{bmatrix} = \ket{0} \otimes \cdots \otimes \ket{0}= |0\cdots 0\rangle = \ket{0}^{\otimes n} = \ket{0}.</span></span>
$$

### <a name="example-describing-superposition-with-dirac-notation"></a><span data-ttu-id="26d83-153">例: Dirac 表記で法則を記述する</span><span class="sxs-lookup"><span data-stu-id="26d83-153">Example: Describing superposition with Dirac notation</span></span>
<span data-ttu-id="26d83-154">Dirac 表記を使用してクォンタムの状態を記述するもう1つの例として、次のように同等のクォンタム状態を記述する方法を検討してください。これは、法則になる可能性のあるすべてのビット文字列に対して同じである必要があり $n$</span><span class="sxs-lookup"><span data-stu-id="26d83-154">As another example of how you can use Dirac notation to describe a quantum state, consider the following equivalent ways of writing a quantum state that is an equal superposition over every possible bit string of length $n$</span></span>

<span data-ttu-id="26d83-155">$ $ H ^ {\ otimes n } \ket{0 } = \frac{1 } {2 ^ {n/2 } } \ sum_ {j = 0 } ^ {2 ^ n-1 } \ket{j } = \ket { +} ^ {/otimes n } .</span><span class="sxs-lookup"><span data-stu-id="26d83-155">$$ H^{\otimes n} \ket{0} = \frac{1}{2^{n/2}} \sum_{j=0}^{2^n-1} \ket{j} = \ket{+}^{\otimes n}.</span></span>
$$

<span data-ttu-id="26d83-156">ここで、合計が $0 から $ $ 2 ^ {n } -1 $ の $n ビットになるのはなぜですか $ 。</span><span class="sxs-lookup"><span data-stu-id="26d83-156">Here you may wonder why the sum goes from $0$ to $2^{n}-1$ for $n$ bits.</span></span>  <span data-ttu-id="26d83-157">まず、$n ビットには、$ 2 ^ {n $ の異なる構成があることに注意 } $ してください。</span><span class="sxs-lookup"><span data-stu-id="26d83-157">First note that there are $2^{n}$ different configurations that $n$ bits can take.</span></span>  <span data-ttu-id="26d83-158">これは、1つのビットが $2 の値を受け取ることはでき $ ますが、2つのビットが $4 の値を受け取る可能性があることに注意してください $ 。</span><span class="sxs-lookup"><span data-stu-id="26d83-158">You can see this by noting that one bit can take $2$ values but two bits can take $4$ values and so forth.</span></span> <span data-ttu-id="26d83-159">一般に、これは、$ 2 ^ n 異なる可能性のあるビット文字列がありますが、 $ $1 \cdots 1 = 2 ^ n-1 でエンコードされた最大値であるため、合計の上限になり $ ます。</span><span class="sxs-lookup"><span data-stu-id="26d83-159">In general, this means that there are $2^n$ different possible bit strings but the largest value encoded in any of them $1\cdots 1=2^n-1$ and hence it is the upper limit for the sum.</span></span>
<span data-ttu-id="26d83-160">この例では、$ \ket { +} ^ {\ otimes n } = \ket { +} $ を $ \ket{0 ^ {\ otimes n = \ket{0 $ と同じように使用していません } } } 。この数値表記規約は、通常、すべての qubit が0に初期化されています。</span><span class="sxs-lookup"><span data-stu-id="26d83-160">As a side note, in this example we did not use $\ket{+}^{\otimes n}=\ket{+}$ in analogy to $\ket{0}^{\otimes n} = \ket{0}$ because this notational convention is usually reserved for the computational basis state with every qubit initialized to zero.</span></span>  <span data-ttu-id="26d83-161">このような規則は、この場合には実用的なものですが、クォンタムコンピューティングの資料には採用されていません。</span><span class="sxs-lookup"><span data-stu-id="26d83-161">While such a convention would be sensible in this case, it is not employed in the quantum computing literature.</span></span>

### <a name="expressing-linearity-with-dirac-notation"></a><span data-ttu-id="26d83-162">Dirac 表記を使用した直線性の表現</span><span class="sxs-lookup"><span data-stu-id="26d83-162">Expressing linearity with Dirac notation</span></span>
<span data-ttu-id="26d83-163">Dirac 表記のもう1つの優れた機能は、これが線形であるということです。</span><span class="sxs-lookup"><span data-stu-id="26d83-163">Another nice feature of Dirac notation is the fact that it is linear.</span></span>  <span data-ttu-id="26d83-164">4つのクォンタム状態ベクトルに対して書き込みを行う場合は、</span><span class="sxs-lookup"><span data-stu-id="26d83-164">If we wish to write for any four quantum state vectors,</span></span> 

<span data-ttu-id="26d83-165">$ $ (\ alpha \ket { \ psi } + \ ベータ \ket { } ) \ otimes (\ gamma \ket { \ カイ } + \ delta \ket- { オメガ } ) = \ alpha \ket/ \gamma psi \ket/ { } { カイ +- } alpha \ket/ \delta psi \ket/ { } { オメガ } \gamma \ket { } { } \delta \ket { } { } +-beta/phi \ket/カイ +/ベータ/phi \ket \</span><span class="sxs-lookup"><span data-stu-id="26d83-165">$$(\alpha \ket{\psi} +\beta\ket{\phi})\otimes (\gamma \ket{\chi} + \delta \ket{\omega})= \alpha\gamma \ket{\psi}\ket{\chi} + \alpha\delta \ket{\psi}\ket{\omega}+\beta\gamma\ket{\phi}\ket{\chi}+\beta\delta\ket{\phi}\ket{\omega}.$$</span></span>

<span data-ttu-id="26d83-166">つまり、状態ベクター間での整理された製品の作成が通常の乗算と同じになるように、「Dirac 表記」で、「」という表記を配布することができます。</span><span class="sxs-lookup"><span data-stu-id="26d83-166">That is to say, you can distribute the tensor product notation in Dirac notation so that taking tensor products between state vectors ends up looking just like ordinary multiplication.</span></span>

<span data-ttu-id="26d83-167">Bra ベクターは、k ベクターと同様の規則に従います。</span><span class="sxs-lookup"><span data-stu-id="26d83-167">Bra vectors follow a similar convention to ket vectors.</span></span>  <span data-ttu-id="26d83-168">たとえば、vector $ \bra { \ psi \bra/ } { phi } $ は、state vector $ \ psi ^ \ ダガー-otimes/phi ^-ダガー (-psi- = \otimes phi) ^/ダガーと同等です $ 。</span><span class="sxs-lookup"><span data-stu-id="26d83-168">For example, the vector $\bra{\psi}\bra{\phi}$ is equivalent to the state vector $\psi^\dagger \otimes \phi^\dagger=(\psi\otimes \phi)^\dagger$.</span></span> <span data-ttu-id="26d83-169">K vector $ \ket { \ psi } $ が $ \ alpha \ket{0 } + \ beta \ket{1 $ の場合、 } ベクターの bra vector バージョンは $ \bra { \ psi } = \ket/ { psi } ^ \ ダガー = (- } al/alpha ^ \* +-al{1} } \*) $ になります。</span><span class="sxs-lookup"><span data-stu-id="26d83-169">If the ket vector $\ket{\psi}$ is $\alpha \ket{0} + \beta \ket{1}$ then the bra vector version of the vector is $\bra{\psi}=\ket{\psi}^\dagger = (\bra{0}\alpha^\* +\bra{1}\beta^\*)$.</span></span>

<span data-ttu-id="26d83-170">例として、状態 { } } } } } } } を $ \ket{0 { +} $ または $ \ket-} $ として測定するために、クォンタムプログラムを使用して、$ \ket \ psi = \frac{3 {5 \ket{1 + \frac{4 {5 \ket $ という { 状態を測定する確率を計算したいとします。</span><span class="sxs-lookup"><span data-stu-id="26d83-170">As an example, imagine that we wish to calculate the probability of measuring the state $\ket{\psi} = \frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}$ using a quantum program for measuring states to be either $\ket{+}$ or $\ket{-}$.</span></span> <span data-ttu-id="26d83-171">デバイスが出力する確率は、状態が $ \ket-} $ であることを { 示します。</span><span class="sxs-lookup"><span data-stu-id="26d83-171">Then the probability that the device would output that the state is $\ket{-}$ is</span></span> 

<span data-ttu-id="26d83-172">$ $ | \braket { -| \ psi } | ^ 2 = \ 左 | \frac{1 } {\ sqrt{2 } } (& b) ( } } \frac{3 } {5 } \ket{1 } + \frac{4 } {5 } \ket{0 } ) \ right ^ 2 \ \frac{3 {5 { | = | } \sqrt 2 } } + \frac{4 } {5 \sqrt {2 } } \ 右 | ^ 2 = \frac{1 { } 50 } . $ $</span><span class="sxs-lookup"><span data-stu-id="26d83-172">$$|\braket{- | \psi}|^2= \left|\frac{1}{\sqrt{2}}(\bra{0} - \bra{1})(\frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}) \right|^2=\left|-\frac{3}{5\sqrt{2}} + \frac{4}{5\sqrt{2}}\right|^2=\frac{1}{50}.$$</span></span>

<span data-ttu-id="26d83-173">確率の計算で負の符号が表示されるのは、クォンタムの干渉の取り組みです。これは、クォンタムコンピューティングが古典的なコンピューティングよりも優れているというメカニズムの1つです。</span><span class="sxs-lookup"><span data-stu-id="26d83-173">The fact that the negative sign appears in the calculation of the probability is a manifestation of quantum interference, which is one of the mechanisms by which quantum computing gains advantages over classical computing.</span></span>

## <a name="ketbra-or-outer-product"></a><span data-ttu-id="26d83-174">ketbra または外側の製品</span><span class="sxs-lookup"><span data-stu-id="26d83-174">ketbra or outer product</span></span>
<span data-ttu-id="26d83-175">Dirac 表記で説明する最後の項目は、 *ketbra*または outer 製品です。</span><span class="sxs-lookup"><span data-stu-id="26d83-175">The final item worth discussing in Dirac notation is the *ketbra* or outer product.</span></span>  <span data-ttu-id="26d83-176">外側の製品は、Dirac 表記では $ \ket { \ psi \bra \ phi $ として表され、 } { } bras と kets は brakets と逆の順序で発生するため、ketbras と呼ばれることもあります。</span><span class="sxs-lookup"><span data-stu-id="26d83-176">The outer product is represented within Dirac notations as $\ket{\psi} \bra{\phi}$, and sometimes called ketbras because the bras and kets occur in the opposite order as brakets.</span></span>  <span data-ttu-id="26d83-177">外側の製品は、マトリックス乗算を使用して、 { } { } $ クォンタム状態ベクトル $ \ psi と $ phi の $ \ket \ psi \bra/phi = \ psi \ phi ^ \ ダガーと $ して定義され $ ます。</span><span class="sxs-lookup"><span data-stu-id="26d83-177">The outer product is defined via matrix multiplication as $\ket{\psi} \bra{\phi} = \psi \phi^\dagger$ for quantum state vectors $\psi$ and $\phi$.</span></span>  <span data-ttu-id="26d83-178">この表記法の最も単純で最も一般的な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="26d83-178">The simplest, and arguably most common example of this notation, is</span></span>

<span data-ttu-id="26d83-179">$ $ \ket{0/\qquad } } = \ begin{ bmatrix } 1 \\\\ 0 \ end{ bmatrix } \ begin{ bmatrix } 1&0 \ end{ bmatrix } = \ begin{ bmatrix } 1 &0 0 &0 \ket{1/end{/begin{} 0 \\\\ \end{bmatrix} } } bmatrix \\\\ bmatrix } bmatrix&1 & end{= \ begin{} 0 bmatrix } bmatrix &0 \\\\ 0 &1 \end{bmatrix} . です。</span><span class="sxs-lookup"><span data-stu-id="26d83-179">$$ \ket{0} \bra{0} = \begin{bmatrix}1\\\\ 0 \end{bmatrix}\begin{bmatrix}1&0 \end{bmatrix}= \begin{bmatrix}1 &0\\\\ 0 &0\end{bmatrix} \qquad \ket{1} \bra{1} = \begin{bmatrix}0\\\\ 1 \end{bmatrix}\begin{bmatrix}0&1 \end{bmatrix}= \begin{bmatrix}0 &0\\\\ 0 &1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="26d83-180">Ketbras は、クォンタム状態を固定値に射影するため、多くの場合、プロジェクターと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="26d83-180">Ketbras are often called projectors because they project a quantum state onto a fixed value.</span></span>  <span data-ttu-id="26d83-181">これらの操作は、(ベクターの基準を維持するのではなく)、また、クォンタムコンピューターがプロジェクターを確定的に適用できないということではありません。</span><span class="sxs-lookup"><span data-stu-id="26d83-181">Since these operations are not unitary (and do not even preserve the norm of a vector), it should come as no surprise that a quantum computer cannot deterministically apply a projector.</span></span>  <span data-ttu-id="26d83-182">しかし、プロジェクターは、クォンタムの状態に対して測定されるアクションを記述する美しいジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="26d83-182">However projectors do a beautiful job of describing the action that measurement has on a quantum state.</span></span>  <span data-ttu-id="26d83-183">たとえば、$ \ket \ psi $ という状態を $0 に測定した場合、 { } 状態が $ 測定の結果として得られる変換は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="26d83-183">For example, if we measure a state $\ket{\psi}$ to be $0$ then the resulting transformation that the state experiences as a result of the measurement is</span></span>

  <span data-ttu-id="26d83-184">$ $ \ket { \ psi } \rightarrow \ frac { (\ket{0/ } } ) \ket/ { psi } } {| \braket{0 | \ psi } |}= \ket{0 } 、$ $</span><span class="sxs-lookup"><span data-stu-id="26d83-184">$$\ket{\psi} \rightarrow \frac{(\ket{0} \bra{0})\ket{\psi}}{|\braket{0 | \psi}|}= \ket{0},$$</span></span>

<span data-ttu-id="26d83-185">これは、状態を測定して $ \ket{0 $ として検出した場合に想定し } ます。</span><span class="sxs-lookup"><span data-stu-id="26d83-185">as one expects if you were to measure the state and find it to be $\ket{0}$.</span></span>  <span data-ttu-id="26d83-186">繰り返しますが、このようなプロジェクターは、クォンタムコンピューターの状態に対して確定的には適用できません。</span><span class="sxs-lookup"><span data-stu-id="26d83-186">To reiterate, such projectors cannot be applied on a state in a quantum computer deterministically.</span></span>  <span data-ttu-id="26d83-187">代わりに、 } いくつかの固定確率で表示される結果 $ \ket{0 $ を使用して、ランダムに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="26d83-187">Instead, they can at best be applied randomly with the result $\ket{0}$ appearing with some fixed probability.</span></span>  <span data-ttu-id="26d83-188">このような測定値の確率は、その状態のクォンタムプロジェクターの予測値として記述できます。</span><span class="sxs-lookup"><span data-stu-id="26d83-188">The probability of such a measurement succeeding can be written as the expectation value of the quantum projector in the state</span></span>

<span data-ttu-id="26d83-189">$ $ \bra { \ psi } (\ket{0 } } /) \ket { /psi } = | \braket { \ psi | 0 } | ^ 2, $ $</span><span class="sxs-lookup"><span data-stu-id="26d83-189">$$ \bra{\psi} (\ket{0} \bra{0})\ket{\psi} = |\braket{\psi | 0}|^2, $$</span></span>

<span data-ttu-id="26d83-190">つまり、プロジェクターは測定プロセスを表現する新しい方法を提供しています。</span><span class="sxs-lookup"><span data-stu-id="26d83-190">which illustrates that projectors simply give a new way of expressing the measurement process.</span></span>

<span data-ttu-id="26d83-191">代わりに、マルチ qubit 状態の最初の qubit を $1 に測定することを検討する場合は、 $ プロジェクターと Dirac 表記を使用して、このプロセスを簡単に記述することもできます。</span><span class="sxs-lookup"><span data-stu-id="26d83-191">If instead we consider measuring the first qubit of a multi-qubit state to be $1$ then we can also describe this process conveniently using projectors and Dirac notation:</span></span>

<span data-ttu-id="26d83-192">$ $ P (\ text{first qubit = 1 } ) = \bra { } (\ket{1 } } ) \ket/psi (} {/otimes n-1 } \ right) { \ psi } です。</span><span class="sxs-lookup"><span data-stu-id="26d83-192">$$ P(\text{first qubit = 1})= \bra{\psi}\left(\ket{1}\bra{1}\otimes \boldone^{\otimes n-1}\right) \ket{\psi}.</span></span>
$$

<span data-ttu-id="26d83-193">ここでは、id 行列を Dirac 表記で簡単に記述できます。</span><span class="sxs-lookup"><span data-stu-id="26d83-193">Here the identity matrix can be conveniently written in Dirac notation as</span></span>

<span data-ttu-id="26d83-194">$ $ \ \ket{1 done = \ket{0 } \ ロウ } } } { bmatrix } 1&0 \\\\ 0&1 & end{ですが、このように bmatrix } なります。</span><span class="sxs-lookup"><span data-stu-id="26d83-194">$$ \boldone = \ket{0} \bra{0}+\ket{1} \bra{1}= \begin{bmatrix}1&0\\\\ 0&1 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="26d83-195">2つの場合、プロジェクターは次のように拡張できます。</span><span class="sxs-lookup"><span data-stu-id="26d83-195">For the case where there are two-qubits the projector can be expanded as</span></span> 

<span data-ttu-id="26d83-196">$ $ \ket{1 } } \ket{1 } } } } = \ket{10 \bra{10 + \ket{11 \bra{11 のようにして、$ $ = \ket{1 (\ket{0 } } ) = } } + } } します。</span><span class="sxs-lookup"><span data-stu-id="26d83-196">$$ \ket{1} \bra{1} \otimes \id = \ket{1}\bra{1} \otimes (\ket{0} \bra{0}+\ket{1} \bra{1})= \ket{10}\bra{10} + \ket{11}\bra{11}.</span></span>
$$

<span data-ttu-id="26d83-197">これは、列ベクトル表記を使用する multiqubit の likelihoods の測定値についての説明と一致していることがわかります。</span><span class="sxs-lookup"><span data-stu-id="26d83-197">We can then see that this is consistent with the discussion about measurement likelihoods for multiqubit states using column-vector notation:</span></span>

<span data-ttu-id="26d83-198">$ $ P (\ text1> 最初の qubit = 1 } ) = \ psi ^ \ ダガー (e e \_ {10} \_ {10 } ^ \ ダガー + e \_ {11} e \_ {11 } ^-ダガー)/psi = | e \_ {10 } ^ & ダガー-psi | ^ 2 + | e \_ {11 } ^ \ ダガー \ psi | ^ 2, $ $</span><span class="sxs-lookup"><span data-stu-id="26d83-198">$$ P(\text{first qubit = 1})= \psi^\dagger (e\_{10}e\_{10}^\dagger + e\_{11}e\_{11}^\dagger)\psi = |e\_{10}^\dagger \psi|^2 + |e\_{11}^\dagger \psi|^2, $$</span></span>

<span data-ttu-id="26d83-199">これは、multi-factor bit の測定に関する議論に一致します。</span><span class="sxs-lookup"><span data-stu-id="26d83-199">which matches the multi-qubit measurement discussion.</span></span>  <span data-ttu-id="26d83-200">ただし、この結果をマルチ qubit ケースに汎化することは、列ベクトル表記よりも Dirac 表記法を使用する方が少し単純で、前の処理とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="26d83-200">The generalization of this result to the multi-qubit case, however, is slightly more straightforward to express using Dirac notation than column-vector notation, and is entirely equivalent to the previous treatment.</span></span>

## <a name="density-operators"></a><span data-ttu-id="26d83-201">密度演算子</span><span class="sxs-lookup"><span data-stu-id="26d83-201">Density operators</span></span>

<span data-ttu-id="26d83-202">Dirac 表記を使用して表すもう1つの便利な演算子は、*密度演算子*です。これは、*状態演算子*とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="26d83-202">Another useful operator to express using Dirac notation is a *density operator*, sometimes also known as a *state operator*.</span></span>
<span data-ttu-id="26d83-203">クォンタム状態ベクトルの密度演算子は、$ \rho = \ket-psi \bra/psi $ という形式に { } { } なります。</span><span class="sxs-lookup"><span data-stu-id="26d83-203">A density operator for a quantum state vector takes the form $\rho = \ket{\psi} \bra{\psi}$.</span></span>
<span data-ttu-id="26d83-204">このように、ベクターではなく、マトリックスとして状態を表すこの概念は、確率の計算を表す便利な方法を提供し、同じ形式内のクォンタムの不確実性だけでなく統計の不確実性を示すこともできるため便利です。</span><span class="sxs-lookup"><span data-stu-id="26d83-204">This concept of representing the state as a matrix, rather than a vector, is often convenient because it gives a convenient way of representing probability calculations, and also allows one to describe both statistical uncertainty as well as quantum uncertainty within the same formalism.</span></span>
<span data-ttu-id="26d83-205">一般的なクォンタム状態の演算子は、ベクターではなく、クォンタムコンピューティングの一部の領域で広く使われていますが、フィールドの基本を理解する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="26d83-205">General quantum state operators, rather than vectors, are ubiquitous in some areas of quantum computing but are not necessary to understand the basics of the field.</span></span>
<span data-ttu-id="26d83-206">興味のある読者については、「」で提供されている参照資料のいずれ[かを参照](xref:microsoft.quantum.more-information)してください。</span><span class="sxs-lookup"><span data-stu-id="26d83-206">For the interested reader, we recommend reading one of the reference books provided in [For more information](xref:microsoft.quantum.more-information).</span></span>

## <a name="q-gate-sequences-equivalent-to-quantum-states"></a><span data-ttu-id="26d83-207">"クォンタム" 状態に相当する Q # ゲートシーケンス</span><span class="sxs-lookup"><span data-stu-id="26d83-207">Q# gate sequences equivalent to quantum states</span></span>
<span data-ttu-id="26d83-208">クォンタム表記と Q # プログラミング言語については、最後に説明します。このドキュメントでは、クォンタムの状態がクォンタムコンピューティングにおける情報の基本的なオブジェクトであることを説明しました。</span><span class="sxs-lookup"><span data-stu-id="26d83-208">A final point worth raising about quantum notation and the Q# programming language: at the onset of this document we mentioned that the quantum state is the fundamental object of information in quantum computing.</span></span>  <span data-ttu-id="26d83-209">その後、Q # では、クォンタム状態の概念がないことが不思議になるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="26d83-209">It may then come as a surprise that in Q# there is no notion of a quantum state.</span></span>  <span data-ttu-id="26d83-210">すべての状態は、その準備に使用された操作によってのみ記述されます。</span><span class="sxs-lookup"><span data-stu-id="26d83-210">Instead, all states are described only by the operations used to prepare them.</span></span>  <span data-ttu-id="26d83-211">前の例は、このことを示す優れた図解です。</span><span class="sxs-lookup"><span data-stu-id="26d83-211">The previous example is an excellent illustration of this.</span></span>  <span data-ttu-id="26d83-212">レジスタ内のすべてのクォンタムビット文字列に対して uniform 法則を表現するのではなく、結果を ^ {/otimes n \ket{0 $ の $H として表すことができ } } ます。</span><span class="sxs-lookup"><span data-stu-id="26d83-212">Rather than expressing a uniform superposition over every quantum bit string in a register, we can represent the result as $H^{\otimes n} \ket{0}$.</span></span>  <span data-ttu-id="26d83-213">これは、その理由をクラシックデプロイことができるという利点だけでなく、アルゴリズムを実装するためにソフトウェアスタックを通じて伝達される必要がある操作を簡潔に定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="26d83-213">This exponentially shorter description of the state not only has the advantage that we can classically reason about it, but it also concisely defines the operations needed to be propagated through the software stack to implement the algorithm.</span></span>  <span data-ttu-id="26d83-214">このため、Q # はクォンタムの状態ではなくゲートシーケンスを生成するように設計されています。ただし、理論的なレベルでは、2つのパースペクティブは同等です。</span><span class="sxs-lookup"><span data-stu-id="26d83-214">For this reason, Q# is designed to emit gate sequences rather than quantum states; however, at a theoretical level the two perspectives are equivalent.</span></span>
