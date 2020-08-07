---
title: 高度なマトリックスの概念説明: クォンタムアルゴリズムの記述とシミュレーションに使用される基本的なツールである固有ベクトル、eigenvalues、および matrix 指数について説明します。
author: QuantumWriter uid: microsoft. quantum................: nawiebe@microsoft.com ms. date: 12/11/2017 ms. topic: article no loc:
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "$$$"
- "$$$"
- "$$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---
# <a name="advanced-matrix-concepts"></a>高度なマトリックスの概念 #

マトリックスの操作を[*Eigenvalues、固有ベクトル*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)、[*指数*](https://en.wikipedia.org/wiki/Matrix_exponential)に拡張しました。これにより、クォンタムアルゴリズムの記述と実装に必要なツールの基本的なセットが形成されます。

## <a name="eigenvalues-and-eigenvectors"></a>Eigenvalues と固有ベクトル ##

$M を $ 正方形行列にし、 $ v は $ すべてゼロベクトルではないベクター (つまり、すべてのエントリが0に等しいベクトル) に $ し $ ます。

$ $ たとえば、 [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)があると $ $ $ します。この場合、 = 数 c の Mv cv が発生 $ $ $ します。 $C $ は eigenvector v に対応する[*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)であると言い $ $ ます。 一般に、マトリックス $ M は $ ベクターを他のベクターに変換することがありますが、eigenvector は特殊なものです。これは、数値で乗算される点を除いて、変更されていないためです。 $V $ が eigenvalue c の eigenvector である場合 $ $ 、 $ $ $ 同じ eigenvalue を持つ av は eigenvector (0 以外の a の場合) でも $ あることに注意してください。

たとえば、id 行列の場合、すべての vector $ v $ は eigenvalue 1 の eigenvector $ に $ なります。

もう1つの例と[*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix)して、対角線 $ $ に0以外のエントリのみを持つ対角線行列 D を考えてみます。

$$
\begin{bmatrix}
d_1 & 0 0 0 & d_2 0 0 0 \\\\ & & \\\\ & & d_3 \end{bmatrix} です。
$$

ベクター

$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix} 、 \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \end{bmatrix} 、 \begin{bmatrix} 0 \\\\ 0 \\\\ 1\end{bmatrix}$$

このマトリックスの固有ベクトルは $ $ 、それぞれ d_1、 $ d_2 $ 、および $ d_3 $ です。 $D_1 $ 、 $ d_2 $ 、 $ d_3 が個別の数値の場合 $ 、これらのベクター (およびそのマルチプル) はマトリックス d の唯一の固有ベクトルです $ $ 。一般に、対角線マトリックスの場合は、固有値と固有ベクトルを簡単に読み取ることができます。 固有値は、対角線に表示されるすべての数値であり、それぞれの固有ベクトルは1つのエントリが1で、 $ $ 残りのエントリが0に等しい単位ベクターです $ $ 。

上の例では、D の固有ベクトル $ が $ 3 次元ベクトルのベースになっていることに注意して $ $ ください。 ベースはベクターのセットであり、ベクターを線形の組み合わせとして書き込むことができます。 より明示的、 $ v_1 $ 、 $ v_2 $ 、および v_3 は、 $ $ $ $ $ = $ 何らかの数値 $ v_1 $ 、 $ a_2 $ 、および v_2 $ $ に対して v a_1 a_3 + v_3 a_1 + a_2 a_3 として記述することができます。

Hermitian matrix (自己 adjoint とも呼ばれます) は複雑な四角形行列で、独自の複素共役転置と同じであることに注意してください。さらに、ユニタリ行列は、その逆が adjoint または複雑な共役転置と等しい複合正方形行列です。
基本的には、Hermitian およびユニタリ行列は、クォンタムコンピューティングで検出された唯一のマトリックスで、次をアサートする、[*スペクトル定理*](https://en.wikipedia.org/wiki/Spectral_theorem)と呼ばれる一般的な結果があります。 Hermitian またはマトリックス m の場合は、 $ $ 1 つの $ $ $ = \dagger $ 対角線のマトリックス d に $ 対し $ て m u ^ D u が使用されます。さらに、D の対角線のエントリは $ $ M の固有値になり $ $ ます。

固有ベクトルの固有値とを計算する方法は既にわかって $ $ います D。この定理を使用して、 $ v $ が $ $ eigenvalue c の eigenvector ( $ $ つまり、Dv cv) である場合、 $ = $ $ U ^ \dagger v は $ $ $ eigenvalue c の eigenvector になり $ $ ます。 これは、

$$M (U ^ \dagger v) = u ^ \dagger d u (u ^ \dagger v) = U ^ \dagger d (u u ^ \dagger ) v = u ^ \dagger d v = c u ^ \dagger v$$

## <a name="matrix-exponentials"></a>マトリックス指数
指数関数と完全に同じように[*行列指数*](https://en.wikipedia.org/wiki/Matrix_exponential)を定義することもできます。  マトリックス a の行列指数は $ 、 $ として表すことができます。

$$
e ^ A = \boldone + a + \frac { a ^ 2 } { 2! } + \frac {^ 3 } { 3!}+\cdots
$$

このことが重要なのは、クォンタムの機械的な時間の進化は、 $ { } $ Hermitian matrix B の e ^ iB 形式 $ のユニタリ行列によって記述されるためです $ 。 このため、matrix 指数の実行はクォンタムコンピューティングの基本的な部分であり、そのため、 Q# これらの操作を記述するための組み込みルーチンが用意されています。
従来のコンピューターで行列指数を計算するには、多くの方法がありますが、通常は数値の近い数値でしかしが発生します。  「 [*Cleve Moler とチャールズ Van ローン」を参照してください。"Nineteen あいまいにより、マトリックスの指数を計算することができます。"関連する課題の詳細については、「SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) 」を参照してください。

マトリックスの指数を計算する方法を理解する最も簡単な方法は、そのマトリックスの固有値と固有ベクトルを使用することです。  具体的には、前に説明したスペクトル定理では、すべての Hermitian または行列に対して、1つのユニタリ行列が存在し、その中に " $ $ $ $ $ $ u ^ D u" などの対角線行列 $ = \dagger $ があることが示されています。 Unitarity ティのプロパティにより、 $ ^ 2 = u ^ \dagger d ^ 2 u $ と同様に、任意の power $ p $ $ a ^ p = U ^ \dagger d ^ p u $ が使用されています。 これを演算子指数の演算子定義に置き換えると、次のようになります。

$$
e ^ A = U ^ \dagger \left ( \boldone + d + \frac { d ^ 2 } { 2! } + \cdots \right )U = u ^ \dagger \begin{bmatrix} \ exp (D_ { 11 } ) & 0 & \cdots & 0 \\\\ 0 & \ exp (D_ { 22 } ) 0 \ (vドット \)-vドット & \cdots & \\\\ & & \ddots & \\\\ 0 & 0 & \cdots & \ exp (D_ { NN } ) \end{bmatrix} U。$$

つまり、マトリックス A の eigenbasis に変換する場合、行列 $ 指数を $ 計算することは、マトリックスの eigenbasis の通常の指数を計算することと同じです。  クォンタムコンピューティングにおける多くの操作には、matrix 指数の実行が含まれています。そのため、マトリックスの eigenbasis に変換することにより、演算子指数が頻繁に表示されるようになり、このガイドの後半で説明する Trotter – Suzuki-スタイルのクォンタムシミュレーションメソッドなど、多くのクォンタムアルゴリズムが基礎となります。

B がユニタリと Hermitian の両方である場合は、もう1つの便利なプロパティがあり $ $ ます。つまり、 $ b = b ^ { -1 b ^、 } = \dagger $ $ b ^ 2 = \boldone $ のようになります。 上記の行列指数の展開にこのルールを適用することにより、と B の用語をグループ化することで $ \boldone $ $ $ 、任意の実数 $ x の id について確認できます $ 。

$$e ^ { ibx } = \boldone \ cos (x) + ibx sin (x)$$


収容. この方法は特に便利です。 b の次元が指数関数的に大きい場合でも、b $ $ $ が Hermitian である場合でも、マトリックス指数のアクションに関する理由があるためです $ 。
