---
title: 量子オラクル
description: 別のアルゴリズムへの入力として使用される、クォンタム oracles、ブラックボックス操作の操作方法と定義方法について説明します。
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
ms.openlocfilehash: 1d1d0b0903db8e994166c3e8a5798f70742a1c7e
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904929"
---
# <a name="quantum-oracles"></a>Quantum Oracles

Oracle $O $ は、別のアルゴリズムへの入力として使用される "ブラックボックス" 操作です。
多くの場合、このような操作は従来の関数 $f を使用して定義されています: \\{0, 1\\} ^ n \ \\{0, 1\\} ^ m $ に $n $ bit バイナリ入力を取得し、$m $ bit バイナリ出力を生成します。
これを行うには、特定のバイナリ入力 $x = (x_{0}、x_{1}、\ ドット、x_ {n-1}) $ を考慮してください。
Qubit 状態には、$ \ket{\vec{x}} = \ket{x_{0}}/otimes \ket{x_{1}}/otimes/cドット/otimes \ket{x_ {n-1}} $ というラベルを付けることができます。

最初に $O $ を定義しようとします。これにより、$O \ket{x} = \ket{f (x)} $ になりますが、これにはいくつかの問題があります。
まず、$ $f には、入力と出力のサイズが異なる場合があります ($n \n e m $)。 $O $ を適用すると、レジスタの qubits の数が変更されます。
2番目に、$n = m $ の場合でも、関数は反転できるではない可能性があります。たとえば、一部の $x \n e y $ の $f (x) = f (y) $ の場合、$O \ket{x} = O\ket {y} $、$O ^ \ ダガー O\ket {x} \n e O ^、ダガー O\ket {y} $。
つまり、adjoint 操作 $O ^ oracles $ に作成することはできず、そのためには adjoint が定義されている必要があります。

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>計算ベースの状態に影響を与える oracle の定義
回答を保持する $m $ qubits の2番目のレジスタを導入することで、両方の問題に対処できます。
次に、すべての計算ベースの状態に対して、oracle の効果を定義します。すべての $x \ \\{0, 1\\} ^ n $ と $y \ \\{0, 1\\} ^ m $,

$ $ \begin{align} O (\ket{x}/otimes \ket{y}) = \ket{x} \ otimes \ket{y \ oplus f (x)}。
\end{align} $ $

ここで $O = O ^ \ ダガー $ を構築によってしました。したがって、上記の問題の両方を解決しました。

> [!TIP]
> $O = O ^ {-dagger} $ であることを確認するには、$O ^ 2 = \ $a の後に $ {+ b を加え、b = a $ a all $a (b) \{0, 1\}$ であることに注意してください。
> 結果として、$O \ket{x} \ket{y と f (x)} = \ket{x} \ket{y と f (x) \ oplus f (x)} = \ket{x} \ket{y} $ のようになります。

重要な点として、各計算基準の状態に対して oracle を定義すると、$ \ket{x}\ket{y} $ は、他のすべての状態に対して $ act $O 方法も定義します。
これは、すべてのクォンタム操作と同様、$ $O 処理される状態で線形であるという事実からすぐに続きます。
Hadamard 操作を考えてみます。たとえば、$H \ket{0} = \ket{+} $ および $H \ket{1} = \ket{-}$ によって定義されているとします。
$ \Ket{+} $ に対して $ act を $H 方法を知りたい場合は、$ is linear $H を使用できます。

$ $ \begin{align} H\ket {+} & = \ frac{1}{\ sqrt{2}} H (\ket{0} + \ket{1}) = \ frac{1}{\ sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \ frac{1}{\ sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0}-\ket{1}) = \ket{0}です。
\end{align} $ $

Oracle $O $ を定義する場合は、次のように、任意の状態 $ \ket{\psi} $ on $n + m $ qubits を使用することもできます。

$ $ \begin{align} \ket{\psi} & = \ sum_ {x \ \\{0, 1\\} ^ n, y \ \\{0, 1\\} ^ m} \ alpha (x, y) \ket{x} \ket{y} \end{align} $ $

$-alpha: \\{0, 1\\} ^ n 回 \\{0, 1\\} ^ m-to \mathbb{C} $ は、状態 $ \ket{\psi} $ の係数を表します。 したがって

$ $ \begin{align} O \ket{\psi} & = O \ sum_ {x \ \\{0, 1\\} ^ n, y \ \\{0, 1\\} ^ m} \ アルファ (x, y) \ket{x} \ket{y} \\\\ & = \ sum_ {x \ \\{0, 1\\} ^ n, y \ \\{0, 1\\} ^ m} \ alpha (x, y) O \ket{x} \ket{y} \\\\ & = \ sum_ {x \ \\{0, 1\\} ^ n, y \ \\{0, 1\\} ^ m} \ alpha (x, y) \ket{x} \ket{y/oplus f (x)}。
\end{align} $ $

## <a name="phase-oracles"></a>フェーズ oracles
または、$O $ への入力に基づいて_フェーズ_を適用して、$f $ を oracle $O $ にエンコードすることもできます。
たとえば、$ $ \begin{align} O \ket{x} = (-1) ^ {f (x)} \ket{x}. という $O $ を定義する場合があります。
\end{align} $ $ 計算ベースの状態が "$ \ket{x} $" である場合、このフェーズはグローバルフェーズであるため、監視できません。
ただし、このような oracle は、法則または制御された操作として適用される場合、非常に強力なリソースになります。
たとえば、$ という1つの単一の qubit $f 関数に対して _f $ $O フェーズ orcale を考えてみます。
次に、$ $ \begin{align} O_f \ket{+} & = O_f (\ket{0} + \ket{1})/\ sqrt{2} \\\\ & = ((-1) ^ {f (0)} \ket{0} + (-1) ^ {f (1)} \ket{1})//sqrt{2} \\\\ & = (-1) ^ {f (0)} (\ket{0} + (-1) ^ {f (1)-f (0)} \ket{1})/\ sqrt{2} \\\\ & = (-1) ^ {f (0)} Z ^ {f (0)-f (1)} \ket{+}。
\end{align} $ $

一般的には、oracles の両方のビューを拡大して、1ビットだけではなく実数を返す古典関数を表すことができます。

Oracle を実装する最適な方法を選択することは、特定のアルゴリズム内でこの oracle がどのように使用されるかに大きく依存します。
たとえば、 [Deutsch アルゴリズム](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm)は最初の方法で実装された oracle に依存しますが、 [Grover のアルゴリズム](https://en.wikipedia.org/wiki/Grover's_algorithm)は2番目の方法で実装された oracle に依存しています。


詳細については、 [Gilyén *et*1711.00465](https://arxiv.org/abs/1711.00465)に関する説明をお勧めします。
