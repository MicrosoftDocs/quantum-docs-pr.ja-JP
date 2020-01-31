---
title: ヨルダン-Wigner 表現 |Microsoft Docs
description: ヨルダン-Wigner 表現概念ドキュメント
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.jordanwigner
ms.openlocfilehash: 5d9038e440a2022547395e889e149a531a7ef818
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820540"
---
# <a name="jordan-wigner-representation"></a><span data-ttu-id="4bdde-103">ヨルダン-Wigner 表現</span><span class="sxs-lookup"><span data-stu-id="4bdde-103">Jordan-Wigner Representation</span></span>

<span data-ttu-id="4bdde-104">2番目の量子化 Hamiltonians は $a ^ & ダガー $ (作成) と $a $ (annihilation) という観点からわかりやすくなっていますが、これらの操作は、quantum コンピューターでは基本的な操作ではありません。</span><span class="sxs-lookup"><span data-stu-id="4bdde-104">While second quantized Hamiltonians are conveniently represented in terms of $a^\dagger$ (creation) and $a$ (annihilation), these operations are not fundamental operations in quantum computers.</span></span>
<span data-ttu-id="4bdde-105">そのため、クォンタムコンピューターに実装する場合は、クォンタムコンピューターに実装できる一連の検索行列に演算子をマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bdde-105">As a result, if we wish it implement them on a quantum computer we need to map the operators to unitary matrices that can be implemented on a quantum computer.</span></span>
<span data-ttu-id="4bdde-106">ヨルダン– Wigner 表現は、このようなマップを1つ提供します。</span><span class="sxs-lookup"><span data-stu-id="4bdde-106">The Jordan–Wigner representation gives one such map.</span></span>
<span data-ttu-id="4bdde-107">ただし、Bravyi – Kitaev 表現などの他のものも存在し、独自の相対利点と欠点があります。</span><span class="sxs-lookup"><span data-stu-id="4bdde-107">However, others such as the Bravyi–Kitaev representation also exist and have their own relative advantages and disadvantages.</span></span>
<span data-ttu-id="4bdde-108">ヨルダン表現の主な利点は、単純であるということです。</span><span class="sxs-lookup"><span data-stu-id="4bdde-108">The main advantage of the Jordan-Wigner representation is its simplicity.</span></span>

<span data-ttu-id="4bdde-109">ヨルダン表現は、派生するために簡単に記述できます。</span><span class="sxs-lookup"><span data-stu-id="4bdde-109">The Jordan-Wigner representation is straight forward to derive.</span></span>
<span data-ttu-id="4bdde-110">State $ \ket{0}_j $ は、spin 回転 $j $ が空であることを意味し、$ \ket{1}_j $ はそれが占有されていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="4bdde-110">Recall that a state $\ket{0}_j$ implies that spin orbital $j$ is empty and $\ket{1}_j$ implies that it is occupied.</span></span>
<span data-ttu-id="4bdde-111">これは、qubits が特定のスピン回転の職業を自然に格納できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="4bdde-111">This means that qubits can naturally store the occupation of a given spin orbital.</span></span>
<span data-ttu-id="4bdde-112">次に、$a ^ \ dagger_j \ket{0}_j = \ket{1}_j $ and $a ^ \ dagger_j \ket{1}_j = $0 を設定します。</span><span class="sxs-lookup"><span data-stu-id="4bdde-112">We then have that $a^\dagger_j \ket{0}_j = \ket{1}_j$ and $a^\dagger_j \ket{1}_j = 0$.</span></span>
<span data-ttu-id="4bdde-113">\Begin{align} a ^ \ dagger_j & = \begin{bmatrix}0 & 0 \\\ 1 & 0 \end{bmatrix} = \frac{X_j iY_j}{2}であることを確認するのは簡単です。 \nonumber\\\\ a_j & = \begin{bmatrix}0 & 1 \\\ 0 & 0 \end{bmatrix} = \frac{X_j + iY_j}{2}、\end{align} where $X _j $ および $Y _j $ は、qubit $X $ に対して動作する、p $ および-$Y $ 演算子です。</span><span class="sxs-lookup"><span data-stu-id="4bdde-113">It is easy to verify that \begin{align} a^\dagger_j &= \begin{bmatrix}0 & 0 \\\ 1 &0 \end{bmatrix}=\frac{X_j - iY_j}{2}, \nonumber\\\\ a_j &= \begin{bmatrix}0 & 1 \\\ 0 &0 \end{bmatrix}=\frac{X_j + iY_j}{2}, \end{align} where $X_j$ and $Y_j$ are the Pauli-$X$ and -$Y$ operators acting on qubit $j$.</span></span>

>[!NOTE]
> <span data-ttu-id="4bdde-114">Q # $ \ket{0}$ state は、$Z $ 演算子の + 1 eigenstate を表します。</span><span class="sxs-lookup"><span data-stu-id="4bdde-114">In Q# the $\ket{0}$ state represents the +1 eigenstate of the $Z$ operator.</span></span> <span data-ttu-id="4bdde-115">物理的な領域では、{0}$ は、低エネルギーの接地状態を表します。したがって、$Z $ 演算子の-1 eigenstate を表します。</span><span class="sxs-lookup"><span data-stu-id="4bdde-115">In some areas of physics $\ket{0}$ represents the low-energy ground state and thus the -1 eigenstate of the $Z$ operator.</span></span> <span data-ttu-id="4bdde-116">そのため、いくつかの数式は一般的な文献とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4bdde-116">Therefore some formulas might differ from popular literature.</span></span>

<span data-ttu-id="4bdde-117">化学ライブラリでは、$ \ket{0}$ を使用して、未使用のスピン回転を表します。</span><span class="sxs-lookup"><span data-stu-id="4bdde-117">In the chemistry library we use $\ket{0}$ to represent an unoccupied spin-orbital.</span></span>
<span data-ttu-id="4bdde-118">これは、1つのスピン回転の場合、量子コンピューターが理解しているユニタリ行列の観点から、作成演算子と annihilation 演算子を簡単に表すことができることを示しています。</span><span class="sxs-lookup"><span data-stu-id="4bdde-118">This shows that for a single spin orbital it is easy to represent creation and annihilation operators in terms of unitary matrices that quantum computers understand.</span></span>
<span data-ttu-id="4bdde-119">$X $ と $Y $ は、$a ^ \ ダガー $、$a $ はありません。</span><span class="sxs-lookup"><span data-stu-id="4bdde-119">Note that while $X$ and $Y$ are unitary $a^\dagger$ and $a$ are not.</span></span>
<span data-ttu-id="4bdde-120">このことがシミュレーションの課題になることは、後で説明します。</span><span class="sxs-lookup"><span data-stu-id="4bdde-120">We will see later that this does not pose a challenge for simulation.</span></span>

<span data-ttu-id="4bdde-121">残っている問題の1つは、上記の構築が1つのスピン回転に対して機能していても、2つ以上のスピン/ビットがあるシステムでは失敗することです。</span><span class="sxs-lookup"><span data-stu-id="4bdde-121">One problem that remains is that while the above construction works for a single spin orbital, it fails for systems with two or more spin orbitals.</span></span>
<span data-ttu-id="4bdde-122">Antisymmetic は、^ \ dagger_j ^ \ dagger_k =-a ^ \ dagger_k a ^ \ dagger_j $、$j $、$k $ という $a があることがわかっています。</span><span class="sxs-lookup"><span data-stu-id="4bdde-122">Since Fermions are antisymmetic, we know that $a^\dagger_j a^\dagger_k = - a^\dagger_k a^\dagger_j$ for any $j$ and $k$.</span></span>
<span data-ttu-id="4bdde-123">ただし、$ $ \ left (\frac{X_j-iY_j}{2}→) \ left (\frac{X_k-iY_k}{2}\ right) = \ left (\frac{X_k} iY_k} 右)、left (\frac{{2}-X_j} iY_j) です。</span><span class="sxs-lookup"><span data-stu-id="4bdde-123">However, $$ \left(\frac{X_j - iY_j}{2}\right)\left(\frac{X_k - iY_k}{2}\right) = \left(\frac{X_k - iY_k}{2}\right) \left(\frac{X_j - iY_j}{2}\right).</span></span>
<span data-ttu-id="4bdde-124">$ $ つまり、2つの作成演算子は、必要に応じて commute を実行しません。</span><span class="sxs-lookup"><span data-stu-id="4bdde-124">$$ In other words, the two creation operators do not anti-commute as required.</span></span>
<span data-ttu-id="4bdde-125">これは、inelegant 方法では簡単に解決できます。</span><span class="sxs-lookup"><span data-stu-id="4bdde-125">This can be remedied though in a straightforward, if inelegant fashion.</span></span>
<span data-ttu-id="4bdde-126">この問題を解決するには、Pcommute の演算子は自然なアンチフィックスを持つことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4bdde-126">The fix is to note that Pauli operators naturally anti-commute.</span></span>
<span data-ttu-id="4bdde-127">特に、$XZ =-ZX $ and $YZ =-ZY $ です。</span><span class="sxs-lookup"><span data-stu-id="4bdde-127">In particular, $XZ = -ZX$ and $YZ=-ZY$.</span></span>
<span data-ttu-id="4bdde-128">したがって、演算子の構築に $ operators $Z interspersing ことにより、適切な交換をエミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="4bdde-128">Thus, by interspersing $Z$ operators into the construction of the operator, we can emulate the correct anti-commutation.</span></span>
<span data-ttu-id="4bdde-129">完全な構築は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4bdde-129">The full construction is as follows:</span></span> 

<span data-ttu-id="4bdde-130">\begin{align} a ^ \ dagger_1 & = \ left (\frac{X-iY}{2}→) \ otimes/otimes 1/otimes 1/otimes/cドット-otimes 1、\\\\ ^ \ dagger_2 & = Z\frac{X-iY}-left ({2}→)/otimes 1 \ otimes 1/otimes/cドット/otimes 1\\\\ ^ dagger_3 & = zotimes-left (\frac{X-iY}{2}\ right)-otimes 1/otimes-cドット/otimes 1,\\\\ &/vドット\\\\ ^ \ dagger_N & = zotimes & otimes/otimes z/otimes & cドット/otimes Z \ otimesotimes \ left (\frac{X-iY}{2})。</span><span class="sxs-lookup"><span data-stu-id="4bdde-130">\begin{align} a^\dagger_1 &= \left(\frac{X-iY}{2}\right)\otimes 1 \otimes 1 \otimes 1 \otimes \cdots \otimes 1,\\\\ a^\dagger_2 &= Z\otimes\left(\frac{X-iY}{2}\right)\otimes 1\otimes 1 \otimes \cdots \otimes 1,\\\\ a^\dagger_3 &= Z\otimes Z\otimes \left(\frac{X-iY}{2}\right)\otimes 1 \otimes \cdots \otimes 1,\\\\ &\vdots\\\\ a^\dagger_N &= Z\otimes Z\otimes Z\otimes Z \otimes \cdots \otimes Z\otimes \left(\frac{X-iY}{2}\right).</span></span> <span data-ttu-id="4bdde-131">& # {eq: JW} \end{align}</span><span class="sxs-lookup"><span data-stu-id="4bdde-131">\label{eq:JW} \end{align}</span></span>

<span data-ttu-id="4bdde-132">また、演算子として、数値演算子 $n _j $ を表すのも便利です。</span><span class="sxs-lookup"><span data-stu-id="4bdde-132">It is also convenient to express the number operators, $n_j$, in terms of Pauli operators.</span></span>
<span data-ttu-id="4bdde-133">さいわいにも、$Z $ operators (ヨルダン-Wigner 文字列) の文字列は、この置換が行われた後にキャンセルされます。</span><span class="sxs-lookup"><span data-stu-id="4bdde-133">Thankfully, the strings of $Z$ operators (known as Jordan-Wigner strings) cancel after one makes this substitution.</span></span>
<span data-ttu-id="4bdde-134">これを実行した後 ($X _jY_j = iZ_j $) をリコールした後は、& lt; の n_j = a ^ \ dagger_j a_j = \frac{(1-Z_j)}{2}があります。</span><span class="sxs-lookup"><span data-stu-id="4bdde-134">After carrying this out (and recalling that $X_jY_j=iZ_j$), we have \begin{equation} n_j = a^\dagger_j a_j = \frac{(1-Z_j)}{2}.</span></span>
<span data-ttu-id="4bdde-135">& # {2}</span><span class="sxs-lookup"><span data-stu-id="4bdde-135">\end{equation}</span></span>


## <a name="constructing-hamiltonians-in-jordan-wigner-representation"></a><span data-ttu-id="4bdde-136">ヨルダン-Wigner 表現でのの構築</span><span class="sxs-lookup"><span data-stu-id="4bdde-136">Constructing Hamiltonians in Jordan-Wigner Representation</span></span>

<span data-ttu-id="4bdde-137">Hamiltonian 表現を呼び出した後は、その後、すべての演算子の合計に対して、高速に変換されます。</span><span class="sxs-lookup"><span data-stu-id="4bdde-137">Once we have invoked the Jordan-Wigner representation translating the Hamiltonian to a sum of Pauli operators is straight forward.</span></span>
<span data-ttu-id="4bdde-138">1つは、Fermionic Hamiltonian の各 $a ^ & ダガー $ および $a $ 演算子を、上記の p の文字列に置き換えるだけです。</span><span class="sxs-lookup"><span data-stu-id="4bdde-138">One simply has to replace each of the $a^\dagger$ and $a$ operators in the Fermionic Hamiltonian with the strings of Pauli-operators given above.</span></span>
<span data-ttu-id="4bdde-139">この置換を実行するときには、Hamiltonian 内に含まれる用語のクラスは5つだけです。</span><span class="sxs-lookup"><span data-stu-id="4bdde-139">When one performs this substitution, there are only five classes of terms within the Hamiltonian.</span></span>
<span data-ttu-id="4bdde-140">これらの5つのクラスは、1つの本文で Hamiltonian、q $ と $p、q、r、s $ を $p 選択するさまざまな方法に対応しています。また、内の2つの本文の語句を使用します。</span><span class="sxs-lookup"><span data-stu-id="4bdde-140">These five classes correspond to the different ways we can pick the $p,q$ and $p,q,r,s$ in the one-body and the two-body terms in the Hamiltonian.</span></span>
<span data-ttu-id="4bdde-141">これら5つのクラス ($p > q > r > s $ と実際の値の orbitals) は、</span><span class="sxs-lookup"><span data-stu-id="4bdde-141">These five classes, for the case where $p>q>r>s$ and real-valued orbitals, are</span></span>

<span data-ttu-id="4bdde-142">\begin{align} h_ {pp} a_p ^ \frac{a_p & = \ sum_p \frac{h_ {pp}}{2}(1-Z_p)\\\\ h_ {pq} (a_p ^ \ ダガー a_q + a ^ \ dagger_q a_p) & = h_ {pq}}{2}/left (\ prod_ {j = q + 1} ^ {p-1} Z_j \ 右) \ 左 (X_pX_q + Y_pY_q 右)\\\\ h_ {pqqp} n_p n_q & = \frac{h_ {pqqp}}{4}Z_p Z_q Z_pZ_q {pqqp}\\= \frac{\\ {pqqp}} H_/左 (\ & {j =) h_/左 (\{2}{j =r + 1} ^ {p-1} Z_j \ 左 (X_pX_r + Y_pY_r \ 右) \ 左 (\frac{1-Z_q}{2}\ 右)\\\\ H_ {pqrs} & = \frac{h_ {pqrs}}{8}\ prod_ {j = s + 1} ^ {r-1} Z_j \ prod_ {k = q + 1} ^ {p-1} Z_k \ Big (XXXX-XXYY + XYXY\nonumber\\\\ & \qquad\qquad\qquad\qquad\qquad + YXXY + YXYX-YYXX\nonumber\\\\ & \qquad\qquad\qquad\qquad\qquad + XYYX + YYYY\Big) \end{align}</span><span class="sxs-lookup"><span data-stu-id="4bdde-142">\begin{align} h_{pp}a_p^\dagger a_p &= \sum_p \frac{h_{pp}}{2}(1 - Z_p)\\\\ h_{pq}(a_p^\dagger a_q + a^\dagger_q a_p) &= \frac{h_{pq}}{2}\left(\prod_{j=q+1}^{p-1} Z_j \right)\left( X_pX_q + Y_pY_q\right)\\\\ h_{pqqp} n_p n_q &=  \frac{h_{pqqp}}{4}\left(1-Z_p - Z_q +Z_pZ_q \right)\\\\ H_{pqqr} &= \frac{h_{pqqr}}{2}\left(\prod_{j=r+1}^{p-1} Z_j \right)\left( X_pX_r + Y_pY_r\right)\left(\frac{1-Z_q}{2}\right)\\\\ H_{pqrs} &= \frac{h_{pqrs}}{8}\prod_{j=s+1}^{r-1} Z_j\prod_{k=q+1}^{p-1} Z_k \Big(XXXX - XXYY+XYXY\nonumber\\\\ &\qquad\qquad\qquad\qquad\qquad+YXXY+YXYX-YYXX\nonumber\\\\ &\qquad\qquad\qquad\qquad\qquad+XYYX+YYYY\Big) \end{align}</span></span>

<span data-ttu-id="4bdde-143">このような Hamiltonians を手動で生成する場合は、これらの置換規則を適用するだけで済みますが、大規模な分子の場合は、何百万もの Hamiltonian の用語で構成される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4bdde-143">While generating such Hamiltonians by hand only requires applying these replacement rules, doing so would be infeasible for large molecules which can consist of millions of Hamiltonian terms.</span></span>
<span data-ttu-id="4bdde-144">別の方法として、Hamiltonian の `FermionHamiltonian` 表現を指定して、`JordanWignerEncoding` を自動的に作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="4bdde-144">As an alternative, we can automatically construct the `JordanWignerEncoding` given a `FermionHamiltonian` representation of the Hamiltonian.</span></span>

```csharp
    // We load the namespace containing fermion and Pauli objects. 
    using Microsoft.Quantum.Chemistry.Fermion;
    using Microsoft.Quantum.Chemistry.Pauli;
    
    // We create an example `FermionHamiltonian` instance.
    var fermionHamiltonian = new FermionHamiltonian();

    // We convert this Fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);
```

<span data-ttu-id="4bdde-145">この形式で Hamiltonians を構築した後は、クォンタムシミュレーションアルゴリズムのホストを使用して、$e ^ {-iHt} $ によって生成された dynamics を一連の基本ゲートにコンパイルできます (ユーザー定義可能なエラー許容範囲内)。</span><span class="sxs-lookup"><span data-stu-id="4bdde-145">Once the Hamiltonians are constructed in this form, we can use a host of quantum simulation algorithms to compile the dynamics generated by $e^{-iHt}$ into a sequence of elementary gates (within some user definable error tolerance).</span></span>
<span data-ttu-id="4bdde-146">ここでは、アルゴリズムのドキュメントで、クォンタムシミュレーション、qubitization、および Trotter – Suzuki の数式の最も人気のある2つの方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4bdde-146">We discuss the two most popular methods for quantum simulation, qubitization and Trotter–Suzuki formulas, in the algorithmic documentation.</span></span> <span data-ttu-id="4bdde-147">Hamiltonian シミュレーションライブラリには、両方のメソッドの実装が用意されています。</span><span class="sxs-lookup"><span data-stu-id="4bdde-147">We provide implementations for both methods in the Hamiltonian simulation library.</span></span>
