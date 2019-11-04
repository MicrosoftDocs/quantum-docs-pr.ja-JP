---
title: ヨルダン-Wigner 表現 |Microsoft Docs
description: ヨルダン-Wigner 表現概念ドキュメント
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.jordanwigner
ms.openlocfilehash: f34233bc17ff68a9e04256959f8d79be2682c34f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184051"
---
# <a name="jordan-wigner-representation"></a><span data-ttu-id="41370-103">ヨルダン-Wigner 表現</span><span class="sxs-lookup"><span data-stu-id="41370-103">Jordan-Wigner Representation</span></span>

<span data-ttu-id="41370-104">2番目の量子化 Hamiltonians は $a ^ & ダガー $ (作成) と $a $ (annihilation) という観点からわかりやすくなっていますが、これらの操作は、quantum コンピューターでは基本的な操作ではありません。</span><span class="sxs-lookup"><span data-stu-id="41370-104">While second quantized Hamiltonians are conveniently represented in terms of $a^\dagger$ (creation) and $a$ (annihilation), these operations are not fundamental operations in quantum computers.</span></span>
<span data-ttu-id="41370-105">そのため、クォンタムコンピューターに実装する場合は、クォンタムコンピューターに実装できる一連の検索行列に演算子をマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="41370-105">As a result, if we wish it implement them on a quantum computer we need to map the operators to unitary matrices that can be implemented on a quantum computer.</span></span>
<span data-ttu-id="41370-106">ヨルダン– Wigner 表現は、このようなマップを1つ提供します。</span><span class="sxs-lookup"><span data-stu-id="41370-106">The Jordan–Wigner representation gives one such map.</span></span>
<span data-ttu-id="41370-107">ただし、Bravyi – Kitaev 表現などの他のものも存在し、独自の相対利点と欠点があります。</span><span class="sxs-lookup"><span data-stu-id="41370-107">However, others such as the Bravyi–Kitaev representation also exist and have their own relative advantages and disadvantages.</span></span>
<span data-ttu-id="41370-108">ヨルダン表現の主な利点は、単純であるということです。</span><span class="sxs-lookup"><span data-stu-id="41370-108">The main advantage of the Jordan-Wigner representation is its simplicity.</span></span>

<span data-ttu-id="41370-109">ヨルダン表現は、派生するために簡単に記述できます。</span><span class="sxs-lookup"><span data-stu-id="41370-109">The Jordan-Wigner representation is straight forward to derive.</span></span>
<span data-ttu-id="41370-110">State $ \ket{0}j $ は、spin 回転 $j $ が空であることを意味し、$ \ket{1}j $ はそれが占有されていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="41370-110">Recall that a state $\ket{0}_j$ implies that spin orbital $j$ is empty and $\ket{1}_j$ implies that it is occupied.</span></span>
<span data-ttu-id="41370-111">これは、qubits が特定のスピン回転の職業を自然に格納できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="41370-111">This means that qubits can naturally store the occupation of a given spin orbital.</span></span>
<span data-ttu-id="41370-112">次に、$a ^ & dagger_ \ket{0}j = \ket{1}_ $ および $a ^-\ket{1}j = $0 を設定します。</span><span class="sxs-lookup"><span data-stu-id="41370-112">We then have that $a^\dagger_j \ket{0}_j = \ket{1}_j$ and $a^\dagger_j \ket{1}_j = 0$.</span></span>
<span data-ttu-id="41370-113">\Begin{align} a ^ & dagger_ & = \begin{bmatrix}0 & 1 \\\ 0 & 0 \end{bmatrix} = \frac{X_j + iY_j}{2}、\nonumber\\\\ a_j & = \begin{bmatrix}0 & 0 \\\ 1 & 0/end{を確認するのは簡単です。bmatrix} = \frac{X_j-iY_j}{2}、\end{align} where $X j $ および $Y j $ は、qubit $Y $ で動作する $X p $ 演算子と-$j $ 演算子です。</span><span class="sxs-lookup"><span data-stu-id="41370-113">It is easy to verify that \begin{align} a^\dagger_j &= \begin{bmatrix}0 & 1 \\\ 0 &0 \end{bmatrix}=\frac{X_j + iY_j}{2}, \nonumber\\\\ a_j &= \begin{bmatrix}0 & 0 \\\ 1 &0 \end{bmatrix}=\frac{X_j - iY_j}{2}, \end{align} where $X_j$ and $Y_j$ are the Pauli-$X$ and -$Y$ operators acting on qubit $j$.</span></span>
<span data-ttu-id="41370-114">これは、1つのスピン回転の場合、量子コンピューターが理解しているユニタリ行列の観点から、作成演算子と annihilation 演算子を簡単に表すことができることを示しています。</span><span class="sxs-lookup"><span data-stu-id="41370-114">This shows that for a single spin orbital it is easy to represent creation and annihilation operators in terms of unitary matrices that quantum computers understand.</span></span>
<span data-ttu-id="41370-115">$X $ と $Y $ は、$a ^ \ ダガー $、$a $ はありません。</span><span class="sxs-lookup"><span data-stu-id="41370-115">Note that while $X$ and $Y$ are unitary $a^\dagger$ and $a$ are not.</span></span>
<span data-ttu-id="41370-116">このことがシミュレーションの課題になることは、後で説明します。</span><span class="sxs-lookup"><span data-stu-id="41370-116">We will see later that this does not pose a challenge for simulation.</span></span>

<span data-ttu-id="41370-117">残っている問題の1つは、上記の構築が1つのスピン回転に対して機能していても、2つ以上のスピン/ビットがあるシステムでは失敗することです。</span><span class="sxs-lookup"><span data-stu-id="41370-117">One problem that remains is that while the above construction works for a single spin orbital, it fails for systems with two or more spin orbitals.</span></span>
<span data-ttu-id="41370-118">Antisymmetic は、すべての $j $ と $k $ に対して、^ & dagger_ a ^ & daggerk =-a ^ & dagger_ $ を $a していることがわかっています。</span><span class="sxs-lookup"><span data-stu-id="41370-118">Since Fermions are antisymmetic, we know that $a^\dagger_j a^\dagger_k = - a^\dagger_k a^\dagger_j$ for any $j$ and $k$.</span></span>
<span data-ttu-id="41370-119">ただし、$ $ \ left (\frac{X_j-iY_j}{2} \ (\frac{X_k-iY_k}{2}\ right) = \ left (\frac{X_k-iY_k}{2}/right) \ left (\frac{X_j-iY_j}{2}\ right) のようになります。</span><span class="sxs-lookup"><span data-stu-id="41370-119">However, $$ \left(\frac{X_j - iY_j}{2}\right)\left(\frac{X_k - iY_k}{2}\right) = \left(\frac{X_k - iY_k}{2}\right) \left(\frac{X_j - iY_j}{2}\right).</span></span>
<span data-ttu-id="41370-120">$ $ つまり、2つの作成演算子は、必要に応じて commute を実行しません。</span><span class="sxs-lookup"><span data-stu-id="41370-120">$$ In other words, the two creation operators do not anti-commute as required.</span></span>
<span data-ttu-id="41370-121">これは、inelegant 方法では簡単に解決できます。</span><span class="sxs-lookup"><span data-stu-id="41370-121">This can be remedied though in a straightforward, if inelegant fashion.</span></span>
<span data-ttu-id="41370-122">この問題を解決するには、Pcommute の演算子は自然なアンチフィックスを持つことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="41370-122">The fix is to note that Pauli operators naturally anti-commute.</span></span>
<span data-ttu-id="41370-123">特に、$XZ =-ZX $ and $YZ =-ZY $ です。</span><span class="sxs-lookup"><span data-stu-id="41370-123">In particular, $XZ = -ZX$ and $YZ=-ZY$.</span></span>
<span data-ttu-id="41370-124">したがって、演算子の構築に $ operators $Z interspersing ことにより、適切な交換をエミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="41370-124">Thus, by interspersing $Z$ operators into the construction of the operator, we can emulate the correct anti-commutation.</span></span>
<span data-ttu-id="41370-125">完全な構築は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="41370-125">The full construction is as follows:</span></span> 

<span data-ttu-id="41370-126">\begin{align} a ^ & dagger_1 & = \ left (\frac{X-iY}{2}\ right) \ otimes 1, otimes 1/otimes 1/otimes-cドット/otimes 1,\\\\ a ^ \dagger_2 & = z/left (\frac{X-iY}{2}-right) \ otimes 1 \ otimes/otimes 1,、\\\\ ^ & dagger& = zotimes-left (\frac{X-iY}{2}\ right)-otimes 1, otimes/cドット/otimes 1,、および\\\\ & \ vドット\\\\ ^ \dagger_N & = zotimes zotimes & otimes/otimes/cドット/時刻Zotimes \ left (\frac{X-iY}{2})。</span><span class="sxs-lookup"><span data-stu-id="41370-126">\begin{align} a^\dagger_1 &= \left(\frac{X-iY}{2}\right)\otimes 1 \otimes 1 \otimes 1 \otimes \cdots \otimes 1,\\\\ a^\dagger_2 &= Z\otimes\left(\frac{X-iY}{2}\right)\otimes 1\otimes 1 \otimes \cdots \otimes 1,\\\\ a^\dagger_3 &= Z\otimes Z\otimes \left(\frac{X-iY}{2}\right)\otimes 1 \otimes \cdots \otimes 1,\\\\ &\vdots\\\\ a^\dagger_N &= Z\otimes Z\otimes Z\otimes Z \otimes \cdots \otimes Z\otimes \left(\frac{X-iY}{2}\right).</span></span> <span data-ttu-id="41370-127">& # {eq: JW} \end{align}</span><span class="sxs-lookup"><span data-stu-id="41370-127">\label{eq:JW} \end{align}</span></span>

<span data-ttu-id="41370-128">また、演算子を使用すると、数値演算子 (j $ $n) を表すのに便利です。</span><span class="sxs-lookup"><span data-stu-id="41370-128">It is also convenient to express the number operators, $n_j$, in terms of Pauli operators.</span></span>
<span data-ttu-id="41370-129">さいわいにも、$Z $ operators (ヨルダン-Wigner 文字列) の文字列は、この置換が行われた後にキャンセルされます。</span><span class="sxs-lookup"><span data-stu-id="41370-129">Thankfully, the strings of $Z$ operators (known as Jordan-Wigner strings) cancel after one makes this substitution.</span></span>
<span data-ttu-id="41370-130">これを行ってから (iZ_j $ $X を呼び出すと)、n_j = a ^ a_j = \frac{(1-Z_j)} というのは、= (){2}} になります。</span><span class="sxs-lookup"><span data-stu-id="41370-130">After carrying this out (and recalling that $X_jY_j=iZ_j$), we have \begin{equation} n_j = a^\dagger_j a_j = \frac{(1-Z_j)}{2}.</span></span>
<span data-ttu-id="41370-131">& # {2}</span><span class="sxs-lookup"><span data-stu-id="41370-131">\end{equation}</span></span>


## <a name="constructing-hamiltonians-in-jordan-wigner-representation"></a><span data-ttu-id="41370-132">ヨルダン-Wigner 表現でのの構築</span><span class="sxs-lookup"><span data-stu-id="41370-132">Constructing Hamiltonians in Jordan-Wigner Representation</span></span>

<span data-ttu-id="41370-133">Hamiltonian 表現を呼び出した後は、その後、すべての演算子の合計に対して、高速に変換されます。</span><span class="sxs-lookup"><span data-stu-id="41370-133">Once we have invoked the Jordan-Wigner representation translating the Hamiltonian to a sum of Pauli operators is straight forward.</span></span>
<span data-ttu-id="41370-134">1つは、Fermionic Hamiltonian の各 $a ^ & ダガー $ および $a $ 演算子を、上記の p の文字列に置き換えるだけです。</span><span class="sxs-lookup"><span data-stu-id="41370-134">One simply has to replace each of the $a^\dagger$ and $a$ operators in the Fermionic Hamiltonian with the strings of Pauli-operators given above.</span></span>
<span data-ttu-id="41370-135">この置換を実行するときには、Hamiltonian 内に含まれる用語のクラスは5つだけです。</span><span class="sxs-lookup"><span data-stu-id="41370-135">When one performs this substitution, there are only five classes of terms within the Hamiltonian.</span></span>
<span data-ttu-id="41370-136">これらの5つのクラスは、1つの本文で Hamiltonian、q $ と $p、q、r、s $ を $p 選択するさまざまな方法に対応しています。また、内の2つの本文の語句を使用します。</span><span class="sxs-lookup"><span data-stu-id="41370-136">These five classes correspond to the different ways we can pick the $p,q$ and $p,q,r,s$ in the one-body and the two-body terms in the Hamiltonian.</span></span>
<span data-ttu-id="41370-137">これら5つのクラス ($p > q > r > s $ と実際の値の orbitals) は、</span><span class="sxs-lookup"><span data-stu-id="41370-137">These five classes, for the case where $p>q>r>s$ and real-valued orbitals, are</span></span>

<span data-ttu-id="41370-138">\begin{align} h_ {pp} a_p ^ a_p & = \sum_p \frac{h_{pp}}{2}(1-Z_p)\\\\ h_ {pq} (a_p ^ \ ダガー a_q + a ^-dagger q a_p) & = \frac{h_{pq}}{2}\ left (\prod_{j = q + 1} ^ {p-1} Z_j) \left (X_pX_q + Y_pY_q\right)\\\\ h_ {pqqp} n_p n_q & = \frac{h_{pqqp}}{4}\ left (1-Z_p-Z_q + Z_pZ_q/right)\\\\ H_ {pqqp} & = \frac{h_{pqqr}}{2}\ left (\prod_{j =r + 1} ^ {p-1} Z_j/right) \ left (X_pX_r + Y_pY_r\right\\{2}) \\ H_ {pqrs} & = \frac{h_{pqrs}}{8}\prod_{j = s + 1} ^ {r-1} Z_j\prod_ {k = q + 1} ^ {p-1} Z_k/Big (XXXX-XXYY +XYXY\nonumber\\\\ & \qquad\qquad\qquad\qquad\qquad + YXXY + YXYX-YYXX\nonumber\\\\ & \qquad\qquad\qquad\qquad\qquad + XYYX + YYYY\Big) \end{align}</span><span class="sxs-lookup"><span data-stu-id="41370-138">\begin{align} h_{pp}a_p^\dagger a_p &= \sum_p \frac{h_{pp}}{2}(1 - Z_p)\\\\ h_{pq}(a_p^\dagger a_q + a^\dagger_q a_p) &= \frac{h_{pq}}{2}\left(\prod_{j=q+1}^{p-1} Z_j \right)\left( X_pX_q + Y_pY_q\right)\\\\ h_{pqqp} n_p n_q &=  \frac{h_{pqqp}}{4}\left(1-Z_p - Z_q +Z_pZ_q \right)\\\\ H_{pqqr} &= \frac{h_{pqqr}}{2}\left(\prod_{j=r+1}^{p-1} Z_j \right)\left( X_pX_r + Y_pY_r\right)\left(\frac{1-Z_q}{2}\right)\\\\ H_{pqrs} &= \frac{h_{pqrs}}{8}\prod_{j=s+1}^{r-1} Z_j\prod_{k=q+1}^{p-1} Z_k \Big(XXXX - XXYY+XYXY\nonumber\\\\ &\qquad\qquad\qquad\qquad\qquad+YXXY+YXYX-YYXX\nonumber\\\\ &\qquad\qquad\qquad\qquad\qquad+XYYX+YYYY\Big) \end{align}</span></span>

<span data-ttu-id="41370-139">このような Hamiltonians を手動で生成する場合は、これらの置換規則を適用するだけで済みますが、大規模な分子の場合は、何百万もの Hamiltonian の用語で構成される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="41370-139">While generating such Hamiltonians by hand only requires applying these replacement rules, doing so would be infeasible for large molecules which can consist of millions of Hamiltonian terms.</span></span>
<span data-ttu-id="41370-140">別の方法として、Hamiltonian の `FermionHamiltonian` 表現を指定して、`JordanWignerEncoding` を自動的に作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="41370-140">As an alternative, we can automatically construct the `JordanWignerEncoding` given a `FermionHamiltonian` representation of the Hamiltonian.</span></span>

```csharp
    // We load the namespace containing fermion and Pauli objects. 
    using Microsoft.Quantum.Chemistry.Fermion;
    using Microsoft.Quantum.Chemistry.Pauli;
    
    // We create an example `FermionHamiltonian` instance.
    var fermionHamiltonian = new FermionHamiltonian();

    // We convert this Fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);
```

<span data-ttu-id="41370-141">この形式で Hamiltonians を構築した後は、クォンタムシミュレーションアルゴリズムのホストを使用して、$e ^ {-iHt} $ によって生成された dynamics を一連の基本ゲートにコンパイルできます (ユーザー定義可能なエラー許容範囲内)。</span><span class="sxs-lookup"><span data-stu-id="41370-141">Once the Hamiltonians are constructed in this form, we can use a host of quantum simulation algorithms to compile the dynamics generated by $e^{-iHt}$ into a sequence of elementary gates (within some user definable error tolerance).</span></span>
<span data-ttu-id="41370-142">ここでは、アルゴリズムのドキュメントで、クォンタムシミュレーション、qubitization、および Trotter – Suzuki の数式の最も人気のある2つの方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="41370-142">We discuss the two most popular methods for quantum simulation, qubitization and Trotter–Suzuki formulas, in the algorithmic documentation.</span></span> <span data-ttu-id="41370-143">Hamiltonian シミュレーションライブラリには、両方のメソッドの実装が用意されています。</span><span class="sxs-lookup"><span data-stu-id="41370-143">We provide implementations for both methods in the Hamiltonian simulation library.</span></span>
