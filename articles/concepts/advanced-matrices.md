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
- $
- $
- $
- $
- $$
- $$
- $$
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
ms.openlocfilehash: 71923247121eae6a1d4e26d2664d8e547370ba3a
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269458"
---
# <a name="advanced-matrix-concepts"></a>高度なマトリックスの概念 #

マトリックスの操作を[*Eigenvalues、固有ベクトル*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)、[*指数*](https://en.wikipedia.org/wiki/Matrix_exponential)に拡張しました。これにより、クォンタムアルゴリズムの記述と実装に必要なツールの基本的なセットが形成されます。

## <a name="eigenvalues-and-eigenvectors"></a>Eigenvalues と固有ベクトル ##

$M $ 正方形の行列にし、 $ すべてのゼロベクトルではないベクター (つまり、すべてのエントリが $0 であるベクトル) にする $v $ ます。

$ [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) $ $Mv = cv が $ いくつかの $c である場合、$v は $M の eigenvector であると言い $ ます。 $C $ は、eigenvector $v に対応する[*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)です $ 。 一般に、マトリックス $M は $ ベクターを他のベクターに変換することがありますが、eigenvector は特殊なので、数値で乗算される点を除いて、変更されません。 $V $ が eigenvalue $c の eigenvector である場合 $ 、$av も、 $ 同じ eigenvalue を持つ eigenvector (0 以外のすべての $a) になり $ ます。

たとえば、id 行列の場合、すべてのベクター $v $ は eigenvalue $1 の eigenvector になり $ ます。

もう1つの例として、対角線に0以外のエントリのみがある[*対角線行列*](https://en.wikipedia.org/wiki/Diagonal_matrix)$D を考えてみ $ ます。

$ $ \ begin{bmatrix}
d_1 & 0 & 0 \\ \\ 0 & d_2 & 0 \\ \\ 0 & 0 & d_3 \ end{ bmatrix } です。
$$

ベクター

$ $ \ begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \ end{ bmatrix } , \ begin{ bmatrix } 0 \\ \\ 1 \\ \\ 0 \end{bmatrix} および \ begin{ bmatrix } 0 0 \\ \\ \\ \\ 1\end{bmatrix}$$

このマトリックスの固有ベクトルは、固有値 $d _1 $ 、$d _2 $ 、および $d、それぞれ3つ $ です。 $D _1 $ 、$d _2 $ 、および $d (_d $ ) が個別の数値の場合、これらのベクター (およびそのマルチプル) はマトリックス $D の唯一の固有ベクトル $ です。 一般に、対角線マトリックスの場合は、固有値と固有ベクトルを簡単に読み取ることができます。 固有値は、対角線に表示されるすべての数値であり、それぞれの固有ベクトルは1つのエントリが $1 $ 、残りのエントリが $0 に等しい単位ベクトルです $ 。

上の例では、$D の固有ベクトルが $ $3 次元ベクターの基礎を形成していることに注意して $ ください。 ベースはベクターのセットであり、ベクターを線形の組み合わせとして書き込むことができます。 より明示的には、$v _1 $ 、$v _2 $ 、および $v は、 $ $v 任意 $ $ の数の数値 $v _1 $ 、a_1 _2 $ 、v_1 として a_2 v_2 = a_3 v_3 + $a $a + $a として記述することができ $ ます。

Hermitian matrix (自己 adjoint とも呼ばれます) は、独自の複雑な共役に相当する複雑な正方形行列であることを思い出してください。これに対して、1つのユニタリ行列は複雑な共役と同じ逆の四角形行列です。
実質的には、Hermitian およびユニタリマトリックスの場合は、クォンタムコンピューティングで検出された唯一のマトリックスで、次のことをアサートする、[*スペクトル定理*](https://en.wikipedia.org/wiki/Spectral_theorem)と呼ばれる一般的な結果があります。 Hermitian またはの $M マトリックスの場合は、 $ $ $M = U ^-ダガー D U ( $ 斜めのマトリックスの $D) が存在 $U し $ ます。 さらに、$D の対角線のエントリは、 $ $M の値になり $ ます。

固有ベクトルの固有値とを計算する方法については既に説明して $ います $D。 この定理を使用すると、$v $ が $ eigenvalue $c を持つ $D の場合 $ ($Dv = cv の場合)、$U $ ^ $ eigenvector は $ eigenvalue $M を持つ $c のになり $ ます。 これは、

$ $M (U ^ \ ダガー v) = U ^ \ ダガー D U (U ^-ダガー v) = U ^ \ ダガー D (U U ^-ダガー) v = U ^-ダガー D v = c U ^ \ ダガー v. $ $

## <a name="matrix-exponentials"></a>マトリックス指数
指数関数と完全に同じように[*行列指数*](https://en.wikipedia.org/wiki/Matrix_exponential)を定義することもできます。  マトリックス $A の行列指数は、 $ として表すことができます。

$ $ e ^ A/ = bold 完了 + A + \frac{A ^ 2 } {2!}+ \frac{A ^ 3 } {3!}+ \ cドット $ $

このことが重要なのは、クォンタムの機械的時間の進化は、$e ^ {iB } $ For Hermitian matrix $B という形式の1つの要素で構成され $ ます。  このため、matrix 指数の実行はクォンタムコンピューティングの基本的な部分であり、そのような Q # はこれらの操作を記述するための組み込みルーチンを提供しています。
従来のコンピューターで行列指数を計算するには、多くの方法がありますが、通常は数値の近い数値でしかしが発生します。  「 [*Cleve Moler とチャールズ Van ローン」を参照してください。"Nineteen あいまいにより、マトリックスの指数を計算することができます。"関連する課題の詳細については、「SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) 」を参照してください。

マトリックスの指数を計算する方法を理解する最も簡単な方法は、そのマトリックスの固有値と固有ベクトルを使用することです。  具体的に言うと、前に説明したスペクトル定理は、すべての Hermitian またはマトリックスに対して、$A の $U が存在し、 $ $ 斜線マトリックス $D $ $A = U ^-ダガー D U になっていることを示して $ います。 Unitarity ティのプロパティにより、$A ^ 2 = U ^ \ ダガー D ^ 2 U $ と同様に、任意の power $p $ $A ^ p = u ^ \ ダガー d ^ p u と同様になり $ ます。 これを演算子指数の演算子定義に置き換えると、次のようになります。

$ $ e ^ A = U ^ \ (& A)-左 (\ bold 完了 + D + \frac{D ^ 2 } {2!})+/cドット \ 右) U = u ^ & # 1 & 1 bmatrix } ; \ exp (D_ {11 } ) & 0 &/cdpi &0 \\\\ 0 & \ exp (D_ {22 } ) &/cドット 0 \ &/vドット & (& a) & & \\\\ \\\\ & & (&{NN } ) \ end{ bmatrix } U. $ $

つまり、マトリックスの eigenbasis に変換する場合 $A 行列 $ 指数を計算することは、マトリックスの eigenbasis の通常の指数を計算することと同じです。  クォンタムコンピューティングにおける多くの操作には、matrix 指数の実行が含まれています。そのため、マトリックスの eigenbasis に変換することにより、演算子指数が頻繁に表示されるようになり、このガイドの後半で説明する Trotter – Suzuki-スタイルのクォンタムシミュレーションメソッドなど、多くのクォンタムアルゴリズムが基礎となります。

$B がユニタリと Hermitian の両方である場合は、もう1つの便利なプロパティがあり $ ます。つまり、$B = B ^ {-1 } = b ^ \ ダガーの $ 後 $B ^ 2/ = bold が終了 $ します。 上記のマトリックス指数の展開にこのルールを適用することにより、$/bold と $B の用語をまとめてグループ化することで $ $ 、id $x の任意の実数の値を確認できます。 $

$ $e ^ {iBx } = \ bold 完了 \ cos (x) + ibx sin (x) $ $


収容. この方法は特に便利です。これは、$B の次元が指数関数的に大きい場合でも、$B が Hermitian である場合に、特殊なケースでは、matrix 指数の操作に関する理由を理解できるためです $ $ 。
