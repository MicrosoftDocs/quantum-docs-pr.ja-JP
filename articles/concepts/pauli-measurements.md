---
title: P# li 測定
description: 単一および複数のメジャーの測定操作を使用する方法について説明します。
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
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
ms.openlocfilehash: 115c1703e433f24930e4be61b545048c95da28d1
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630296"
---
# <a name="pauli-measurements"></a><span data-ttu-id="78e5d-103">P# li 測定</span><span class="sxs-lookup"><span data-stu-id="78e5d-103">Pauli Measurements</span></span>

<span data-ttu-id="78e5d-104">前のディスカッションでは、計算ベースの測定に重点を置いてきました。</span><span class="sxs-lookup"><span data-stu-id="78e5d-104">In the previous discussions, we have focused on computational basis measurements.</span></span>
<span data-ttu-id="78e5d-105">実際には、数値表記の観点からは、コンピューティングベースの測定を表すのに便利な、クォンタムコンピューティングで発生する一般的な測定値があります。</span><span class="sxs-lookup"><span data-stu-id="78e5d-105">In fact, there are other common measurements that occur in quantum computing that, from a notational perspective, are convenient to express in terms of computational basis measurements.</span></span>
<span data-ttu-id="78e5d-106">Q # を操作するときに実行する最も一般的な種類の測定は、通常、測定値として使用されます。この*測定*では、計算ベースの測定値を汎用化して、他のベースの測定値と異なる qubits 間のパリティを含めます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-106">As you work with Q#, the most common kind of measurements that you'll run into will likely be *Pauli measurements*, which generalize computational basis measurements to include measurements in other bases, and of parity between different qubits.</span></span>
<span data-ttu-id="78e5d-107">このような場合、一般的には、一般的には、$X、Y、Z $ または $Z \otimes z、x \otimes x、x Y などの演算子である、p# li 演算子の測定について説明し \otimes $ ます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-107">In such cases, it is common to discuss measuring a Pauli operator, in general an operator such as $X,Y,Z$ or $Z\otimes Z, X\otimes X, X\otimes Y$, and so forth.</span></span>

> [!TIP]
> <span data-ttu-id="78e5d-108">Q # では、通常、マルチ qubit の演算子は型の配列によって表され `Pauli[]` ます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-108">In Q#, multi-qubit Pauli operators are generally represented by arrays of type `Pauli[]`.</span></span>
> <span data-ttu-id="78e5d-109">たとえば、Z/otimes $X を表すには、配列を $ 使用し `[PauliX, PauliZ, PauliY]` ます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-109">For example, to represent $X \otimes Z \otimes Y$, you can use the array `[PauliX, PauliZ, PauliY]`.</span></span>

<span data-ttu-id="78e5d-110">P# li 演算子の観点から、メジャーについて説明することは、クォンタムエラー修正のサブフィールドで特に一般的です。</span><span class="sxs-lookup"><span data-stu-id="78e5d-110">Discussing measurement in terms of Pauli operators is especially common in the subfield of quantum error correction.</span></span>
<span data-ttu-id="78e5d-111">Q # では、同様の規則に従います。ここでは、この測定の別のビューについて説明します。</span><span class="sxs-lookup"><span data-stu-id="78e5d-111">In Q#, we follow a similar convention; we now explain this alternative view of measurements.</span></span>

<span data-ttu-id="78e5d-112">P# li 測定を考える方法の詳細について検討する前に、クォンタムコンピューター内の1つの qubit がクォンタムの状態にどのように測定されるかについて考えることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="78e5d-112">Before delving into the details of how to think of a Pauli measurement, it is useful to think about what measuring a single qubit inside a quantum computer does to the quantum state.</span></span>
<span data-ttu-id="78e5d-113">$N $ -qubit クォンタム状態になっているとします。その後、1つの qubit をすぐに測定し $ ます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-113">Imagine that we have an $n$-qubit quantum state; then measuring one qubit immediately rules out half of the $2^n$ possibilities that state could be in.</span></span>
<span data-ttu-id="78e5d-114">つまり、測定値は、2つの半分の空白のいずれかにクォンタムの状態を投影します。</span><span class="sxs-lookup"><span data-stu-id="78e5d-114">In other words, the measurement projects the quantum state onto one of two half-spaces.</span></span>
<span data-ttu-id="78e5d-115">この直感を反映するために、測定について考える方法を一般化できます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-115">We can generalize the way we think about measurement to reflect this intuition.</span></span>

<span data-ttu-id="78e5d-116">これらのサブスペースを簡潔に識別するためには、それらを説明するための言語が必要です。</span><span class="sxs-lookup"><span data-stu-id="78e5d-116">In order to concisely identify these subspaces, we need a language for describing them.</span></span>
<span data-ttu-id="78e5d-117">2つのサブスペースを記述する方法の1つとして、2つの一意の値を持つマトリックスでそれらを指定する方法があります。これは、規約によって $ pm 1 として取得され $ ます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-117">One way to describe the two subspaces is by specifying them through a matrix that just has two unique eigenvalues, taken by convention to be $\pm 1$.</span></span>
<span data-ttu-id="78e5d-118">この方法でサブスペースを記述する簡単な例については、$Z を検討してください $ 。</span><span class="sxs-lookup"><span data-stu-id="78e5d-118">For a simple example of describing subspaces in this way, consider $Z$:</span></span>

<span data-ttu-id="78e5d-119">$ $ & begin{align}</span><span class="sxs-lookup"><span data-stu-id="78e5d-119">$$ \begin{align}</span></span>
  <span data-ttu-id="78e5d-120">Z & = \ begin{ bmatrix } 1 & 0 \\ \\ 0 &-1 \ end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="78e5d-120">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="78e5d-121">& end{align}</span><span class="sxs-lookup"><span data-stu-id="78e5d-121">\end{align}</span></span>
$$

<span data-ttu-id="78e5d-122">$Z 行列の対角線要素を読み取ると $ 、$Z に $ $ \ket{0 $ と $ \ket{1 $ という2つの固有ベクトルがあり、 } 対応する } 固有値 $ \ pm 1 があることがわかります $ 。</span><span class="sxs-lookup"><span data-stu-id="78e5d-122">By reading the diagonal elements of the Pauli-$Z$ matrix, we can see that $Z$ has two eigenvectors, $\ket{0}$ and $\ket{1}$, with corresponding eigenvalues $\pm 1$.</span></span>
<span data-ttu-id="78e5d-123">したがって、qubit を測定し、 `Zero` (状態 $ \ket{0 $ に対応する) を取得すると、 } qubit の状態が $Z 演算子の $ + 1 $ eigenstate であることがわかり $ ます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-123">Thus, if we measure the qubit and obtain `Zero` (corresponding to the state $\ket{0}$), we know that the state of our qubit is a $+1$ eigenstate of the $Z$ operator.</span></span>
<span data-ttu-id="78e5d-124">同様に、を取得した場合は、 `One` qubit の状態が $Z の $-1 の状態であることがわかり $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-124">Similarly, if we obtain `One`, we know that the state of our qubit is a $-1$ eigenstate of $Z$.</span></span>
<span data-ttu-id="78e5d-125">このプロセスは、「P# li $Z の測定」として、P# li 測定の言語で参照され $ ます。これは、計算ベースの測定を実行することとまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="78e5d-125">This process is referred to in the language of Pauli measurements as "measuring Pauli $Z$," and is entirely equivalent to performing a computational basis measurement.</span></span>

<span data-ttu-id="78e5d-126">\times $ $Z のの、すべての $2 2 マトリックスで、 $ この条件を満たすこともできます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-126">Any $2\times 2$ matrix that is a unitary transformation of $Z$ also satisfies this criteria.</span></span>
<span data-ttu-id="78e5d-127">つまり、マトリックス $A = U ^-ダガー Z U を使用することもできます $ 。ここで、$U $ は他の任意の長さ行列で、$ pm 1 固有ベクトルの測定の2つの結果を定義するマトリックスを提供し $ ます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-127">That is, we could also use a matrix $A=U^\dagger Z U$, where $U$ is any other unitary matrix, to give a matrix that defines the two outcomes of a measurement in its $\pm 1$ eigenvectors.</span></span>
<span data-ttu-id="78e5d-128">Preferences Li 測定の表記は、$X、Y、Z の $ 測定値を等価の測定値として識別することによって、このような値を参照します。</span><span class="sxs-lookup"><span data-stu-id="78e5d-128">The notation of Pauli measurements references this unitary equivalence by identifying $X,Y,Z$ measurements as equivalent measurements that one could do to gain information from a qubit.</span></span>
<span data-ttu-id="78e5d-129">これらの測定値は、便宜上、次のように提供されます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-129">These measurements are given below for convenience.</span></span>


|<span data-ttu-id="78e5d-130">P# li 測定</span><span class="sxs-lookup"><span data-stu-id="78e5d-130">Pauli Measurement</span></span>  |<span data-ttu-id="78e5d-131">ユニタリ変換</span><span class="sxs-lookup"><span data-stu-id="78e5d-131">Unitary transformation</span></span>  |
|-------------------|------------------------|
| <span data-ttu-id="78e5d-132">$Z$</span><span class="sxs-lookup"><span data-stu-id="78e5d-132">$Z$</span></span>               | <span data-ttu-id="78e5d-133">$ \ bold$</span><span class="sxs-lookup"><span data-stu-id="78e5d-133">$\boldone$</span></span>             |
| <span data-ttu-id="78e5d-134">$X$</span><span class="sxs-lookup"><span data-stu-id="78e5d-134">$X$</span></span>               | <span data-ttu-id="78e5d-135">$H$</span><span class="sxs-lookup"><span data-stu-id="78e5d-135">$H$</span></span>                    |
| <span data-ttu-id="78e5d-136">$Y$</span><span class="sxs-lookup"><span data-stu-id="78e5d-136">$Y$</span></span>               | <span data-ttu-id="78e5d-137">$HS ^ {\ ダガー}$</span><span class="sxs-lookup"><span data-stu-id="78e5d-137">$HS^{\dagger}$</span></span>         |

<span data-ttu-id="78e5d-138">つまり、この言語を使用すると、"measure $Y $ " は $HS ^/ダガーを適用し、計算の単位で測定することと同じです。 $ ここで、は "フェーズゲート" と呼ばれる組み込みのクォンタム操作であり、これは、長さの [`S`](xref:microsoft.quantum.intrinsic.s) 行列でシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-138">That is, using this language, "measure $Y$" is equivalent to applying $HS^\dagger$ and then measuring in the computational basis, where [`S`](xref:microsoft.quantum.intrinsic.s) is an intrinsic quantum operation sometimes called the "phase gate," and can be simulated by the unitary matrix</span></span>

<span data-ttu-id="78e5d-139">$ $ & begin{align}</span><span class="sxs-lookup"><span data-stu-id="78e5d-139">$$ \begin{align}</span></span>
    <span data-ttu-id="78e5d-140">S = \ begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="78e5d-140">S = \begin{bmatrix}</span></span>
        <span data-ttu-id="78e5d-141">1 & 0 \\ \\ 0 & i \ end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="78e5d-141">1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="78e5d-142">& end{align}</span><span class="sxs-lookup"><span data-stu-id="78e5d-142">\end{align}</span></span>
$$

<span data-ttu-id="78e5d-143">また、 $ クォンタム状態ベクターに $HS ^ を適用し、 $ 次の演算がと等価になるように $Z を測定することと同じです `Measure([PauliY], [q])` 。</span><span class="sxs-lookup"><span data-stu-id="78e5d-143">It is also equivalent to applying $HS^\dagger$ to the quantum state vector and then measuring $Z$, such that the following operation is equivalent to `Measure([PauliY], [q])`:</span></span>

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

<span data-ttu-id="78e5d-144">次に、適切な状態が検出されます。これは、クォンタム状態ベクターに $SH を適用するために、計算ベースに変換されます $ 。上記のスニペットでは、計算に戻る変換は、ブロックを使用することによって自動的に処理され `within … apply` ます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-144">The correct state would then be found by transforming back to the computational basis, which amounts to applying $SH$ to the quantum state vector; in the above snippet, the transformation back to the computational basis is handled automatically by the use of the `within … apply` block.</span></span>

<span data-ttu-id="78e5d-145">Q # では、結果と---して、州---との対話から抽出された古典的な情報が `Result` {\texttt{Zero, \texttt{One} $ の $j 値によって与えられます。これは、 \\ } } \\ その結果が、測定された $ (-1) ^ j eigenspace に含まれるかどうかを示し $ ます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-145">In Q#, we say the outcome---that is, the classical information extracted from interacting with the state---is given by a `Result` value $j \in \\{\texttt{Zero}, \texttt{One}\\}$ indicating if the result is in the $(-1)^j$ eigenspace of the Pauli operator measured.</span></span>


## <a name="multiple-qubit-measurements"></a><span data-ttu-id="78e5d-146">複数の qubit 測定値</span><span class="sxs-lookup"><span data-stu-id="78e5d-146">Multiple-qubit measurements</span></span>

<span data-ttu-id="78e5d-147">次に示すように、マルチ qubit の演算子の測定値は同様に定義されています。</span><span class="sxs-lookup"><span data-stu-id="78e5d-147">Measurements of multi-qubit Pauli operators are defined similarly, as seen from:</span></span>

<span data-ttu-id="78e5d-148">$ $ Z \otimes z = \ begin{ bmatrix } 1 &0 &0&0 \\\\ 0 & -1&0&0 0 \\\\&0 & -1&0 \\\\ 0&0&0&1 \end { bmatrix } 。</span><span class="sxs-lookup"><span data-stu-id="78e5d-148">$$ Z\otimes Z = \begin{bmatrix}1 &0 &0&0\\\\  0&-1&0&0\\\\ 0&0&-1&0\\\\ 0&0&0&1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="78e5d-149">したがって、2つの $Z 演算子のアーカイブ後の製品は、 $ $ + 1 $ と $-1 eigenvalues で構成される2つのスペースで構成されるマトリックスを形成し $ ます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-149">Thus the tensor products of two Pauli-$Z$ operators forms a matrix composed of two spaces consisting of $+1$ and $-1$ eigenvalues.</span></span>
<span data-ttu-id="78e5d-150">シングル qubit の場合と同様に、両方とも、アクセス可能なベクター空間の半分が $ + 1 の e 空間に所属 $ し、残りの半分が $-1 の e 空間に属していることを意味し $ ます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-150">As with the single-qubit case, both constitute a half-space meaning that half of the accessible vector space belongs to the $+1$ eigenspace and the remaining half to the $-1$ eigenspace.</span></span>
<span data-ttu-id="78e5d-151">一般に、その製品の定義から簡単に確認できます。これは、P$Z のオペレーターと id のすべての製品についても同様です $ 。</span><span class="sxs-lookup"><span data-stu-id="78e5d-151">In general, it is easy to see from the definition of the tensor product that any tensor product of Pauli-$Z$ operators and the identity also obeys this.</span></span>
<span data-ttu-id="78e5d-152">たとえば、</span><span class="sxs-lookup"><span data-stu-id="78e5d-152">For example,</span></span>

<span data-ttu-id="78e5d-153">$ $ & begin{align}</span><span class="sxs-lookup"><span data-stu-id="78e5d-153">$$ \begin{align}</span></span>
    <span data-ttu-id="78e5d-154">Z/otimes/bold 完了 = \ begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="78e5d-154">Z \otimes \boldone = \begin{bmatrix}</span></span>
        <span data-ttu-id="78e5d-155">1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 &-1 & 0 \\ \\ 0 & 0 & 0 &-1 \ end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="78e5d-155">1 &  0 &  0 &  0 \\\\ 0 &  1 &  0 &  0 \\\\ 0 &  0 & -1 &  0 \\\\ 0 &  0 &  0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="78e5d-156">& end{align}</span><span class="sxs-lookup"><span data-stu-id="78e5d-156">\end{align}</span></span>
$$

<span data-ttu-id="78e5d-157">前と同様に、このようなマトリックスのすべてのユニタリ変換では、$-pm 1 eigenvalues でラベル付けされた2つの半分の空白も記述し $ ます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-157">As before, any unitary transformation of such matrices also describes two half-spaces labeled by $\pm 1$ eigenvalues.</span></span>
<span data-ttu-id="78e5d-158">たとえば、 \otimes id から X = h \otimes h (z \otimes z) h h を $X し、 \otimes $ $Z = hxh に $ します。</span><span class="sxs-lookup"><span data-stu-id="78e5d-158">For example, $X\otimes X = H\otimes H(Z\otimes Z)H\otimes H$  from the identity that $Z=HXH$.</span></span>
<span data-ttu-id="78e5d-159">1 qubit の場合と同様に、2つの2つのビットを持つすべての値は、 \otimes $ $4 4 つの $U のユニタリ行列に対して $U ^/ダガー (Z/Id) U として書き込むことができ \times $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-159">Similar to the one-qubit case, all two-qubit Pauli-measurements can be written as $U^\dagger (Z\otimes \id) U$ for $4\times 4$ unitary matrices $U$.</span></span> <span data-ttu-id="78e5d-160">次の表に示す変換を列挙します。</span><span class="sxs-lookup"><span data-stu-id="78e5d-160">We enumerate the transformations in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="78e5d-161">次の表では、$ & を使用して、 } マトリックス $ $ を示します。}</span><span class="sxs-lookup"><span data-stu-id="78e5d-161">In the table below, we use $\operatorname{SWAP}$ to indicate the matrix $$ \begin{align}</span></span>
>     <span data-ttu-id="78e5d-162">& } & = \ left (\ begin{matrix)}</span><span class="sxs-lookup"><span data-stu-id="78e5d-162">\operatorname{SWAP} & = \left(\begin{matrix}</span></span>
>         <span data-ttu-id="78e5d-163">1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 0 \\ \\ & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1/end{マトリックス } 右)}</span><span class="sxs-lookup"><span data-stu-id="78e5d-163">1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{matrix}\right) \end{align}</span></span>
> <span data-ttu-id="78e5d-164">組み込み操作をシミュレートするために使用される $ $ [`SWAP`](xref:microsoft.quantum.intrinsic) 。</span><span class="sxs-lookup"><span data-stu-id="78e5d-164">$$ used to simulate the intrinsic operation [`SWAP`](xref:microsoft.quantum.intrinsic).</span></span>

|<span data-ttu-id="78e5d-165">P# li 測定</span><span class="sxs-lookup"><span data-stu-id="78e5d-165">Pauli Measurement</span></span>     |<span data-ttu-id="78e5d-166">ユニタリ変換</span><span class="sxs-lookup"><span data-stu-id="78e5d-166">Unitary transformation</span></span>  |
|----------------------|------------------------|
| <span data-ttu-id="78e5d-167">$Z の実行 (& o)$</span><span class="sxs-lookup"><span data-stu-id="78e5d-167">$Z \otimes \boldone$</span></span> | <span data-ttu-id="78e5d-168">{times > その他の作業の完了 (& o)$</span><span class="sxs-lookup"><span data-stu-id="78e5d-168">$\boldone \otimes \boldone$</span></span> |
| <span data-ttu-id="78e5d-169">$Z \otimes$</span><span class="sxs-lookup"><span data-stu-id="78e5d-169">$Z\otimes \boldone$</span></span> | <span data-ttu-id="78e5d-170">$/ \otimes bold 完了$</span><span class="sxs-lookup"><span data-stu-id="78e5d-170">$\boldone\otimes \boldone$</span></span> |
| <span data-ttu-id="78e5d-171">$X \otimes$</span><span class="sxs-lookup"><span data-stu-id="78e5d-171">$X\otimes \boldone$</span></span> | <span data-ttu-id="78e5d-172">$H \otimes$</span><span class="sxs-lookup"><span data-stu-id="78e5d-172">$H\otimes \boldone$</span></span> |
| <span data-ttu-id="78e5d-173">$Y \otimes$</span><span class="sxs-lookup"><span data-stu-id="78e5d-173">$Y\otimes \boldone$</span></span> | <span data-ttu-id="78e5d-174">$HS ^ & b) \otimes$</span><span class="sxs-lookup"><span data-stu-id="78e5d-174">$HS^\dagger\otimes \boldone$</span></span> |
| <span data-ttu-id="78e5d-175">$/bold (Z)$</span><span class="sxs-lookup"><span data-stu-id="78e5d-175">$\boldone \otimes Z$</span></span> | <span data-ttu-id="78e5d-176">$ \ 演算子の入れ替え}$</span><span class="sxs-lookup"><span data-stu-id="78e5d-176">$\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="78e5d-177">$ > その他の操作 (X)$</span><span class="sxs-lookup"><span data-stu-id="78e5d-177">$\boldone \otimes X$</span></span> | <span data-ttu-id="78e5d-178">$ (& H) & # 0/記号の \otimes 入れ替え}$</span><span class="sxs-lookup"><span data-stu-id="78e5d-178">$(H\otimes \boldone)\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="78e5d-179">$/その他の操作 (Y)$</span><span class="sxs-lookup"><span data-stu-id="78e5d-179">$\boldone \otimes Y$</span></span> | <span data-ttu-id="78e5d-180">$ (HS ^ \ ダガー > その他の操作 \otimes ) \ の演算子}$</span><span class="sxs-lookup"><span data-stu-id="78e5d-180">$(HS^\dagger\otimes \boldone)\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="78e5d-181">$Z \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="78e5d-181">$Z\otimes Z$</span></span> | <span data-ttu-id="78e5d-182">$ \ 演算子名 } \_ {10}$</span><span class="sxs-lookup"><span data-stu-id="78e5d-182">$\operatorname{CNOT}\_{10}$</span></span> |
| <span data-ttu-id="78e5d-183">$X \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="78e5d-183">$X\otimes Z$</span></span> | <span data-ttu-id="78e5d-184">$ \ 演算子名 } \_ {10 (& a } ) {10 (& t \otimes ) $</span><span class="sxs-lookup"><span data-stu-id="78e5d-184">$\operatorname{CNOT}\_{10}(H\otimes \boldone)$</span></span> |
| <span data-ttu-id="78e5d-185">$Y \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="78e5d-185">$Y\otimes Z$</span></span> | <span data-ttu-id="78e5d-186">$ \ オペレーター名 } \_ {10 } (HS ^ \ ダガー > \otimes 完了) $</span><span class="sxs-lookup"><span data-stu-id="78e5d-186">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes \boldone)$</span></span> |
| <span data-ttu-id="78e5d-187">$Z \otimes X$</span><span class="sxs-lookup"><span data-stu-id="78e5d-187">$Z\otimes X$</span></span> | <span data-ttu-id="78e5d-188">$ \ 演算子名 } \_ {10 } (\ bold 完了 \otimes H) $</span><span class="sxs-lookup"><span data-stu-id="78e5d-188">$\operatorname{CNOT}\_{10}(\boldone\otimes H)$</span></span> |
| <span data-ttu-id="78e5d-189">$X \otimes X$</span><span class="sxs-lookup"><span data-stu-id="78e5d-189">$X\otimes X$</span></span> | <span data-ttu-id="78e5d-190">$ \ 演算子名 } \_ {10 } (h \otimes h) $</span><span class="sxs-lookup"><span data-stu-id="78e5d-190">$\operatorname{CNOT}\_{10}(H\otimes H)$</span></span> |
| <span data-ttu-id="78e5d-191">$Y \otimes X$</span><span class="sxs-lookup"><span data-stu-id="78e5d-191">$Y\otimes X$</span></span> | <span data-ttu-id="78e5d-192">$ \ オペレーター名 } \_ {10 } (HS ^ \ ダガー \otimes H) $</span><span class="sxs-lookup"><span data-stu-id="78e5d-192">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes H)$</span></span> |
| <span data-ttu-id="78e5d-193">$Z \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="78e5d-193">$Z\otimes Y$</span></span> | <span data-ttu-id="78e5d-194">$ \ オペレーター名 } \_ {10 (& a) {10 (& a) {10 } (& c</span><span class="sxs-lookup"><span data-stu-id="78e5d-194">$\operatorname{CNOT}\_{10}(\boldone \otimes HS^\dagger)$</span></span> |
| <span data-ttu-id="78e5d-195">$X \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="78e5d-195">$X\otimes Y$</span></span> | <span data-ttu-id="78e5d-196">$ \ オペレーター名 } \_ {10 } (H \otimes HS ^ \ ダガー) $</span><span class="sxs-lookup"><span data-stu-id="78e5d-196">$\operatorname{CNOT}\_{10}(H\otimes HS^\dagger)$</span></span> |
| <span data-ttu-id="78e5d-197">$Y \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="78e5d-197">$Y\otimes Y$</span></span> | <span data-ttu-id="78e5d-198">$ \ オペレーター名 } \_ {10 } (hs ^ \ ダガー \otimes hs ^ \ ダガー) $</span><span class="sxs-lookup"><span data-stu-id="78e5d-198">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes HS^\dagger)$</span></span> |

<span data-ttu-id="78e5d-199">ここでは、 [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) 次の理由で操作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-199">Here, the [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operation appears for the following reason.</span></span>
<span data-ttu-id="78e5d-200">$/Bold done マトリックスを含まない各 P# li の測定値 $ は、前述の理由により、$Z Z までの長さに相当 \otimes $ します。</span><span class="sxs-lookup"><span data-stu-id="78e5d-200">Each Pauli measurement that does not include the $\boldone$ matrix is equivalent up to a unitary to $Z\otimes Z$ by the above reasoning.</span></span>
<span data-ttu-id="78e5d-201">$Z Z の固有値は、 \otimes $ 各計算ベースのベクトルを構成する qubits のパリティに依存します。また、制御されていない操作は、このパリティを計算して最初のビットに格納するために機能します。</span><span class="sxs-lookup"><span data-stu-id="78e5d-201">The eigenvalues of $Z\otimes Z$ only depend on the parity of the qubits that comprise each computational basis vector, and the controlled-not operations serve to compute this parity and store it in the first bit.</span></span>
<span data-ttu-id="78e5d-202">次に、最初のビットを測定した後、結果として得られる半分の領域の id を回復できます。これは、P# li 演算子の測定に相当します。</span><span class="sxs-lookup"><span data-stu-id="78e5d-202">Then once the first bit is measured, we can recover the identity of the resultant half-space, which is equivalent to measuring the Pauli operator.</span></span>

<span data-ttu-id="78e5d-203">注意点として、$Z Z の測定 \otimes $ が $Z \mathbb{1 $ を順番に測定して \otimes から $ \mathbb{1/otimes z を測定するのと同じであると想定することもあります } } $ 。この想定は false です。</span><span class="sxs-lookup"><span data-stu-id="78e5d-203">One additional note: while it may be tempting to assume that measuring $Z\otimes Z$ is the same as sequentially measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$, this assumption would be false.</span></span>
<span data-ttu-id="78e5d-204">その理由は、$Z Z を測定すると、 \otimes $ $ これらの演算子の $ + 1 または $-1 eigenstate にクォンタムの状態が投影されるためです $ 。</span><span class="sxs-lookup"><span data-stu-id="78e5d-204">The reason is that measuring $Z\otimes Z$ projects the quantum state into either the $+1$ or $-1$ eigenstate of these operators.</span></span>
<span data-ttu-id="78e5d-205">$Z \otimes \mathbb{1 } $ を測定してから $ \mathbb{1/Otimes z を測定すると } $ 、最初にクォンタムの状態ベクターが $Z \mathbb{1 $ の半分の領域に、 \otimes } 次に $ \mathbb{1/ } otimes z の半分 $ の領域に投影されます。計算ベースのベクトルが4つあるため、両方の測定を実行すると、状態が4分の1に減少し、1つの計算ベースのベクトルに縮小されます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-205">Measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$ projects the quantum state vector first onto a half space of $Z\otimes \mathbb{1}$ and then onto a half space of $\mathbb{1} \otimes Z$. As there are four computational basis vectors, performing both measurements reduces the state to a quarter-space and hence reduces it to a single computational basis vector.</span></span>

## <a name="correlations-between-qubits"></a><span data-ttu-id="78e5d-206">Qubits 間の相関関係</span><span class="sxs-lookup"><span data-stu-id="78e5d-206">Correlations between qubits</span></span>
<span data-ttu-id="78e5d-207">$X X や $Z Z などの P# li マトリックスの保存されていない製品を測定する別の方法として、 \otimes $ これらの \otimes $ 測定値を使用すると、2つの qubits 間の相関関係に格納されている情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-207">Another way of looking at measuring tensor products of Pauli matrices such as $X\otimes X$ or $Z\otimes Z$ is that these measurements let you look at information stored in the correlations between the two qubits.</span></span>
<span data-ttu-id="78e5d-208">$X \otimes \ id を測定 $ すると、最初の qubit にローカルに格納されている情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-208">Measuring $X\otimes \id$ lets you look at information that is locally stored in the first qubit.</span></span>
<span data-ttu-id="78e5d-209">クォンタムコンピューティングではどちらの種類の測定も同等の価値がありますが、前者はクォンタムコンピューティングの能力を測定します。</span><span class="sxs-lookup"><span data-stu-id="78e5d-209">While both types of measurements are equally valuable in quantum computing, the former illuminates the power of quantum computing.</span></span>
<span data-ttu-id="78e5d-210">クォンタムコンピューティングでは、学習する情報が1つの qubit に格納されておらず、すべての qubit にローカルに格納されていないことが明らかになっています。したがって、この情報は、結合測定 ($Z Z など) を使用して参照することによって、 \otimes $ マニフェストになります。</span><span class="sxs-lookup"><span data-stu-id="78e5d-210">It reveals that in quantum computing, often the information you wish to learn is not stored in any single qubit but rather stored non-locally in all the qubits at once, and therefore only by looking at it through a joint measurement (e.g. $Z\otimes Z$) does this information become manifest.</span></span>

<span data-ttu-id="78e5d-211">たとえば、エラー修正では、保護しようとしている状態について何も学習していないときに発生したエラーを確認したい場合がよくあります。</span><span class="sxs-lookup"><span data-stu-id="78e5d-211">For example, in error correction, we often wish to learn what error occurred while learning nothing about the state that we're trying to protect.</span></span>
<span data-ttu-id="78e5d-212">[ビットフリップコードサンプル](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code)では、$Z/otimes z/otimes $ /id と $/id/z/otimes z のような測定値を使用して、その方法の例を示して $ います。</span><span class="sxs-lookup"><span data-stu-id="78e5d-212">The [bit-flip code sample](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) shows an example of how you can do that using measurements like $Z \otimes Z \otimes \id$ and $\id \otimes Z \otimes Z$.</span></span>
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

<span data-ttu-id="78e5d-213">$X Y/otimes などの任意の Pforce 演算子 \otimes $ を測定することもできます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-213">Arbitrary Pauli operators such as $X\otimes Y \otimes Z \otimes \boldone$ can also be measured.</span></span>
<span data-ttu-id="78e5d-214">P# li 演算子のすべてのその他の製品には、2つの固有値 $ pm 1 しかあり $ ません。固有値はベクター空間全体の半分のスペースを構成します。</span><span class="sxs-lookup"><span data-stu-id="78e5d-214">All such tensor products of Pauli operators have only two eigenvalues $\pm 1$ and both eigenspaces constitute half-spaces of the entire vector space.</span></span>
<span data-ttu-id="78e5d-215">そのため、これらは上記の要件と一致します。</span><span class="sxs-lookup"><span data-stu-id="78e5d-215">Thus they coincide with the requirements stated above.</span></span>

<span data-ttu-id="78e5d-216">Q # では、このような測定値によって、 $ $ (-1) ^ j という符号の結果が生成されると $j が返さ $ れます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-216">In Q#, such measurements return $j$ if the measurement yields a result in the eigenspace of sign $(-1)^j$.</span></span>
<span data-ttu-id="78e5d-217">Q # の組み込み機能として Pdiagonalizing の測定値を持つことは便利です。このような演算子を測定するには、制御されていないゲート型のチェーンと基本変換の長いチェーンが必要であり、その $ 操作を $Z と $ id のすべての製品として表現するために必要な $U ゲートを記述し $ $ ます。これらの定義済みの測定値のいずれかを実行することを指定できるようにすることで、計算ベースの測定によって必要な情報が得られるように、基になる方法を気にする必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="78e5d-217">Having Pauli measurements as a built-in feature in Q# is helpful because measuring such operators requires long chains of controlled-NOT gates and basis transformations to describe the diagonalizing $U$ gate needed to express the operation as a tensor product of $Z$ and $\id$. By being able to specify that you wish to do one of these pre-defined measurements, you don't need to worry about how to transform your basis such that a computational basis measurement provides the necessary information.</span></span>
<span data-ttu-id="78e5d-218">Q # は、必要なすべての基準変換を自動的に処理します。</span><span class="sxs-lookup"><span data-stu-id="78e5d-218">Q# handles all the necessary basis transformations for you automatically.</span></span>
<span data-ttu-id="78e5d-219">詳細については、「」および「」操作を参照してください [`Measure`](xref:microsoft.quantum.intrinsic.measure) [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) 。</span><span class="sxs-lookup"><span data-stu-id="78e5d-219">For more information, see the [`Measure`](xref:microsoft.quantum.intrinsic.measure) and [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operations.</span></span>

## <a name="the-no-cloning-theorem"></a><span data-ttu-id="78e5d-220">複製なしの定理</span><span class="sxs-lookup"><span data-stu-id="78e5d-220">The No-Cloning Theorem</span></span>

<span data-ttu-id="78e5d-221">クォンタム情報は強力です。</span><span class="sxs-lookup"><span data-stu-id="78e5d-221">Quantum information is powerful.</span></span>
<span data-ttu-id="78e5d-222">これにより、最もよく知られている古典アルゴリズムよりも指数関数的に数値を指数関数的に処理できるようにすることが可能になります。また、正確にシミュレートするためにクラシックデプロイに必要な、関連する電子システムを効率的にシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-222">It enables us to do amazing things such as factor numbers exponentially faster than the best known classical algorithms, or efficiently simulate correlated electron systems that classically require exponential cost to simulate accurately.</span></span>
<span data-ttu-id="78e5d-223">ただし、クォンタムコンピューティングの能力には制限があります。</span><span class="sxs-lookup"><span data-stu-id="78e5d-223">However, there are limitations to the power of quantum computing.</span></span>
<span data-ttu-id="78e5d-224">このような制限は、*複製なしの定理*によって与えられます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-224">One such limitation is given by the *No-Cloning Theorem*.</span></span>

<span data-ttu-id="78e5d-225">No 複製定理は、このという名前です。</span><span class="sxs-lookup"><span data-stu-id="78e5d-225">The No-Cloning Theorem is aptly named.</span></span>
<span data-ttu-id="78e5d-226">クォンタムコンピューターによる汎用クォンタム状態の複製は禁止されています。</span><span class="sxs-lookup"><span data-stu-id="78e5d-226">It disallows cloning of generic quantum states by a quantum computer.</span></span>
<span data-ttu-id="78e5d-227">定理の証明は、非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="78e5d-227">The proof of the theorem is remarkably straightforward.</span></span>
<span data-ttu-id="78e5d-228">ここでは、複製なしの定理の完全な証明は少し技術的なものではありませんが、追加の補助 qubits がこのスコープ内に存在しない場合は、(計算中にスクラッチ領域に使用される補助 qubits は qubits であり、Q # で簡単に使用および管理されます)[を参照し](xref:microsoft.quantum.guide.qubits#borrowed-qubits)てください。</span><span class="sxs-lookup"><span data-stu-id="78e5d-228">While a full proof of the no-cloning theorem is a little too technical for our discussion here, the proof in the case of no additional auxiliary qubits is within our scope (auxiliary qubits are qubits used for scratch space during a computation and are easily used and managed in Q#, see [borrowed qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span></span>

<span data-ttu-id="78e5d-229">このようなクォンタムコンピューターでは、複製操作は、1つのユニタリ行列によって記述される必要があります。</span><span class="sxs-lookup"><span data-stu-id="78e5d-229">For such a quantum computer, the cloning operation must be described by a unitary matrix.</span></span>
<span data-ttu-id="78e5d-230">複製しようとしているクォンタムの状態が破損する可能性があるため、測定は禁止されています。</span><span class="sxs-lookup"><span data-stu-id="78e5d-230">We disallow measurement, since it would corrupt the quantum state we are trying to clone.</span></span>
<span data-ttu-id="78e5d-231">複製操作をシミュレートするには、' $ $ U \ket { \ psi } \ket{0 } = \ket/ { psi } \ket/ { psi というプロパティを持つために使用される、ユニタリ行列が必要です。}</span><span class="sxs-lookup"><span data-stu-id="78e5d-231">To simulate the cloning operation, we want the unitary matrix used to have the property that $$ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}</span></span>
<span data-ttu-id="78e5d-232">任意の状態の $ \ket { \ psi } $。</span><span class="sxs-lookup"><span data-stu-id="78e5d-232">$$ for any state $\ket{\psi}$.</span></span>
<span data-ttu-id="78e5d-233">マトリックス乗算の直線性プロパティは、2つ目のクォンタム状態 $ \ket { $ であることを意味します。 }</span><span class="sxs-lookup"><span data-stu-id="78e5d-233">The linearity property of matrix multiplication then implies that for any second quantum state $\ket{\phi}$,</span></span>

<span data-ttu-id="78e5d-234">$ $ & begin{align}</span><span class="sxs-lookup"><span data-stu-id="78e5d-234">$$ \begin{align}</span></span>
    <span data-ttu-id="78e5d-235">U-left [\frac{1 } {\ sqrt{2 } } \ left (\ket/ { phi + \ket \-right } { } ) \ket{0}</span><span class="sxs-lookup"><span data-stu-id="78e5d-235">U \left[ \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right] \ket{0}</span></span>
    <span data-ttu-id="78e5d-236">& = \frac{1 } {\ sqrt{2 } } U \ket { \ phi } \ket{0}</span><span class="sxs-lookup"><span data-stu-id="78e5d-236">& = \frac{1}{\sqrt{2}} U\ket{\phi}\ket{0}</span></span>
      <span data-ttu-id="78e5d-237">+ \frac{1 } {\ sqrt{2 } } U \ket { \ psi } \ket{0 } \\ \\ & = \frac{1 } {\ sqrt{2 } } \ left (\ket/ { phi } \ket/ { phi } + \ket/ { psi } \ket { \ psi}</span><span class="sxs-lookup"><span data-stu-id="78e5d-237">+ \frac{1}{\sqrt{2}} U\ket{\psi}\ket{0} \\\\ & = \frac{1}{\sqrt{2}} \left( \ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi}</span></span>
        <span data-ttu-id="78e5d-238">\ right) \\ \\ & \n 左 (\frac{1 } {\ sqrt{2 } } \ left (\ket/ { phi } + \ket/psi \ right) \) \ { } otimes \ left (\frac{1 } {\ sqrt{2 } }/left (\ket/ { phi } + \ket \-right { } ) \ right)</span><span class="sxs-lookup"><span data-stu-id="78e5d-238">\right) \\\\ & \ne \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right) \otimes \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right).</span></span>
<span data-ttu-id="78e5d-239">& end{align}</span><span class="sxs-lookup"><span data-stu-id="78e5d-239">\end{align}</span></span>
$$

<span data-ttu-id="78e5d-240">これにより、複製されていない定理の背後で基本的な直感が得られます。不明なクォンタム状態をコピーするデバイスは、少なくともそのコピーされた状態の中でエラーを誘発する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78e5d-240">This provides the fundamental intuition behind the No-Cloning Theorem: any device that copies an unknown quantum state must induce errors on at least some of the states it copies.</span></span>
<span data-ttu-id="78e5d-241">Cloner が入力状態で直線的に動作することを前提として、補助 qubits の追加や測定によって違反が発生する可能性がありますが、このような対話によって、測定統計を通じてシステムに関する情報が漏洩し、そのような場合には正確な複製を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-241">While the key assumption that the cloner acts linearly on the input state can be violated through the addition and measurement of auxiliary qubits, such interactions also leak information about the system through the measurement statistics and prevent exact cloning in such cases as well.</span></span>
<span data-ttu-id="78e5d-242">複製なしの定理の詳細については、「」[を](xref:microsoft.quantum.more-information)参照してください。</span><span class="sxs-lookup"><span data-stu-id="78e5d-242">For a more complete proof of the No-Cloning Theorem see [For more information](xref:microsoft.quantum.more-information).</span></span>

<span data-ttu-id="78e5d-243">クォンタムの状態を複製できる場合は、クォンタムの状態についての理解を深めることができるので、定理の複製は、クォンタムの計算にとって重要です。</span><span class="sxs-lookup"><span data-stu-id="78e5d-243">The No-Cloning Theorem is important for qualitative understanding of quantum computing because if you could clone quantum states inexpensively then you would be granted a near-magical ability to learn from quantum states.</span></span>
<span data-ttu-id="78e5d-244">実際には、ハイゼンベルグの vaunted の不確定性の原則に違反する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="78e5d-244">Indeed, you could violate Heisenberg's vaunted uncertainty principle.</span></span>
<span data-ttu-id="78e5d-245">または、最適な cloner を使用して、複雑なクォンタム分布から1つのサンプルを取得し、1つのサンプルだけからその分布について学習できる可能性のあるすべてのことを学ぶこともできます。</span><span class="sxs-lookup"><span data-stu-id="78e5d-245">Alternatively, you could use an optimal cloner to take a single sample from a complex quantum distribution and learn everything you could possibly learn about that distribution from just one sample.</span></span>
<span data-ttu-id="78e5d-246">これは、コインと観察ヘッドを反転し、その結果について友人に伝えたときに、そのコインの分布が $p = 0.512643 を使用してベルヌーイでなければならないということです $ 。</span><span class="sxs-lookup"><span data-stu-id="78e5d-246">This would be like you flipping a coin and observing heads and then upon telling a friend about the result having them respond "Ah the distribution of that coin must be Bernoulli with $p=0.512643\ldots$!"</span></span>  <span data-ttu-id="78e5d-247">このようなステートメントは非 sensical になります。これは、1つの情報 (ヘッドの結果) は、十分な前の情報を使用せずに、分布をエンコードするために必要な多くの情報を提供できないためです。</span><span class="sxs-lookup"><span data-stu-id="78e5d-247">Such a statement would be non-sensical because one bit of information (the heads outcome) simply cannot provide the many bits of information needed to encode the distribution without substantial prior information.</span></span>
<span data-ttu-id="78e5d-248">同様に、以前の情報がないと、$p を知らなくても、このようなコインを完全に複製することはできません $ 。</span><span class="sxs-lookup"><span data-stu-id="78e5d-248">Similarly, without prior information we cannot perfectly clone a quantum state just as we cannot prepare an ensemble of such coins without knowing $p$.</span></span>

<span data-ttu-id="78e5d-249">クォンタムコンピューティングでは、情報は無料です。</span><span class="sxs-lookup"><span data-stu-id="78e5d-249">Information is not free in quantum computing.</span></span>
<span data-ttu-id="78e5d-250">測定された各 qubit は1ビットの情報を提供し、複製なしの定理は、システムに関する情報とそれに対して発生した問題の基本的なトレードオフを回避するために、攻撃を受ける可能性があるバックドアがないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="78e5d-250">Each qubit measured gives a single bit of information, and the No-Cloning Theorem shows that there is no backdoor that can be exploited to get around the fundamental tradeoff between information gained about the system and the disturbance invoked upon it.</span></span>
