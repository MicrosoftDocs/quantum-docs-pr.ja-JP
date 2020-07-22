---
title: クォンタム oracles の説明: 別のアルゴリズムへの入力として使用される、クォンタム oracles、ブラックボックス操作の操作方法と定義方法について説明します。
執筆者: cgranade uid: oracles: Christopher.Granade@microsoft.com ms. date: 07/11/2018 ms. topic: article no loc (次の説明を参照):
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
# <a name="quantum-oracles"></a>Quantum Oracles

Oracle $ O $ は、別のアルゴリズムへの入力として使用される "ブラックボックス" 操作です。
多くの場合、このような操作は従来の関数 $ f: \\ { 0、1 ^ n 0、1 ^ m を使用して定義されます \\ } \to \\ { \\ } $ 。これは $ n $ ビットのバイナリ入力を受け取り、 $ m ビットのバイナリ出力を生成し $ ます。
これを行うには、特定のバイナリ入力 $ x = (x_ { 0 } 、x_ { 1 } 、\ ドット、x_ { n-1) } $ を考慮してください。
Qubit 状態には $ \ket { \vec { } } = \ket { 、x x_ { 0 } } \otimes \ket { x_ { 1 x_ } } \otimes \cdots \otimes \ket { { n-1 } } $ というラベルを付けることができます。

最初に o x f (x) を定義しようとし $ $ てい $ \ket { } = \ket { } $ ますが、これにはいくつかの問題があります。
まず、 $ f の $ 場合、入力と出力のサイズが異なり $ ます (n \ne m $ )。 O を適用すると $ レジスタの $ qubits の数が変わることがあります。
2つ目は、n m の場合でも、関数が反転できるになら $ = $ ない可能性があります。 $ f (x) = f (y) がある $ $ x y の場合 \ne $ 、 $ o \ket { x } = o \ket { y で } $ は $ o ^ \dagger o \ket { x } \ne o ^ o \dagger \ket { y } $ 。
つまり、adjoint 操作 O ^ を作成することはできません $ \dagger $ 。また、oracles には adjoint が定義されている必要があります。

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>計算ベースの状態に影響を与える oracle の定義
これらの問題の両方に対処するには、 $ 回答を保持する2番目の m qubits のレジスタを導入し $ ます。
次に、すべての計算ベースの状態に対して、oracle の効果を定義します。すべての $ x \in \\ { 0、1 \\ } ^ n、 $ および $ y \in \\ { 0、1 \\ } ^ m $

$$
\begin{align}
    O ( \ket { x } \otimes \ket { y } ) = \ket { x } \otimes \ket { y \ oplus f (x) } 。
\end{align}
$$

ここで $ o = ^ は \dagger $ 構築によって、以前の問題を解決しました。

> [!TIP]
>O ^ 2 があることを確認するには、 $ = { \dagger } $ $ o ^ 2 = \boldone $ $ = $ $ \in \[ が b と b の a a、b!ファンド.NO LOC ({)] 0, 1 \[ !ファンド.なし (})] $ 。
>結果として、 $ O \ket { x y と f } \ket { (x) } = \ket { x } \ket { y/oplus f (x) & oplus f (x) } = \ket { x } \ket { y } $ です。

重要な点として、各計算基準の状態 x y に対して oracle を定義することで、 $ \ket { } \ket { } $ O が $ 他の状態にどのように作用するかも定義し $ ます。
これは、すべてのクォンタム操作と同様に、処理が実行されている $ 状態で線形であるという事実からすぐに続き $ ます。
たとえば、 $ h \ket { 0 } = \ket { + } $ と $ h \ket { 1 } = \ket { - } $ で定義されている Hadamard 操作を考えてみます。
H がどのように動作するかを知りたい場合は、 $ $ h を $ \ket { + } $ $ $ 線形にすることができます。

$$
\begin{align}
H \ket { + } & = \frac { 1 } { \sqrt { 2 } } h ( \ket { 0 }  +  \ket { 1 } ) = \frac { 1 } { \sqrt { 2 } } (h \ket { 0 } + H \ket { 1 } )\\\\
           &= \frac{1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } ) = \frac 12 ( \ket { 0 }  +  \ket { 1 }  +  \ket { 0 1 }  -  \ket { } ) = \ket { 0 } 。
\end{align}
$$

Oracle O を定義する場合は $ $ 、 $ \ket { \psi } $ $ n + m $ qubits の任意の状態を次のように記述できると同様に使用できます。

$$
\begin{align}
\ket{\psi}& = \sum_ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha (x、y) \ket { x } \ket { y}
\end{align}
$$

ここで $ \alpha : \\ { 0、1 \\ } ^ n \times \\ { 0、1 \\ } ^ m \to \mathbb { C は } $ 、状態の係数を表し $ \ket { \psi } $ ます。 したがって

$$
\begin{align}
O \ket { \psi } & = o \sum _ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y } x \\\\ 0 & 、 = 1 ^ n、y 0、1 ^ m (x, y) O \sum _ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\
             &= \sum _ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y/oplus f (x) } 。
\end{align}
$$

## <a name="phase-oracles"></a>フェーズ oracles
または、 $ $ $ $ O への入力に基づいて_フェーズ_を適用して、f を oracle O にエンコード $ することもでき $ ます。たとえば、次のような O を定義する場合があります。 $ $$$
\begin{align}
    O \ket { x } = (-1) ^ { f (x) } \ket { x }
\end{align}
$$
フェーズ oracle が最初に計算ベースの状態 x でレジスタに対して動作する場合 $ \ket { } $ 、このフェーズはグローバルフェーズであるため、監視できません。
ただし、このような oracle は、法則または制御された操作として適用される場合、非常に強力なリソースになります。
たとえば、 $ $ 1 つの-qubit 関数 f の場合、oracle の O_f フェーズを考えてみましょう $ $ 。
そうしたら$$
\begin{align}
    O_f\ket{+}
        &=O_f ( \ket { 0 }  +  \ket { 1 } )/ \sqrt { 2 }\\\\
        &=((-1) ^ { f (0) } \ket { 0 } + (-1) ^ { f (1) } \ket { 1 } )/ \sqrt { 2 }\\\\
        &=(-1) ^ { f (0) } ( \ket { 0 } + (-1) ^ { f (1)-f (0) } \ket { 1 } )/ \sqrt { 2 }\\\\
        &=(-1) ^ { f (0) } Z ^ { f (0)-f (1) } \ket { + } 。
\end{align}
$$

一般的には、oracles の両方のビューを拡大して、1ビットだけではなく実数を返す古典関数を表すことができます。

Oracle を実装する最適な方法を選択することは、特定のアルゴリズム内でこの oracle がどのように使用されるかに大きく依存します。
たとえば、 [Deutsch アルゴリズム](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm)は最初の方法で実装された oracle に依存しますが、 [Grover のアルゴリズム](https://en.wikipedia.org/wiki/Grover's_algorithm)は2番目の方法で実装された oracle に依存しています。


詳細については、 [Gilyén *et*1711.00465](https://arxiv.org/abs/1711.00465)に関する説明をお勧めします。
