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
# <a name="jordan-wigner-representation"></a>ヨルダン-Wigner 表現

2番目の量子化 Hamiltonians は $a ^ & ダガー $ (作成) と $a $ (annihilation) という観点からわかりやすくなっていますが、これらの操作は、quantum コンピューターでは基本的な操作ではありません。
そのため、クォンタムコンピューターに実装する場合は、クォンタムコンピューターに実装できる一連の検索行列に演算子をマップする必要があります。
ヨルダン– Wigner 表現は、このようなマップを1つ提供します。
ただし、Bravyi – Kitaev 表現などの他のものも存在し、独自の相対利点と欠点があります。
ヨルダン表現の主な利点は、単純であるということです。

ヨルダン表現は、派生するために簡単に記述できます。
State $ \ket{0}j $ は、spin 回転 $j $ が空であることを意味し、$ \ket{1}j $ はそれが占有されていることを意味します。
これは、qubits が特定のスピン回転の職業を自然に格納できることを意味します。
次に、$a ^ & dagger_ \ket{0}j = \ket{1}_ $ および $a ^-\ket{1}j = $0 を設定します。
\Begin{align} a ^ & dagger_ & = \begin{bmatrix}0 & 1 \\\ 0 & 0 \end{bmatrix} = \frac{X_j + iY_j}{2}、\nonumber\\\\ a_j & = \begin{bmatrix}0 & 0 \\\ 1 & 0/end{を確認するのは簡単です。bmatrix} = \frac{X_j-iY_j}{2}、\end{align} where $X j $ および $Y j $ は、qubit $Y $ で動作する $X p $ 演算子と-$j $ 演算子です。
これは、1つのスピン回転の場合、量子コンピューターが理解しているユニタリ行列の観点から、作成演算子と annihilation 演算子を簡単に表すことができることを示しています。
$X $ と $Y $ は、$a ^ \ ダガー $、$a $ はありません。
このことがシミュレーションの課題になることは、後で説明します。

残っている問題の1つは、上記の構築が1つのスピン回転に対して機能していても、2つ以上のスピン/ビットがあるシステムでは失敗することです。
Antisymmetic は、すべての $j $ と $k $ に対して、^ & dagger_ a ^ & daggerk =-a ^ & dagger_ $ を $a していることがわかっています。
ただし、$ $ \ left (\frac{X_j-iY_j}{2} \ (\frac{X_k-iY_k}{2}\ right) = \ left (\frac{X_k-iY_k}{2}/right) \ left (\frac{X_j-iY_j}{2}\ right) のようになります。
$ $ つまり、2つの作成演算子は、必要に応じて commute を実行しません。
これは、inelegant 方法では簡単に解決できます。
この問題を解決するには、Pcommute の演算子は自然なアンチフィックスを持つことに注意してください。
特に、$XZ =-ZX $ and $YZ =-ZY $ です。
したがって、演算子の構築に $ operators $Z interspersing ことにより、適切な交換をエミュレートできます。
完全な構築は次のとおりです。 

\begin{align} a ^ & dagger_1 & = \ left (\frac{X-iY}{2}\ right) \ otimes 1, otimes 1/otimes 1/otimes-cドット/otimes 1,\\\\ a ^ \dagger_2 & = z/left (\frac{X-iY}{2}-right) \ otimes 1 \ otimes/otimes 1,、\\\\ ^ & dagger& = zotimes-left (\frac{X-iY}{2}\ right)-otimes 1, otimes/cドット/otimes 1,、および\\\\ & \ vドット\\\\ ^ \dagger_N & = zotimes zotimes & otimes/otimes/cドット/時刻Zotimes \ left (\frac{X-iY}{2})。 & # {eq: JW} \end{align}

また、演算子を使用すると、数値演算子 (j $ $n) を表すのに便利です。
さいわいにも、$Z $ operators (ヨルダン-Wigner 文字列) の文字列は、この置換が行われた後にキャンセルされます。
これを行ってから (iZ_j $ $X を呼び出すと)、n_j = a ^ a_j = \frac{(1-Z_j)} というのは、= (){2}} になります。
& # {2}


## <a name="constructing-hamiltonians-in-jordan-wigner-representation"></a>ヨルダン-Wigner 表現でのの構築

Hamiltonian 表現を呼び出した後は、その後、すべての演算子の合計に対して、高速に変換されます。
1つは、Fermionic Hamiltonian の各 $a ^ & ダガー $ および $a $ 演算子を、上記の p の文字列に置き換えるだけです。
この置換を実行するときには、Hamiltonian 内に含まれる用語のクラスは5つだけです。
これらの5つのクラスは、1つの本文で Hamiltonian、q $ と $p、q、r、s $ を $p 選択するさまざまな方法に対応しています。また、内の2つの本文の語句を使用します。
これら5つのクラス ($p > q > r > s $ と実際の値の orbitals) は、

\begin{align} h_ {pp} a_p ^ a_p & = \sum_p \frac{h_{pp}}{2}(1-Z_p)\\\\ h_ {pq} (a_p ^ \ ダガー a_q + a ^-dagger q a_p) & = \frac{h_{pq}}{2}\ left (\prod_{j = q + 1} ^ {p-1} Z_j) \left (X_pX_q + Y_pY_q\right)\\\\ h_ {pqqp} n_p n_q & = \frac{h_{pqqp}}{4}\ left (1-Z_p-Z_q + Z_pZ_q/right)\\\\ H_ {pqqp} & = \frac{h_{pqqr}}{2}\ left (\prod_{j =r + 1} ^ {p-1} Z_j/right) \ left (X_pX_r + Y_pY_r\right\\{2}) \\ H_ {pqrs} & = \frac{h_{pqrs}}{8}\prod_{j = s + 1} ^ {r-1} Z_j\prod_ {k = q + 1} ^ {p-1} Z_k/Big (XXXX-XXYY +XYXY\nonumber\\\\ & \qquad\qquad\qquad\qquad\qquad + YXXY + YXYX-YYXX\nonumber\\\\ & \qquad\qquad\qquad\qquad\qquad + XYYX + YYYY\Big) \end{align}

このような Hamiltonians を手動で生成する場合は、これらの置換規則を適用するだけで済みますが、大規模な分子の場合は、何百万もの Hamiltonian の用語で構成される可能性があります。
別の方法として、Hamiltonian の `FermionHamiltonian` 表現を指定して、`JordanWignerEncoding` を自動的に作成することもできます。

```csharp
    // We load the namespace containing fermion and Pauli objects. 
    using Microsoft.Quantum.Chemistry.Fermion;
    using Microsoft.Quantum.Chemistry.Pauli;
    
    // We create an example `FermionHamiltonian` instance.
    var fermionHamiltonian = new FermionHamiltonian();

    // We convert this Fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);
```

この形式で Hamiltonians を構築した後は、クォンタムシミュレーションアルゴリズムのホストを使用して、$e ^ {-iHt} $ によって生成された dynamics を一連の基本ゲートにコンパイルできます (ユーザー定義可能なエラー許容範囲内)。
ここでは、アルゴリズムのドキュメントで、クォンタムシミュレーション、qubitization、および Trotter – Suzuki の数式の最も人気のある2つの方法について説明します。 Hamiltonian シミュレーションライブラリには、両方のメソッドの実装が用意されています。
