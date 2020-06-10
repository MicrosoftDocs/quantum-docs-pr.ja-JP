---
title: 量子オラクル
description: 別のアルゴリズムへの入力として使用される、クォンタム oracles、ブラックボックス操作の操作方法と定義方法について説明します。
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
no-loc:
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
ms.openlocfilehash: 31e43940fc0607b15ccefcfae6be7122227b3d64
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630315"
---
# <a name="quantum-oracles"></a>Quantum Oracles

Oracle $O $ は、別のアルゴリズムへの入力として使用される "ブラックボックス" 操作です。
多くの場合、このような操作は従来の関数 $f を使用して定義されます。 \\ {0, 1 \\ } ^ n \ \\ {0, 1 \\ } ^ m は、 $ $n $ ビットのバイナリ入力を受け取り、$m ビットのバイナリ出力を生成し $ ます。
これを行うには、$x = (x_ {0 } , x_ {1 } , \ ドット, x_ {n-1) $ という特定のバイナリ入力を考えてみ } ます。
Qubit 状態には、$ \ket { \ vec{x } } = \ket{x_ {0 } } \ otimes \ket{x_ {1}/otimes } /cドット/otimes \ket{x_ {n-1 } } $ というラベルを付けることができます。

最初に、 $ $O \ket {x = \ket{f (x)} $ に $O を定義しようとしましたが、これには } いくつかの問題があります。
最初に、$f $ の入力と出力のサイズが異なる場合があります ($n \n e m)。これにより $ $O を適用すると $ レジスタの qubits の数が変更されます。
2番目に、$n = m の場合でも、関数が反転できるになら $ ない可能性があります。たとえば、一部の $x \n e y に対して $f (x) = f (y) $ を指定する $ と、$O \ket {x } = O \ket {y } $ は $O ^-ダガー o { \ket x } \n e o ^ & ダガー o \ket {y } $ です。
つまり、oracles に adjoint $O 操作を作成できなくなり $ 、に adjoint が定義されている必要があります。

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>計算ベースの状態に影響を与える oracle の定義
回答を保持する $m qubits の2番目のレジスタを導入することで、両方の問題に対処でき $ ます。
次に、すべての計算ベースの状態に対して、oracle の効果を定義します。すべての $x \ \\ {0, 1 \\ } ^ n $ と $y \ \\ {0, 1 \\ } ^ m $ で実行します。

$ $ & begin{align}
    O (\ket{x/ } otimes \ket{y } ) = \ket{x } 、otimes \ket{y、oplus f (x)}。
& end{align}
$$

ここでは、$O = O ^ \ $ を構築しています。したがって、以前の問題の両方を解決しました。

> [!TIP]
> $O = O ^ {\ ダガー $ であることを確認するには、 } $O ^ 2 = \ $ $a の後に、 $ すべての $a の b = a ( \{ 0, 1 $) を使用し \} ます。
> 結果として、$O \ket{x } \ket{y と f (x)} = \ket{x \ket{y と f ( } x) \ oplus f (x)} = \ket{x \ket{y $ のようになり } } ます。

重要な点として、各計算基準の状態に対して oracle を定義すると、$ \ket{x } \ket{y } $ は $ 他の状態に対してどのように動作 $O するかも定義します。
これ $ は、すべてのクォンタム操作と同様に、処理が実行されている状態で線形である $O という事実からすぐに続きます。
たとえば、$H \ket{0 } = \ket { +} $ および $H \ket{1 } = \ket-} $ によって定義されている Hadamard 操作を考えてみ { ます。
$H が $ \ket +} $ でどのように動作するかを知りたい場合は、 $ { 線形の $H を使用できます。 $

$ $ & begin{align}
H \ket { +} & = \frac{1 } {\ sqrt{2 } } H (\ket{0 } + \ket{1 } ) = \frac{1 } {\ sqrt{2 } } (h \ket {0 } + H \ket {1 } ) \\ \\ & = \frac{1 } {\ sqrt{2 } } (\ket { +} + \ket { -}) = \frac12 (\ket{0 + \ket{1 + \ket{0 } } } } ) = \ket{1 } 。
& end{align}
$$

Oracle $O を定義する場合は、次のように、 $ 任意の状態 $ \ket { \ psi } $ on $n + m $ qubits を書き込むこともできます。

$ $ & begin{align}
\ket { \ psi } & = \ sum_ {x \ in {0, \\ 1 \\ } ^ n, y \ in \\ {0, 1 \\ } ^ m- } alpha (x, y) } \ket{y}
& end{align}
$$

ここで、$-alpha: \\ {0, 1 \\ } ^ n \\ /times {0, 1} ^ \\ \mathbb{C } $ は、状態 $ \ket \ psi $ の係数を表し { } ます。 したがって

$ $ & begin{align}
O \ket { \ psi } & = O \ sum_ {x \ in \\ {0, 1 \\ } ^ n, y \ \\ {0, 1 \\ } ^ m } \ alpha (x, y) \ket{x } \ket{y } \\ \\ & = \ sum_ {x \ \\ {0, 1 \\ } ^ n、y \ \\ {0, 1 \\ } ^ m- } alpha (x, y) O \ket{x } \ket{y } \\ \\ & = \ sum_ {x \ in {0, 1} \\ \\ ^ n, y \ in {0, 1} ^ \\ m/ \\ } alpha (x, y) \ket{x } \ket{y/oplus f (x)}。
& end{align}
$$

## <a name="phase-oracles"></a>フェーズ oracles
または、 $ $ $O への入力に基づいて_フェーズ_を適用して、$f を oracle $O にエンコードすることもでき $ ます。
たとえば、$ $ & $O 定義します。 $}
    O \ket{x } = (-1) ^ {f (x)} \ket{x } .
& end{align}
$ $ 計算された oracle が、最初にコンピューティングベースの状態 $ \ket{x $ で登録に対して動作する場合 } 、このフェーズはグローバルフェーズであるため、監視できません。
ただし、このような oracle は、法則または制御された操作として適用される場合、非常に強力なリソースになります。
たとえば、 $ 1 つの-qubit 関数 $f に対して、フェーズ orcale $O _f を考えてみ $ ます。
次に、$ $ > begin{align}
    O_f \ket { +} & = O_f (\ket{0 } + \ket{1 } )/\ sqrt{2 } \\ \\ & = ((-1) ^ {f (0)} \ket{0 } + (-1) ^ {f (1)} \ket{1 } )/\ sqrt{2 } \\ \\ & = (-1) ^ {f (0)} (\ket{0 } + (-1) ^ {f (1)-f (0)} \ket{1 } )/\ sqrt{2 } \\ \\ & = (-1) ^ {f (0)} Z ^ {f (0)-f (1)} \ket { +}。
& end{align}
$$

一般的には、oracles の両方のビューを拡大して、1ビットだけではなく実数を返す古典関数を表すことができます。

Oracle を実装する最適な方法を選択することは、特定のアルゴリズム内でこの oracle がどのように使用されるかに大きく依存します。
たとえば、 [Deutsch アルゴリズム](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm)は最初の方法で実装された oracle に依存しますが、 [Grover のアルゴリズム](https://en.wikipedia.org/wiki/Grover's_algorithm)は2番目の方法で実装された oracle に依存しています。


詳細については、 [Gilyén *et*1711.00465](https://arxiv.org/abs/1711.00465)に関する説明をお勧めします。
