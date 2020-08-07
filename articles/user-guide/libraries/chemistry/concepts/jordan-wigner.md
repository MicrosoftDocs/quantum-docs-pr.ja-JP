---
title: ヨルダン-Wigner 表現
description: ヨルダン Hamiltonian 表現について説明します。これにより、クォンタムコンピューターでより簡単に実装できるように、その演算子が、より簡単に実装できるようになります。
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.jordanwigner
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9f1455ebbecf6a3500ec11a5196e7662455c9a78
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869513"
---
# <a name="jordan-wigner-representation"></a>ヨルダン-Wigner 表現

2番目の量子化 Hamiltonians は $a ^ & ダガー $ (作成) と $a $ (annihilation) という観点からわかりやすくなっていますが、これらの操作は、quantum コンピューターでは基本的な操作ではありません。
そのため、クォンタムコンピューターに実装する場合は、クォンタムコンピューターに実装できる一連の検索行列に演算子をマップする必要があります。
ヨルダン– Wigner 表現は、このようなマップを1つ提供します。
ただし、Bravyi – Kitaev 表現などの他のものも存在し、独自の相対利点と欠点があります。
ヨルダン表現の主な利点は、単純であるということです。

ヨルダン表現は、派生するために簡単に記述できます。
State $ \ket {0} _j $ は、spin 回転 $j $ が空であることを意味し、$ \ket {1} _j $ はそれが占有されていることを意味します。
これは、qubits が特定のスピン回転の職業を自然に格納できることを意味します。
次に、$a ^ \ dagger_j \ket {0} _j = \ket {1} _j $ および $a ^ \ dagger_j \ket {1} _j = $0 を設定します。
\Begin{align} a ^ \ dagger_j &= \begin{bmatrix}0 & 0 \\ \ 1 &0 \end{bmatrix} = \frac{X_j-iY_j} {2} 、\nonumber \\ \\ a_j &= \begin{bmatrix}0 & 1 \\ \ 0 &0 \end{bmatrix} = \frac{X_j + iY_j}、\end{align} という確認は簡単です {2} 。ここで、$X _j $ および $Y _j $ は、Qubit $X $ で動作する p $ 演算子および-$Y $ 演算子です。

>[!NOTE]
> Q#$ \Ket $ state は、$ {0} operator $Z の + 1 eigenstate を表します。 物理的な領域によっては、エネルギーの \ket {0} $ が低エネルギーの接地状態を表しています。したがって、$ operator $Z $ 演算子の-1 eigenstate が示されます。 そのため、いくつかの数式は一般的な文献とは異なる場合があります。

化学ライブラリでは、$ \ket $ を使用して、 {0} 未使用のスピン回転を表します。
これは、1つのスピン回転の場合、量子コンピューターが理解しているユニタリ行列の観点から、作成演算子と annihilation 演算子を簡単に表すことができることを示しています。
$X $ と $Y $ は、$a ^ \ ダガー $、$a $ はありません。
このことがシミュレーションの課題になることは、後で説明します。

残っている問題の1つは、上記の構築が1つのスピン回転に対して機能していても、2つ以上のスピン/ビットがあるシステムでは失敗することです。
Antisymmetic は、^ \ dagger_j ^ \ dagger_k =-a ^ \ dagger_k a ^ \ dagger_j $、$j $、$k $ という $a があることがわかっています。
ただし、$ $-left (\frac{X_j-iY_j} {2} \ right) \ left (\frac{X_k-iY_k} {2} \ right) = \ left (\frac{X_k} \ right) {2} \ left (\frac{iY_k-X_j} {2} \ right)。
$ $ つまり、2つの作成演算子は、必要に応じて commute を実行しません。
これは、inelegant 方法では簡単に解決できます。
この問題を解決するには、Pcommute の演算子は自然なアンチフィックスを持つことに注意してください。
特に、$XZ =-ZX $ and $YZ =-ZY $ です。
したがって、演算子の構築に $ operators $Z interspersing ことにより、適切な交換をエミュレートできます。
完全な構築は次のとおりです。 

\begin{align} a ^ \ dagger_1 &= \ left (\frac{X-iY})/otimes 1, otimes 1, otimes/otimes/otimes {2} /otimes 1, \\ \\ ^ \ dagger_2 &= Z\frac{X-iY} (\frac{X-iY} {2} )-otimes 1 \ otimes 1/otimes/cドット/otimes 1、 \\ \\ ^ \ dagger_3 &= zotimes-left ()/otimes/otimes 1、otimes {2} 、cドット、otimes 1、およびです。 \\ \\ & \ vドット \\ \\ a ^ \ dagger_N &= zotimes {2} zo times & lt;/o times & lt; \frac{X-iY}; o times-←/otimes/left ()。 & # {eq: JW} \end{align}

また、演算子として、数値演算子 $n _j $ を表すのも便利です。
さいわいにも、$Z $ operators (ヨルダン-Wigner 文字列) の文字列は、この置換が行われた後にキャンセルされます。
これを実行した後 (および $X _jY_j = iZ_j $) を呼び出した後は、& lt;、"n_j = a ^ \ dagger_j a_j = \frac{(1-Z_j)} {2} です。
\end{equation}


## <a name="constructing-hamiltonians-in-jordan-wigner-representation"></a>ヨルダン-Wigner 表現でのの構築

Hamiltonian 表現を呼び出した後は、その後、すべての演算子の合計に対して、高速に変換されます。
1つは、Fermionic Hamiltonian の各 $a ^ & ダガー $ および $a $ 演算子を、上記の p の文字列に置き換えるだけです。
この置換を実行するときには、Hamiltonian 内に含まれる用語のクラスは5つだけです。
これらの5つのクラスは、1つの本文で Hamiltonian、q $ と $p、q、r、s $ を $p 選択するさまざまな方法に対応しています。また、内の2つの本文の語句を使用します。
これら5つのクラス ($p>q>r>s $ と実際の値の orbitals) は、

\begin{align} h_ {pp} a_p ^ \ ダガー a_p &= \ sum_p \frac{h_ {pp}} {2} (1-Z_p) \\ \\ h_ {pq} (a_p ^ \ ダガー a_q + a ^ \ dagger_q a_p) &= \frac{h_ {pq}} {2} \ 左 (\ prod_ {j = q + 1} ^ {p-1} Z_j 右) \ 左 (X_pX_q + Y_pY_q \ 右) \\ \\ h_ {pqqp} n_p n_q &= \frac{h_ {pqqp}} {4} \ 左 (1-Z_p + Z_q + 右) \\ \\ Z_pZ_q {pqqp} H_ = \frac{&{pqqp}} \ {2} left (\ prod_ {j = r + 1} ^ {p-1} Z_j \ 右) \ 左 (X_pX_r + Y_pY_r 右) \ 左 (\frac{1-Z_q} \ 右) H_ {pqqp} {2} \\ \\ &= \frac{h_ {pqqp}} {8} \ prod_ {j = s + 1} ^ {r-1} Z_j \ prod_ {k = q + 1} ^ {p-1} Z_k \ Big (XXXX-xxyy + XYXY\nonumber \\ \\ & \qquad\qquad\qquad\qquad\qquad + yxxy + YXYX-YYXX\nonumber \\ \\ & \qquad\qquad\qquad\qquad\qquad + xyyx + YYYY\Big) \end{align}

このような Hamiltonians を手動で生成する場合は、これらの置換規則を適用するだけで済みますが、大規模な分子の場合は、何百万もの Hamiltonian の用語で構成される可能性があります。
代わりに、 `JordanWignerEncoding` Hamiltonian の表現を指定してを自動的に作成することもでき `FermionHamiltonian` ます。

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
