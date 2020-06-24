---
title: 量子コンピューティングのベクトルと行列
description: ベクターとマトリックスを操作する方法の基本について説明します。
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
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
ms.openlocfilehash: f9d4e14742b7d06a6e90af0902b31fbdf17aedab
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269543"
---
# <a name="vectors-and-matrices"></a>ベクターと行列

ベクターとマトリックスについては、クォンタムコンピューティングを理解するために重要な知識があります。 次の簡単な概要を説明します。また、読者には、 *Strang、G. (1993) などの線形代数の標準参照を読むことをお勧めします。線形代数 (Vol. 3) の概要。Wellesley、MA: Wellesley を押す*か、[線形代数](http://joshua.smcvt.edu/linearalgebra/)などのオンライン参照をクリックします。

次元 (またはサイズ $n) の列ベクター (または単に[*ベクター*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v $ は、 $ $ 列として配置される $n 複素数 $ (v_1、v_2、\ lドット、v_n) $ のコレクションです。

$ $v = \ begin{bmatrix}
v_1\\\\
v_2\\\\
\ vドット\\\\
v_n & end{bmatrix}$$

ベクター $v の基準は、 $ $-sqrt { \ sum \_ i | v \_ i | ^ 2 $ として定義されてい } ます。 ベクターは、標準が $1 の場合には単位基準 (または[*単位ベクトル*](https://en.wikipedia.org/wiki/Unit_vector)と呼ばれます) と呼ばれ $ ます。 [*ベクター $v の adjoint*](https://en.wikipedia.org/wiki/Adjoint_matrix)は、 $ $v ^ に示され、 $ 次の行ベクトルとして定義されています。 $ \* $ は複雑な共役を表します。

$ $ \ begin{ bmatrix } v_1 \\ \\ \ vドット \\ \\ v_n \ end{ bmatrix } ^ \ ダガー = \ begin{ bmatrix } v_1 ^ * &/cドット & v_n ^ * & end{bmatrix}$$

2つのベクトルを乗算する最も一般的な方法は、[*内部製品*](https://en.wikipedia.org/wiki/Inner_product_space)(ドット積とも呼ばれます) を使用することです。  内側の製品は、あるベクターの射影を別のベクターに提供し、1つのベクターを他のより単純なベクターの合計として表現する方法を説明するうえで非常に重要です。  $U と $v 間の内部積。ここで $ $ は $ left \langle u, v \right \rangle $ はとして定義されています。

$ $ \ langle u, v \rangle = u ^ \ ダガー v = u \_ 1 ^ { \* } v_1 + \ cドット + u \_ n ^ { \* } v \_ n
$$

この表記法を使用すると、ベクターの $v $ を $-sqrt { \ langle v, v $ として記述することもでき \rangle } ます。

ベクターと数値 $c を乗算して、 $ $c によってエントリに乗算される新しいベクターを形成でき $ ます。 また、2つのベクター $u $ を追加 $v して、 $ $u と $v のエントリを加算したエントリを持つ新しいベクターを作成することもでき $ $ ます。 これらの操作を次に示します。

$ $ \mathrm{If } ~ u = \ begin{bmatrix}
u_1\\\\
u_2\\\\
\ vドット\\\\
u_n \ end{ bmatrix } ~ \mathrm{and } ~ v = \ begin{bmatrix}
    v_1\\\\
    v_2\\\\
    \ vドット\\\\
    v_n \ end{ bmatrix } , ~ \mathrm{then } ~ au + bv = \ begin{bmatrix}
au_1 + bv_1\\\\
au_2 + bv_2\\\\
\ vドット\\\\
au_n + bv_n \ end{ bmatrix } .
$$

次[*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics))のように $ $m の $ $ 行と $n の列に配置された $mn 複素数のコレクションは、サイズ $m/倍 n です $ 。

$ $M = \ begin{bmatrix}
M_ {11 } ~ ~ M_ {12 } ~ ~ \ ドット ~ ~ M_ {1n } \\ \\ M_ {21 } ~ ~ M_ {22 } ~ ~ \ ドット ~ ~ M_ {2n } \\ \\\\\\
M_ {m1 } ~ ~ M_ {m2 } ~ ~-cドット ~ ~ M_ { } \\ \\ bmatrix } . $ $

Dimension $n のベクター $ は、単に size $n の1倍の行列であることに注意して $ ください。 ベクターの場合と同様に、マトリックスと数値 $c を乗算して、 $ すべてのエントリが $c と乗算される新しい行列を取得できます $ 。また、同じサイズの2つのマトリックスを追加して、2つの行列の各エントリの合計を入力する新しい行列を生成することもできます。 

## <a name="matrix-multiplication-and-tensor-products"></a>マトリックス乗算とその他の製品

また、次のように、次元の2つの行列 $M $ $m \times n $ と $n 次元の $N を乗算することによって、ディメンションの $P の $ $ 新しいマトリックス $m を取得することもでき $ $ ます。

& i)}
& \ begin{bmatrix}
    M_ {11 } ~ ~ M_ {12 } ~ ~ \ ドット ~ ~ M_ {1n } \\ \\ M_ {21 } ~ ~ M_ {22 } ~ ~ \ ドット ~ ~ M_ {2n } \\ \\\\\\
    M_ {m1 } ~ ~ M_ {m2 } ~ ~-cドット ~ ~ M_ {になります}
エンドbmatrix}
初めbmatrix}
N_ {11 } ~ ~ N_ {12 } ~ ~ \ ドット ~ ~ N_ {1p } \\ \\ N_ {21 } ~ ~ N_ {22 } ~ ~/cドット ~ ~ N_ {2p } \\ \\\\\\
N_ {n1 } ~ ~ N_ {n2 } ~ ~ \ N_ {np}
\ end{ bmatrix } = \ begin{bmatrix}
P_ {11 } ~ ~ P_ {12 } ~ ~ \ ドット ~ ~ P_ {1p } \\ \\ P_ {21 } ~ ~ P_ {22 } ~ ~/cドット ~ ~ P_ {2p } \\ \\\\\\
P_ {m1 ~ } ~ P_ {m2 } ~ ~ \ P_ {mp}
エンドbmatrix}
& end{align}

$P のエントリ $ は $P _ {ik } = \ sum_j M_ {ij} N_ {jk } $ です。 たとえば $P _ {11 $ というエントリは、 } $ $N の最初の列を $M の最初の行の内部積です $ 。 ベクターは単にマトリックスの特殊なケースであるため、この定義はマトリックスベクトル乗算まで拡張されることに注意してください。 

考慮するすべてのマトリックスは、行と列の数が等しいか、またはベクトルであり、$1 列にのみ対応する正方形のマトリックス $ です。 1つの特殊な正方形の行列は、 [*id 行列*](https://en.wikipedia.org/wiki/Identity_matrix)です $ 。これは、すべての対角線の要素が $1 と等しく、残りの要素が $0 であることを $ 示してい $ ます。

$ $ > bold 完了 = \ begin{bmatrix}
1 ~ ~ 0 ~ ~ \ 300 ドット ~ 0\\\\
0 ~ ~ 1 ~ ~ \ 300 ドット ~ 0\\\\
~ ~ \ dドット\\\\
0 ~ ~ 0 ~ ~ (cドット) ~ ~ 1 & end{ bmatrix } . $ $

$A の正方形行列の $ $ 場合、$AB = BA =/$B が行われた場合、行列は[*逆*](https://en.wikipedia.org/wiki/Invertible_matrix)に $ なります。 マトリックスの逆も存在している必要はありませんが、存在する場合は一意であり、^ {-1 $ $A ことを意味し } ます。 

マトリックス $M の場合 $ 、$M の adjoint または共役転置はマトリックス $N であり、 $ $ $N _ {ij } = M_ {ji } ^ \* $ です。 $M の adjoint $ は、通常、$M ^ \ ダガーに示され $ ます。 ここでは、" $ ^ [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) & $UU = u ^ \ ダガー u = \" $ を $U ^ {-1 } = u ^ \ ダガーと同等であるかどうかに関係ない場合は、"$U" という行列が付いてい $ ます。  たとえば、最も重要なのは、ベクトルの基準を維持することです。  これは、 

$ $ \ langle v, v \rangle = v ^-ダガー v = v ^ \ ダガー U ^ {-1 } u v = v ^-ダガー u ^ \ ダガー u v = \ langle u v, U v \rangle . $ $  

マトリックスの $M $ は、$M = M ^ [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix)の場合は、"" と呼ばれ $ ます。

最後に、2つの $M マトリックスの[*Kronecker (また*](https://en.wikipedia.org/wiki/Tensor_product)は nq product) のサイズが $ $m \times n で、サイズが $N の $p のサイズが大きい場合、 $ $ q はより大きなマトリックスとして $P $mp $ \otimes $ $ から取得され、次の $M から取得され $ $ ます。

& i)}
    M/otimes N &= \ begin{bmatrix}
        M_ {11 } ~ ~ \ cドット ~ ~ M_ {1n } \\ \\ \ dドット\\\\
        M_ {m1 } ~ ~ \ cドット ~ ~ M_ {になります}
    エンドbmatrix}
    \ otimes \ begin{bmatrix}
        N_ {11 } ~ ~ \ cドット ~ ~ N_ {1q } \\ \\ \ dドット\\\\
        N_ {p1 } ~ ~ \ cドット ~ ~ N_ {pq}
    \ end{ bmatrix } \\ \\ &= \ begin{bmatrix}
        M_ {11 } \ begin{ bmatrix } N_ {11 } ~ ~-cドット ~ ~ N_ {1q } \\ \\ \ dドット \\\\ N_ {p1 } ~ ~-cドット ~ ~ N_ {pq } \ end{~ bmatrix } ~-cドット ~ ~ M_ {1q } \ begin{ bmatrix } N_ {11 } ~ ~ \ cドット ~ ~ N_ {1q/ } \\ \\ dドット \\\\ N_ {p1 } ~ ~-cドット ~ ~ N_ {pq } \ end{/ bmatrix } \\ \\ dドット\\\\
        M_ {m1 } \ begin{ bmatrix } N_ {11 } ~ ~-cドット ~ ~ N_ {1q } \\ \\ \ dドット \\\\ N_ {p1 } ~ ~-cドット ~ ~ N_ {pq } \ end{ bmatrix } ~ ~-cドット ~ ~ M_ { } bmatrix } N_ {11 } ~ ~-cドット ~ ~ N_ {1q } \\ \\ \ dドット \\\\ N_ {p1 } ~ ~-cドット ~ ~ N_ {pq } \ end{bmatrix}
    \ end{ bmatrix } .
& end{align}

次に例をいくつか示します。

$ $ \ begin{bmatrix}
        a \\ \\ b & # {/ bmatrix } otimes & begin{ bmatrix } c \\ \\ d \\ \\ e \ end{ bmatrix } = \ begin{bmatrix}
        a & begin{ bmatrix } c \\ \\ d \\ \\ e \ end{bmatrix}
        \\\\[1.5 em] b & begin{ bmatrix } c \\ \\ d \\ \\ e\end{bmatrix}
    エンドbmatrix}
    = \ begin{ bmatrix } a c \\ \\ a d \\ \\ a e \\ \\ b c \\ \\ b d \\ \\ be\end{bmatrix}
$$

および

$ $ \ begin{bmatrix}
        a \ b \\ \\ c \ d \ end{bmatrix}
    \ otimes \ begin{bmatrix}
        e \ f \\ \\ g \ h \ end{bmatrix}
     = \ begin{bmatrix}
    ある\begin{bmatrix}
    e \ f \\\\ g \ h \ end{bmatrix}
    b\begin{bmatrix}
    e \ f \\\\ g \ h \ end{bmatrix}
    \\\\[1em] c\begin{bmatrix}
    e \ f \\\\ g \ h \ end{bmatrix}
    a\begin{bmatrix}
    e \ f \\\\ g \ h \ end{bmatrix}
    エンドbmatrix}
    = \ begin{bmatrix}
    ae \ af \、\\ bf \\ \\ ag \ ah \ bg \ bh \\ \\ ce \ cf \ \\ \\ bmatrix (&)、df cg } \、& lt; グループ名 \。
$$

数値表記と製品を囲む最後の便利な方法として、ベクター $v $ またはマトリックス $M については、 $ $v ^ {/otimes n $ } または $M ^ {/otimes n } $ は、$n $ フォールドで繰り返されていたすべての製品に対して短縮されます。  次に例を示します。

& i)}
& \ begin{ bmatrix } 1 \\ \\ 0 \ end{ bmatrix } ^ {\ otimes 1 } = \ begin{ bmatrix } 1 \\ \\ 0 \ end{ bmatrix } , \qquad \begin{bmatrix} 1 \\ \\ 0 \ end{ bmatrix } ^ {/otimes 2 } = \ begin{ bmatrix } 1 0 0; \\ \\ \\ \\ \\ \\ \ end{ bmatrix } , \qquad \begin{bmatrix} 1 \\ \\ -1 & end{ bmatrix } } bmatrix } 1 \\ \\ -1- \\ \\ 1-1 \\ \\ 1 & end{ bmatrix } , \\ \\ & \ begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 & end{ bmatrix } ^ {/otimes 1 } = \ begin{ bmatrix } 0 1 1 0 & \\ \\ & \ end{ bmatrix } , \qquad \begin{bmatrix} 0 & 1 \\ \\ 1 & 0/end{ bmatrix } ^ {/otimes 2 } = \ begin{ bmatrix } 0 &0 \\ \\ \\ \\ \\\\ \end{bmatrix}&0&1 0 &0&1&0 0 &0&0 になります。
& end{align}
