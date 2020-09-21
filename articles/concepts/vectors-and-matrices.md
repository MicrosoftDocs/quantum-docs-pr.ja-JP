---
title: 量子コンピューティングのベクトルとマトリックスの説明: ベクターとマトリックスを操作する方法の基本について説明します。
author: QuantumWriter uid: benbra: v-ms. date: 12/11/2017 ms. topic: article no loc (場所の記事):
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
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

# <a name="vectors-and-matrices"></a>ベクターと行列

ベクターとマトリックスについては、クォンタムコンピューティングを理解するために重要な知識があります。 次の簡単な概要を説明します。また、読者には、 *Strang、G. (1993) などの線形代数の標準参照を読むことをお勧めします。線形代数 (Vol. 3) の概要。Wellesley、MA: Wellesley を押す* か、 [線形代数](http://joshua.smcvt.edu/linearalgebra/)などのオンライン参照をクリックします。

次元 (またはサイズ) n の列ベクター (または単なる [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $ v $ は、 $ $ $ 列として配置された n 個の $ 複素数 $ (v_1、v_2、\ lドット、v_n) のコレクションです $ 。

$$v =\begin{bmatrix}
v_1\\\\
v_2\\\\
\ vドット\\\\
v_n \end{bmatrix}$$

Vector v の標準 $ $ は $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $ として定義されています。 ベクターは、基準が1である場合は単位基準 (または [*単位ベクトル*](https://en.wikipedia.org/wiki/Unit_vector)と呼ばれます) と呼ばれ $ $ ます。 [*ベクター v の adjoint*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ は、 $ $ v ^ \dagger $ として定義されています。は、 $ \* $ 複雑な共役を示す次の行ベクトルとして定義されています。

$$\begin{bmatrix}v_1 \\\\ \ vドット \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix} v_1 ^ * & \cdots & v_n ^ *\end{bmatrix}$$

2つのベクトルを乗算する最も一般的な方法は、 [*内部製品*](https://en.wikipedia.org/wiki/Inner_product_space)(ドット積とも呼ばれます) を使用することです。  内側の製品は、あるベクターの射影を別のベクターに提供し、1つのベクターを他のより単純なベクターの合計として表現する方法を説明するうえで非常に重要です。  U と v の間の内部積 $ $ $ $ ( $ \left \langle u, v) \right \rangle $ は、として定義されます。

$$
\langleu、v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n
$$

この表記法では、ベクター v の標準を $ $ v として記述することもでき $ \sqrt { \langle \rangle } $ ます。

ベクターと数値 c を乗算し $ $ て、エントリに c を乗算した新しいベクターを作成することができ $ $ ます。 また、2つのベクター $ u $ と v を追加して、 $ $ エントリが u と v のエントリの合計である新しいベクターを作成することもでき $ $ $ $ ます。 これらの操作を次に示します。

$$\mathrm{If } ~ u=\begin{bmatrix}
u_1\\\\
u_2\\\\
\ vドット\\\\
u_n \end{bmatrix} ~ \mathrm { と}~
画像 =\begin{bmatrix}
    v_1\\\\
    v_2\\\\
    \ vドット\\\\
    v_n \end{bmatrix} 、 ~ \mathrm {}~
au + bv =\begin{bmatrix}
au_1 + bv_1\\\\
au_2 + bv_2\\\\
\ vドット\\\\
au_n + bv_n \end{bmatrix} 。
$$

サイズ m n の [*マトリックス*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) は、 $ \times $ $ $ $ $ $ $ 次に示すように、m 行と n 列に配置された、全数の複素数のコレクションです。

$$M = 
\begin{bmatrix}
M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1n}\\\\
M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\
\ddots\\\\
M_ { m1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { があります}\\\\
\end{bmatrix}.$$

ディメンション n のベクトルは、 $ $ サイズ n 1 のマトリックスであることに注意して $ \times $ ください。 ベクターの場合と同様に、マトリックスと数値 c を乗算して、すべてのエントリに c を乗算した $ $ 新しい行列を取得できます $ $ 。また、同じサイズの2つのマトリックスを追加して、2つの行列の各エントリの合計であるエントリを持つ新しいマトリックスを生成することもできます。 

## <a name="matrix-multiplication-and-tensor-products"></a>マトリックス乗算とその他の製品

また、次元 m n の2つ $ の行列 m $ $ \times $ と $ $ 次元 n p の n を乗算し $ \times $ て、 $ 次のように dimension m p の新しいマトリックス p を取得する $ $ \times $ こともできます。

\begin{align}
&\begin{bmatrix}
    M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1n}\\\\
    M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\
    \ddots\\\\
    M_ { m1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { があります}
\end{bmatrix}
\begin{bmatrix}
N_ { 11 } ~~ N_ { 12 } ~~ \cdots ~~ N_ { 1p}\\\\
N_ { 21 } ~~ N_ { 22 } ~~ \cdots ~~ N_ { 2p}\\\\
\ddots\\\\
N_ { n1 } ~~ N_ { n2 } ~~ \cdots ~~ N_ { np}
\end{bmatrix}=\begin{bmatrix}
P_ { 11 } ~~ P_ { 12 } ~~ \cdots ~~ P_ { 1p}\\\\
P_ { 21 } ~~ P_ { 22 } ~~ \cdots ~~ P_ { 2p}\\\\
\ddots\\\\
P_ { m1 } ~~ P_ { m2 } ~~ \cdots ~~ P_ { mp}
\end{bmatrix}
\end{align}

P のエントリは $ $ $ P_ { ik } = \sum _j M_ { ij } N_ { jk } $ です。 たとえば、P_ 11 のエントリは、 $ { } $ $ $ N の最初の列を含む M の最初の行の内部積です $ $ 。ベクターは単にマトリックスの特殊なケースであるため、この定義はマトリックスベクトル乗算まで拡張されることに注意してください。 

考慮するすべてのマトリックスは、行と列の数が等しいか、またはベクター (1 つの列にのみ対応する) である、正方形のマトリックス $ $ です。 1つの特殊な正方形[*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix)の行列は、次のように、 $ \boldone $ すべての対角線の要素が1に等しく、 $ $ 残りの要素が0に等しい $ $ id 行列です。

$$\boldone=\begin{bmatrix}
1 ~~ 0 ~~ \cdots ~~ 0\\\\
0 ~~ 1 ~~ \cdots ~~ 0\\\\
~~ \ddots\\\\
0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix} 。$$

B 行列 a の $ $ 場合は、"a" という行列 $ があるとし $ [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) $ = = \boldone $ ます。 マトリックスの逆のは存在しない必要がありますが、存在する場合は一意であり、これは $ ^-1 を意味し { } $ ます。 

任意のマトリックス $ m の場合 $ 、m の adjoint または共役転置は $ $ マトリックス $ N であり、 $ $ N_ { ij } = M_ { ji に } ^ \* $ なります。 M の adjoint $ $ は、通常 m ^ と示されてい $ \dagger $ ます。 マトリックス $ u $ は[*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) $ 、UU ^ u \dagger = ^ \dagger u = \boldone $ または同等の $ u ^ { -1 } = u ^ \dagger $ と同等のものです。  たとえば、最も重要なのは、ベクトルの基準を維持することです。  これは、 

$$\langlev、v2.0、v、 \rangle = \dagger = ^ \dagger u ^ { -1 } U v = ^ \dagger u ^ \dagger u v u v = \langle 、u v \rangle$$  

マトリックス $ m $ は、m m ^ の場合は[*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix)と言い $ = \dagger $ ます。

最後に、サイズが m n の2つのマトリックス m の Kronecker [*製品 (また*](https://en.wikipedia.org/wiki/Tensor_product) は nq $ $ $ \times $ $ $ $ p q) は \times 、 $ $ サイズ mp の大きなマトリックス p m n で、次のように = \otimes $ $ \times $ M と n から取得され $ $ $ $ ます。

\begin{align}
    M \otimes N &=
    \begin{bmatrix}
        M_ { 11 } ~~ \cdots ~~ M_ { 1n }\\\\
        \ddots\\\\
        M_ { m1 } ~~ \cdots ~~ M_ { 中  }
    \end{bmatrix}
    \otimes
    \begin{bmatrix}
        N_ { 11 } ~~ \cdots ~~ N_ { 1q  }\\\\
        \ddots\\\\
        N_ { p1 } ~~ \cdots ~~ N_ { pq}
    \end{bmatrix}\\\\
    &=
    \begin{bmatrix}
        M_ { 11 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~ 
        M_ { 1n } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1n } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}\\\\
        \ddots\\\\
        M_ { m1 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~ 
        M_ { } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}
    \end{bmatrix}.
\end{align}

次に例をいくつか示します。

$$
    \begin{bmatrix}
        a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}=
    \begin{bmatrix}
        a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}
        \\\\[1.5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}
    \end{bmatrix}
    =\begin{bmatrix}c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\\end{bmatrix}
$$

and

$$
    \begin{bmatrix}
        a \ b \\\\ c \ d \end{bmatrix}
    \otimes 
    \begin{bmatrix}
        e \ f \\\\ g \ h \end{bmatrix}
     =
    \begin{bmatrix}
    ある\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    b\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    \\\\[1em] c\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    a\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    \end{bmatrix}
    =
    \begin{bmatrix}
    ae \ af \ bf \\\\
    ag \ ah \ bg \ bh \\\\
    ce \ cf \ de \ df \\\\
    cg \ ch \ dg \ dh \end{bmatrix} 。
$$

数値表記と製品を囲む最後の便利な規則として、ベクター $ v またはマトリックス m の場合は、 $ $ $ $ { \otimes } $ $ { \otimes } $ $ n フォールドの繰り返しが繰り返されてい $ ます。  次に例を示します。

\begin{align}
&\begin{bmatrix}1 \\\\ 0 \end{bmatrix} ^ { \otimes 1 1 } = \begin{bmatrix} \\\\ 0 \end{bmatrix} 、 \qquad \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ 0 0 0 \\\\ \\\\ \end{bmatrix} 、 \qquad \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ -1 \\\\ -1 \\\\ 1 \end{bmatrix} 、\\\\
  &\begin{bmatrix}0 1 1 1 0 1 0 1 1 0 & \\\\ & \end{bmatrix} ^ { \otimes } = \begin{bmatrix} & \\\\ & \end{bmatrix} 、 \qquad \begin{bmatrix} 0 & 1 1 0 \\\\ & 2 \end{bmatrix} ^ { \otimes } = \begin{bmatrix} 0 & & & \\\\ & & & \\\\ & & & \\\\ & & & \end{bmatrix} 0 0 1 0 0 1 0 = 1 0 0 を0にします。
\end{align}
