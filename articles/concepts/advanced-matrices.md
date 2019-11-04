---
title: 高度なマトリックスの概念 |Microsoft Docs
description: 高度なマトリックスの概念
author: QuantumWriter
uid: microsoft.quantum.concepts.matrix-advanced
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: f87b3bcd19d2f98fea2a9724a280781a78c4cbb9
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183762"
---
# <a name="advanced-matrix-concepts"></a>高度なマトリックスの概念 #

マトリックスの操作を[*Eigenvalues、固有ベクトル*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)、[*指数*](https://en.wikipedia.org/wiki/Matrix_exponential)に拡張しました。これにより、クォンタムアルゴリズムの記述と実装に必要なツールの基本的なセットが形成されます。

## <a name="eigenvalues-and-eigenvectors"></a>Eigenvalues と固有ベクトル ##

$ を正方形行列に $M し、$ を、すべてのゼロベクトルではないベクター (つまり、すべてのエントリが $0 $ に等しいベクトル) を $v します。

$V $ は、$ if $Mv = cv $ ($ の数値 $c) $M の[*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)であると言います。 $C $ は、eigenvector $v $ に対応する[*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)です。 一般に、$ $M $ はベクターを他のベクターに変換することがありますが、eigenvector は特殊です。これは、数値で乗算される点を除いて、変更されていないためです。 $V $ が eigenvalue $c $ の eigenvector である場合、$av $ も、同じ eigenvalue を持つ eigenvector (0 以外の任意の $a $) であることに注意してください。

たとえば、id 行列の場合、すべてのベクトル $v $ は eigenvalue $1 $ の eigenvector になります。

もう1つの例として、斜線に0以外のエントリのみを持つ、$ $D の[*対角線のマトリックス*](https://en.wikipedia.org/wiki/Diagonal_matrix)を考えてみます。

$ $ \begin{bmatrix} d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.
$$

ベクター

$ $ \begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}、\begin{bmatrix}0 \\\\ 1 \\\\ 0 \ end {bmatrix} および \begin{bmatrix}0 \\\\ 0 \\\\1 \ 終了 {bmatrix} $ $

このマトリックスの固有ベクトルは、固有値 $d _1 $、$d _2 $、および $d/3 $ にそれぞれ含まれています。 $D _1 $、$d _2 $、$d、3 $ が個別の数値の場合、これらのベクトル (およびそのマルチプル) は $D マトリックスの $ $ の唯一の固有ベクトルです。 一般に、対角線マトリックスの場合は、固有値と固有ベクトルを簡単に読み取ることができます。 固有値は、対角線に表示されるすべての数値であり、それぞれの固有ベクトルは、1つのエントリが $1 $、残りのエントリが $0 $ に等しい単位ベクトルです。

上の例では、$D $ の固有ベクトルが $ 3 $ 次元ベクターのベースになっていることに注意してください。 ベースはベクターのセットであり、ベクターを線形の組み合わせとして書き込むことができます。 より明示的には、$v _1 $、$v _2 $、および $v、3 $ $v 任意の数値を $v = a_1 v_1 + a_2 v_2 + a_3 v_3 $ として書き込むことができます (たとえば、_1 $、$a _2 $、$a)。

Hermitian matrix (自己 adjoint とも呼ばれます) は、独自の複雑な共役に相当する複雑な正方形行列であることを思い出してください。これに対して、1つのユニタリ行列は複雑な共役と同じ逆の四角形行列です。
Hermitian およびユニタリマトリックスの場合は、基本的に、クォンタムコンピューティングで検出された唯一のマトリックスである、[*スペクトル定理*](https://en.wikipedia.org/wiki/Spectral_theorem)と呼ばれる一般的な結果があります。これは、次のことをアサートします。 Hermitian または行列 $M $ の場合は、$M = U ^-ダガー D U $ (対角線のあるマトリックスの $D $) を $U するために、'% ' を使用します。 さらに、$D $ の対角線のエントリは $M $ の固有値になります。

$D $ のように、対角線行列の固有値と固有ベクトルを計算する方法は既にわかっています。 この定理を使用すると、$ が $D $ の eigenvector (eigenvalue $c $、つまり $Dv = cv $) である $v 場合、$U ^ eigenvector は eigenvalue $M $ で $c $ のになります。 これは、

$ $M (U ^ \ ダガー v) = U ^ \ ダガー D U (U ^-ダガー v) = U ^ \ ダガー D (U U ^-ダガー) v = U ^-ダガー D v = c U ^ \ ダガー v. $ $

## <a name="matrix-exponentials"></a>マトリックス指数
指数関数と完全に同じように[*行列指数*](https://en.wikipedia.org/wiki/Matrix_exponential)を定義することもできます。  マトリックス $A $ の行列指数は、として表すことができます。

$ $ e ^ A = \ bold 完了 + A + \frac{A ^ 2} {2!}+ \frac{A ^ 3} {3!}+ \ cドット $ $

このことが重要なのは、クォンタムの機械的時間の進化は、Hermitian matrix $B $ の $e ^ {iB} $ という形式の1つの要素で構成されています。  このため、matrix 指数の実行はクォンタムコンピューティングの基本的な部分であり、そのような Q # はこれらの操作を記述するための組み込みルーチンを提供しています。
従来のコンピューターで行列指数を計算するには、多くの方法がありますが、通常は数値の近い数値でしかしが発生します。  「 [*Cleve Moler とチャールズ Van ローン」を参照してください。"Nineteen あいまいにより、マトリックスの指数を計算することができます。"関連する課題の詳細については、「SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) 」を参照してください。

マトリックスの指数を計算する方法を理解する最も簡単な方法は、そのマトリックスの固有値と固有ベクトルを使用することです。  具体的には、前に説明したスペクトル定理は、すべての Hermitian またはマトリックスに $A $ と、$A = U ^ \ ダガー D U $ のような、$ $D $ という斜線行列が $U 存在することを示しています。  Unitarity のプロパティが原因で、^ 2 = U ^ \ ダガー D ^ 2 U $ $A、任意のパワー $p $ $A ^ p = U ^ \ ダガー D ^ p U $ と同様になりました。  これを演算子指数の演算子定義に置き換えると、次のようになります。

$ $ e ^ A = U ^ \ ← \ left (\ bold done + D + \frac{D ^ 2} {2!}+/cdpi-right) U = U ^ \ ダガー \begin{bmatrix}\exp (D_{11}) & 0 & & 0\\\\ 0 & \ exp (D_{22}) &/cドット & 0\\\\ \ vドット & \ vドット & \ dドット & \ vドット\\\\ 0& 0 &/cドット & \ exp (D_ {NN}) \end{bmatrix} U $ $

つまり、マトリックスの eigenbasis に変換する場合 $A $ の後に行列指数を計算することは、マトリックスの eigenbasis の通常の指数を計算することと同じです。  クォンタムコンピューティングにおける多くの操作には、matrix 指数の実行が含まれています。そのため、マトリックスの eigenbasis に変換することで、演算子指数の実行が簡単になり、次のような多くのクォンタムアルゴリズムの基礎となります。Trotter –このガイドの後半で説明する Suzuki のクォンタムシミュレーション方法。

$B $ がユニタリと Hermitian の両方である場合は、もう1つの便利なプロパティです。つまり、$B = B ^{-1}= B ^ \ ダガー $ then $B ^ 2 = \ bold done $ です。 このルールを上記のマトリックス指数の展開に適用し、$ & bold $ and $B $ terms をグループ化することにより、$-$x $ と $ terms を一緒にグループ化することによって、

$ $e ^ {iBx} = \ bold 完了 \ cos (x) + ibx sin (x) $ $


収容. この手法は特に便利です。これは、$B $ の次元が指数関数的に大きい場合でも、$ が Hermitian との両方がある場合でも、特殊な $B ケースでは、matrix 指数のアクションについての理由を許容できるためです。
