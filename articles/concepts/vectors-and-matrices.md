---
title: クォンタムコンピューティングのベクトルとマトリックス
description: ベクターとマトリックスを操作する方法の基本について説明します。
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 076ab6242b7ae31d4936ae8505034f1f13fa4727
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904912"
---
# <a name="vectors-and-matrices"></a>ベクターと行列

ベクターとマトリックスについては、クォンタムコンピューティングを理解するために重要な知識があります。 次の簡単な概要を説明します。また、読者には、 *Strang、G. (1993) などの線形代数の標準参照を読むことをお勧めします。線形代数 (Vol. 3) の概要。Wellesley、MA: Wellesley を押す*か、[線形代数](http://joshua.smcvt.edu/linearalgebra/)などのオンライン参照をクリックします。

列ベクター (または単に[*ベクター*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v $ of dimension (または size) $n $ は、列として配置された $n $ 複素数 $ (v_1、v_2、\ lドット、v_n) $ のコレクションです。

$ $v = \begin{bmatrix} v_1\\\\ v_2\\\\ \ vドット\\\\ v_n \end{bmatrix} $ $

Vector $v $ の基準は、$ \ sqrt{-sum\_i | v\_i | ^ 2} $ として定義されています。 ベクターは、標準が $1 $ の場合は単位基準 (または[*単位ベクトル*](https://en.wikipedia.org/wiki/Unit_vector)と呼ばれます) と呼ばれます。 ベクター $v $[*の adjoint*](https://en.wikipedia.org/wiki/Adjoint_matrix)は $v ^ \ ダガー $ として、次の行ベクトルとして定義されています。 $\*$ は複雑な共役を表します。

$ $ \begin{bmatrix} v_1 \\\\ \ vドット \\\\ v_n \end{bmatrix} ^ \ ダガー = \begin{bmatrix} v_1 ^ * &/cドット & v_n ^ * \end{bmatrix} $ $

2つのベクトルを乗算する最も一般的な方法は、[*内部製品*](https://en.wikipedia.org/wiki/Inner_product_space)(ドット積とも呼ばれます) を使用することです。  内側の製品は、あるベクターの射影を別のベクターに提供し、1つのベクターを他のより単純なベクターの合計として表現する方法を説明するうえで非常に重要です。  $U $ と $v $ の間の内部積 ($ v\right\rangle) が示されています。

$ $ \ langle u, v\rangle = u ^ \ ダガー v = u\_1 ^ {\*} v_1 + \ cドット + u\_n ^ {\*} v\_n
$$

この表記法を使用すると、vector $v $ の基準を $ \ sqrt{, v\rangle} $ として記述することもできます。

ベクターと数値 $c $ を乗算して、$c $ を乗算したエントリを持つ新しいベクターを形成できます。 また、$ および $v $ $u 2 つのベクトルを追加して、$u $ と $v $ のエントリの合計を持つ新しいベクトルを作成することもできます。 これらの操作を次に示します。

$ $ \mathrm{If} ~ u = \begin{bmatrix} u_1\\\\ u_2\\\\ \ vドット\\\\ u_n \end{bmatrix} ~ \mathrm{and} ~ v = \begin{bmatrix} v_1\\\\ v_2\\\\ \ vドット\\\\ v_n \end{bmatrix}、~ \mathrm{then} ~ au + bv = \begin{bmatrix} au_1 + bv_1\\\\ au_2 + bv_2\\\\ \ vドット\\\\ au_n + bv_n \end{bmatrix}.
$$

次に示すように、サイズが $m-n $ の[*行列*](https://en.wikipedia.org/wiki/Matrix_(mathematics))は $m $ rows と $n $ の列に配置された $mn $ 複素数のコレクションです。

$ $M = \begin{bmatrix} M_{11} ~ ~ M_{12} ~ ~-cドット ~ ~ M_ {1n}\\\\ M_{21} ~ ~ M_{22} ~ ~-cドット M_\\\\ {m1} ~ ~\\{m2} ~ ~-cドット ~ ~ \\ {\end{bmatrix}.} M_ M_ $ $ です。\\\\

Dimension $n $ のベクトルは、単に $1 $n のサイズのマトリックスであることに注意してください。 ベクターの場合と同様に、$c $ という数値でマトリックスを乗算して、すべてのエントリが $c $ と乗算された新しい行列を取得できます。また、同じサイズの2つのマトリックスを追加して、2つの行列の各エントリの合計であるエントリを持つ新しいマトリックスを生成することもできます。 

## <a name="matrix-multiplication-and-tensor-products"></a>マトリックス乗算とその他の製品

また、次のように、2つの $M 行列を乗算して、$ of dimension $m/times n $ と $N $ of dimension $n/times p $ を乗算して、$ of dimension $P/times p $ の新しいマトリックスを取得することもできます。

\begin{align} & \begin{bmatrix} M_{11} ~ ~ M_{12} ~ ~ \ cドット ~ ~ M_ {1n}\\\\ M_{21} ~ ~ M_{22} ~ ~ \ ドット M_\\\\ {m1} ~ ~\\{m2} ~ ~-cドット ~ ~ \\ {2n} \end{bmatrix} \begin{bmatrix} を M_ します。 N_{11} ~ ~ N_{12} ~ ~ \ ドット ~ ~ N_ {1p}\\\\ N_{21} ~ ~ N_{22} ~ ~-cドット ~ ~ N_ {2p}\\\\ \begin{bmatrix}\\\\ N_ {n1} ~ ~ N_ {n2} ~ ~ \ cドット ~ ~ N_ {np} \end{bmatrix} = P_{11} ~ ~ P_{12} ~ ~-cドット ~ ~ P_ {1p}\\\\ P_{21} ~ ~ P_{22} ~ ~ \ cドット ~ ~ P_ {2p}\\\\\\{m2} ~ ~/cドット ~ ~ \\ {mp} \end{bmatrix} \end{align} を P_ します。

ここで $P $ のエントリは $P _ {ik} = \ sum_j M_ {ij} N_ {jk} $ です。 たとえば $P _{11}$ というエントリは $M $ の最初の行の内部積であり、$N $ の最初の列になります。 ベクターは単にマトリックスの特殊なケースであるため、この定義はマトリックスベクトル乗算まで拡張されることに注意してください。 

考慮するすべてのマトリックスは、行と列の数が等しいか、または $1 $ 列にのみ対応するベクトルです。 1つの特殊な正方形の行列は、$-bold done $ という[*形式で表さ*](https://en.wikipedia.org/wiki/Identity_matrix)れ、すべての対角線の要素は $1 $、残りの要素は $0 $ と等しくなります。

$ $ \ \end{bmatrix}. done = \begin{bmatrix} 1 ~ ~ 0 ~ ~ \ cドット ~ ~ 0\\\\ 0 ~ ~ 1 ~ 0\\\\ ~ ~-d ドット\\\\ 0 ~ ~ 0 ~ ~ \ ~ ~ 1 $ $ です。

"$" を $A している場合は、"$" が $AB = BA = \ $B $ の場合はその[*逆*](https://en.wikipedia.org/wiki/Invertible_matrix)になります。 マトリックスの逆も存在している必要はありませんが、存在する場合は一意であり、^{-1}$ $A ことを意味します。 

$ $M $ の場合、$M $ の adjoint または共役転置は $N _ {ij} = M_ {ji} ^\*$ というマトリックス $N $ です。 $M $ の adjoint は通常、$M ^ \ ダガー $ と示されます。 マトリックス $U、$ が $UU の場合は、$ が[*ユニタリ*](https://en.wikipedia.org/wiki/Unitary_matrix)であることを示しています。これは、$-ダガー = u ^-ダガー U =-bold 操作 $ または同等の $U ^{-1} = U ^ \ ダガー $ です。  たとえば、最も重要なのは、ベクトルの基準を維持することです。  これは、 

$ $ \ langle v, v \rangle = v ^ \ ダガー v = v ^ \ ダガー U ^{-1} U v = v ^-ダガー U ^-ダガー U v = \ langle U v, U v/rangle$ $  

$ $M $ は、$M = M ^ \ ダガー $ の場合は[*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix)と呼ばれます。

最後に、2つの $M マトリックスの Kronecker (または nq [*product) は*](https://en.wikipedia.org/wiki/Tensor_product)、$ of size $m/times n $ と $N $ of size $p/times q $ が大きなマトリックスであることを示しています。これは、次のように $P $ と $mp $ から取得されます。

\begin{align} M/otimes N & = \begin{bmatrix} M_{11} ~ ~ \ cドット ~ ~ M_ {1n} \\\\ \begin{bmatrix}\\\\ M_ {m1} ~ ~-cドット ~ ~ M_ {} \end{bmatrix}/otimes N_{11} ~ ~/cドット ~ ~ N_ {1n}\\\\ dドット\\\\ N_ {p1} ~ ~ \ N_ {pq} \end{bmatrix}\\\\ & = \begin{bmatrix} M_{11} \begin{bmatrix} N_{11} ~ ~-cドット ~ ~ N_ {1n}\\\\ \end{bmatrix}。 ~ ~ |\\\\ N_ {p1} ~ ~ \ cドット ~ ~ N_ {pq}~ ~/cドット ~ ~ M_ {1n} \begin{bmatrix} N_{11} ~ ~ \ cドット ~ ~ N_ {1n}\\\\ \begin{bmatrix}\\\\ N_ {p1} ~ ~-cドット ~ ~ N_ {pq} \end{bmatrix}\\\\\\\\ ~ ~/cドット ~ ~ M_ {1n} です。\\\\ \ dドット\\\\ N_ {p1} ~ ~ \ cドット ~ ~ N_ {pq} \end{bmatrix} ~ ~-cドット ~ ~ M_ {} \begin{bmatrix} N_{11} ~ ~/cドット ~ ~ N_ {1n}\\\\\\\\ N_ N_ {p1} ~ ~-cドット ~ ~ {pq} & end{bmatrix} \end{bmatrix}.{11}
\end{align}

次に例をいくつか示します。

$ $ \begin{bmatrix} a \\\\ b \end{bmatrix}/otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} = \begin{bmatrix} a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} \\\\[1.5 em] b \begin{bmatrix} c \\\\ d \\\\ e\ end {bmatrix} \end{bmatrix} = \begin{bmatrix} a c \\\\ a d \\\\ e \\\\ bc \\\\ b d \\\\ be {bmatrix} $ $

and

$ $ \begin{bmatrix} a \ b \\\\ c \ d \end{bmatrix} \ otimes \begin{bmatrix} e \ f\\\\g \ h \end{bmatrix} = \begin{bmatrix} a-begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} bmatrix begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} \\\\[1em] c\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} d\ 開始 {bmatrix} e \ f\\\\ g \ h \end{bmatrix} \end{bmatrix} = \begin{bmatrix} ae \ af \ bf \\t_15_ ag \ ah \ bg \ bh \\\\ ce \ cf \ de \ df \\\\ cg \ ch \ dg \ dh \end{bmatrix}.\\
$$

数値表記と製品を囲む最後の便利な方法とし $v て、$ または matrix $M $、$v ^ {\ otimes n} $、または $M ^ {/otimes n} $ は、$ フォールドの連続し $n た空のに対して短縮されます。  例 :

\begin{align} & \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ {\ otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}、\qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ {\begin{bmatrix} times 2} = 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}、\qquad\begin{bmatrix} 1 \\\\-1 \end{bmatrix} ^ {\ otimes 2} = \begin{bmatrix} 1 \\\\-1 \\\\-1 \\\\1 & end{bmatrix}、\\\\ & \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ {/otimes 1} = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix}、\qquad\begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ {/otimes 2} = \begin{bmatrix} 0 & 0 & 0 & 1 \\0 \\ & 0 & 1 & 0 \\0 \\ & 1 & 0 & 0\\0 \ 終了 {です \\。bmatrix}。
\end{align}
