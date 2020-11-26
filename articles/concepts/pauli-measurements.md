---
title: P# li 測定の説明: 単一および複数のメジャーの測定演算を使用する方法について説明します。
author: bradben: benbra: ms. date: 12/11/2017 ミリ秒。 topic: article no loc (場所: 記事の内容は含まれません):
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

# <a name="pauli-measurements"></a>P# li 測定

前のディスカッションでは、計算ベースの測定に重点を置いてきました。
実際には、数値表記の観点からは、コンピューティングベースの測定を表すのに便利な、クォンタムコンピューティングで発生する一般的な測定値があります。
作業を行う際に実行する最も一般的な種類の測定は、通常、測定値として使用されます。この測定では、計算ベースの測定値が Q# 汎用化され、 *Pauli measurements* 他のベースや異なる qubits 間のパリティが含まれます。
このような場合、一般的には、通常、 $ x、y、z、 $ $ z \otimes z、x \otimes x、x Y \otimes $ などの演算子で、p# li 演算子の測定について説明します。 

> [!TIP]
> では Q# 、通常、マルチ qubit の演算子は型の配列によって表され `Pauli[]` ます。
> たとえば、X Z Y を表すには、 $ \otimes 配列を使用し \otimes $ `[PauliX, PauliZ, PauliY]` ます。

P# li 演算子の観点から、メジャーについて説明することは、クォンタムエラー修正のサブフィールドで特に一般的です。
では、同様の規則に従います。ここでは、 Q# この測定の別のビューについて説明します。

P# li 測定を考える方法の詳細について検討する前に、クォンタムコンピューター内の1つの qubit がクォンタムの状態にどのように測定されるかについて考えることをお勧めします。
ここでは、 $ n qubit クォンタム状態になっていると $ します。その後、1つの qubit は、状態がである可能性がある 2 ^ n の可能性の半分を測定し $ $ ます。
つまり、測定値は、2つの半分の空白のいずれかにクォンタムの状態を投影します。
この直感を反映するために、測定について考える方法を一般化できます。

これらのサブスペースを簡潔に識別するためには、それらを説明するための言語が必要です。
2つのサブスペースを記述する方法の1つとして、2つの一意の値を持つマトリックスを使用して指定する方法があります。これは、慣例によって午後1時に行われ $ $ ます。
この方法でサブスペースを記述する簡単な例については、 $ Z $ :

$$
\begin{align}
  Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} 。
\end{align}
$$

P# li-z マトリックスの対角線要素を読み取ることで、 $ $ Z に $ $ 2 つの固有ベクトル ( $ \ket { 0 と 1) があり、 } $ $ \ket { } $ 対応する固有値/ $ pm 1 $ があることがわかります。
したがって、qubit を測定し、 `Zero` (状態0に対応する) を取得すると、 $ \ket { } $ qubit の状態が $ $ Z 演算子の + 1 eigenstate であることがわかり $ $ ます。
同様に、を取得した場合は、 `One` qubit の状態が $ z の-1 $ eigenstate であることがわかり $ $ ます。このプロセスは、「P# li Z の測定」として P# li 測定の言語で参照され $ $ ます。これは、計算ベースの測定を実行することとまったく同じです。

$また、 \times $ Z の1つのユニタリ変換である 2 2 つのマトリックス $ も、 $ この条件を満たしています。
つまり、マトリックス a $ = u ^ \dagger Z u を使用することもでき $ ます。ここで、 $ u $ は他の任意の長さ行列で、午後1時の固有ベクトルの測定の2つの結果を定義するマトリックスを提供し $ $ ます。
Preferences Li 測定の表記では、 $ X、Y、Z の各測定値を $ 等価の測定値として識別することで、このような値を参照します。
これらの測定値は、便宜上、次のように提供されます。


|P# li 測定の  | ユニタリ変換  |
|-------------------|------------------------|
|$ $ Z |               $\boldone$             |
|$ $ X |$H               $                    |
|$ $ Y |$HS ^               {\dagger}$         |

つまり、この言語を使用すると、"measure $ Y $ " は HS ^ を適用し $ \dagger $ た後、計算単位で測定することと同じです。ここで、は "フェーズゲート" と呼ばれる組み込みのクォンタム操作であり、これは、長さ [`S`](xref:Microsoft.Quantum.Intrinsic.S) 行列によってシミュレートできます。

$$
\begin{align}
    S =\begin{bmatrix}
        1 & 0 \\\\ 0 & i \end{bmatrix} .
\end{align}
$$

これは、 $ \dagger $ $ $ 次の演算がと等価になるように、クォンタムの状態ベクターに HS ^ を適用し、Z を測定 `Measure([PauliY], [q])` することと同じです。

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        Adjoint S(q);
        H(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

その後、適切な状態が検出されます。これは、クォンタムの状態ベクターに SH を適用する量です $ $ 。上記のスニペットでは、計算ベースに戻る変換は、ブロックを使用することによって自動的に処理され `within … apply` ます。

では、結果と Q# ---して、州---との対話から抽出された古典的な情報は、値 j 0 によって与えられます。これは、測定された `Result` $ \in \\ { \texttt { } \texttt { } \\ } $ $ pauli 演算子の (-1) ^ j eigenspace に結果があるかどうかを示し $ ます。


## <a name="multiple-qubit-measurements"></a>複数の qubit 測定値

次に示すように、マルチ qubit の演算子の測定値は同様に定義されています。

$$
Z \otimes z 1 0 0 0 0 = \begin{bmatrix} & & -1 0 0 0 0 & \\\\ & & & \\\\ & & -1 & 0 \\\\ & & & \end{bmatrix} 0 0 0 1。
$$

したがって、2つの Pauthentication Li z 演算子のすべての製品は、 $ $ $ + 1 と-1 の値で構成される2つのスペースで構成されるマトリックスを形成し $ $ $ ます。
シングル qubit の場合と同様に、両方とも、アクセス可能なベクター空間の半分が $ + 1 eigspace に所属し、残りの半分が-1 の範囲に属していることを意味し $ $ $ ます。
一般に、これに従うのは、Pdefinition Li の演算子と id のすべての情報が含まれているので、その製品の定義から簡単に確認でき $ $ ます。
たとえば、次のように入力します。

$$
\begin{align}
    \otimes \boldone Z =\begin{bmatrix}
        1 & 0 & 0 0 &\\\\
        0 &  1 &  0 &  0 \\\\
        0 &  0 & ~ 1 &  0 \\\\
        0 0 0 & & & -1 \end{bmatrix} 。
\end{align}
$$

前と同様に、このようなマトリックスのすべてのユニタリ変換では、- $ pm 1 eigenvalues によってラベル付けされた2つの半分の空白も記述さ $ れています。
たとえば、 $ \otimes = \otimes z hxh という id の x x h h (z \otimes z) h \otimes h のように $ $ = $ なります。
1 qubit の場合と同様に、2つの2つのすべての値は、 $ \dagger \otimes \id $ $ 4 4 つの \times $ ユニタリマトリックス $ u の $ u ^ (Z) u として書き込むことができます。次の表に示す変換を列挙します。

> [!NOTE]
>次の表では、 $ \operatorname { SWAP を使用し } $ てマトリックス > を示しています。$$
> \begin{align}
>     \operatorname{スワップ } &=
>     \left( \begin { マトリックス}
>1 & 0 & 0 0 &\\\\
>         0 & 0 & 1 & 0 \\\\
>         0 & 1 & 0 & 0 \\\\
>0 0 0 & & & 1 > \end { マトリックス } \right ) >     \end{align}
> $$
> 組み込み操作をシミュレートするために使用され [`SWAP`](xref:Microsoft.Quantum.Intrinsic) ます。

|P# li 測定の     | ユニタリ変換  |
|----------------------|------------------------|
|$ \otimes \boldone Z $| $\boldone\otimes\boldone$|
|$ \otimes \boldone X $| $\otimes \boldone H $|
|$ \otimes \boldone Y $| $HS \dagger \otimes \boldone ^ $|
|$\boldone \otimesZ $ | $ \operatorname { スワップ } $|
|$\boldone \otimesX $ | $ (H \otimes \boldone ) \operatorname { の } スワップ $|
|$\boldone \otimesY $ | $ (HS ^ \dagger \otimes \boldone ) \operatorname { スワップ } $|
|$Z \otimesZ $ | $ \operatorname { cnot } \_ { 10 } $|
|$X \otimesZ $ | $ \operatorname { cnot } \_ { 10 } (H \otimes \boldone ) $|
|$Y \otimesZ $ | $ \operatorname { cnot } \_ { 10 } (HS ^ \dagger \otimes \boldone ) $|
|$Z \otimesX $ | $ \operatorname { cnot } \_ { 10 } ( \boldone \otimes H) $|
|$X \otimesX $ | $ \operatorname { cnot } \_ { 10 } (h \otimes h) $|
|$Y \otimesX $ | $ \operatorname { cnot } \_ { 10 } (HS ^ \dagger \otimes H) $|
|$Z \otimesY $ | $ \operatorname { cnot } \_ { 10 } ( \boldone \otimes HS ^ \dagger ) $|
|$X \otimesY $ | $ \operatorname { cnot } \_ { 10 } (H \otimes HS ^ \dagger ) $|
|$Y \otimesY $ | $ \operatorname { cnot } \_ { 10 } (hs ^ \dagger \otimes hs ^ \dagger ) $|

ここでは、 [`CNOT`](xref:Microsoft.Quantum.Intrinsic.CNOT) 次の理由で操作が表示されます。
マトリックスを含まない各 peach の測定値 $ \boldone $ は、 $ \otimes 上記の理由により、ユニタリから z z までと同等です $ 。
Z z の固有値は、 $ \otimes $ 各計算ベースベクトルを構成する qubits のパリティに依存します。また、制御されていない操作は、このパリティを計算して最初のビットに格納します。
次に、最初のビットを測定した後、結果として得られる半分の領域の id を回復できます。これは、P# li 演算子の測定に相当します。

1つ追加の注意事項: $ z \otimes z $ は、 $ z \otimes \mathbb { 1 と 1 z を順番に測定するのと同じ } $ $ \mathbb { } \otimes $ であると想定されますが、この想定は false になります。
その理由は、z z を測定すると、 $ \otimes $ $ $ これらの演算子の + 1 または-1 のいずれか $ $ の状態になります。
$Z \otimes \mathbb { 1 } $ と $ \mathbb { 1 z を測定 } \otimes すると $ 、まずクォンタム状態ベクトルが z 1 の半分の領域に投影され、 $ 次に \otimes \mathbb { } $ 1 の半分の領域 $ \mathbb { } \otimes $ に投影されます。計算ベースのベクトルが4つあるため、両方の測定を実行すると、状態が4分の1に減少し、1つの計算ベースのベクトルに縮小されます。

## <a name="correlations-between-qubits"></a>量子ビット間の相関関係
X x や z z などの P# li マトリックスの保存されていない製品を測定する別の方法として、 $ \otimes これらの $ $ \otimes $ 測定値を使用すると、2つの qubits 間の相関関係に格納されている情報を確認できます。
$X \otimes \id $ を測定すると、最初の qubit にローカルに格納されている情報を確認できます。
クォンタムコンピューティングではどちらの種類の測定も同等の価値がありますが、前者はクォンタムコンピューティングの能力を測定します。
クォンタムコンピューティングでは、学習する情報が1つの qubit に格納されておらず、すべての qubit にローカルに格納されていないことがわかります。したがって、この情報は、結合測定 (z z など) を使用して参照することによってのみ、 $ \otimes マニフェストに $ なります。

たとえば、エラー修正では、保護しようとしている状態について何も学習していないときに発生したエラーを確認したい場合がよくあります。
[ビットフリップコードサンプル](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code)では、 $ z z や z z などの測定値を使用してこれを行う方法の例を示して \otimes \otimes \id $ $ \id \otimes \otimes $ います。 <--TODO: ビットフリップコードサンプルがオンボードになるとすぐに、これをサンプルブラウザーへのリンクに変更します。 -->

$X \otimes Y \otimes Z などの任意の演算子 \otimes \boldone $ も測定できます。
P# li 演算子のすべてのその他の製品には、2つの固有値- $ pm 1 しかあり $ ません。固有値はベクター空間全体の半分のスペースを構成します。
そのため、これらは上記の要件と一致します。

では Q# 、このような測定値が $ $ 結果を生成する場合は j が返され $ ます (-1) ^ j $ 。
の組み込み機能として Pdiagonalizing の測定値を持つこと Q# は役に立ちます。このような演算子を測定するには、制御されていないゲートと基本変換の長いチェーンが必要であり、その操作を、 $ $ Z との積として表現するために必要な U ゲートを記述する必要があり $ $ $ \id $ ます。
これらの定義済みの測定値のいずれかを実行することを指定できるようにすることで、計算ベースの測定によって必要な情報が得られるように、基になる方法を気にする必要がなくなります。
Q# 必要なすべての基準変換を自動的に処理します。
詳細については、「」および「」操作を参照してください [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) [`MeasurePaulis`](xref:Microsoft.Quantum.Measurement.MeasurePaulis) 。

## <a name="the-no-cloning-theorem"></a>No-Cloning 定理

クォンタム情報は強力です。
これにより、最もよく知られている古典アルゴリズムよりも指数関数的に数値を指数関数的に処理できるようにすることが可能になります。また、正確にシミュレートするためにクラシックデプロイに必要な、関連する電子システムを効率的にシミュレートできます。
ただし、クォンタムコンピューティングの能力には制限があります。
このような制限は、 *複製なしの定理* によって与えられます。

No-Cloning 定理はこのという名前です。
クォンタムコンピューターによる汎用クォンタム状態の複製は禁止されています。
定理の証明は、非常に簡単です。
複製なしの定理の完全な証明は、ここで説明するための技術的なものではありませんが、追加の補助 qubits が存在しない場合の証拠は、この範囲内にあります。

このようなクォンタムコンピューターでは、複製操作は、1つのユニタリ行列によって記述される必要があります。
複製しようとしているクォンタムの状態が破損する可能性があるため、測定は禁止されています。
複製操作をシミュレートするために、次のようなプロパティを持つために使用されている、 $$
  U \ket { \psi } \ket { 0 } = \ket { \psi }\ket{\psi}
$$
任意の状態 $ \ket { \psi } $ 。
マトリックス乗算の直線性プロパティは、2番目のクォンタム状態の場合 $ \ket { \phi } $ 、

$$
\begin{align}
    U \left [ \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ] \ket { 0}
    &= \frac{1 } { \sqrt { 2 } } U \ket { \phi } \ket { 0}
      + \frac{1 } { \sqrt { 2 } } U \ket { \psi } \ket { 0 }\\\\
    &= \frac{1 } { \sqrt { 2 } } \left ( \ket { \phi } \ket { \phi }  +  \ket { \psi }\ket{\psi}
        \right) \\\\
    &\ne \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ) \otimes \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right )) \right 。
\end{align}
$$

これにより、No-Cloning 定理の背後に基本的な直感が提供されます。不明なクォンタム状態をコピーするすべてのデバイスは、少なくとも、コピーする状態の一部でエラーを発生させる必要があります。
Cloner が入力状態で直線的に動作することを前提として、補助 qubits の追加や測定によって違反が発生する可能性がありますが、このような対話によって、測定統計を通じてシステムに関する情報が漏洩し、そのような場合には正確な複製を防ぐことができます。
No-Cloning の完全な証明については、「」 [を](xref:microsoft.quantum.more-information)参照してください。

クォンタムの状態を複製できる場合は、クォンタムの状態を定理することができるので、クォンタムの計算を理解するためには、No-Cloning のが重要です。
実際には、ハイゼンベルグの vaunted の不確定性の原則に違反する可能性があります。
または、最適な cloner を使用して、複雑なクォンタム分布から1つのサンプルを取得し、1つのサンプルだけからその分布について学習できる可能性のあるすべてのことを学ぶこともできます。
これは、コインと観察ヘッドを反転し、その結果について友人に伝えたときに、そのコインの分布が $ p = 0.512643 \ ldots でベルヌーイでなければならないということです $ 。  このようなステートメントは非 sensical になります。これは、1つの情報 (ヘッドの結果) は、十分な前の情報を使用せずに、分布をエンコードするために必要な多くの情報を提供できないためです。
同様に、事前の情報がないと、p を知らなくても、このようなコインを完全に複製することはできません $ $ 。

クォンタムコンピューティングでは、情報は無料です。
測定された各 qubit は1ビットの情報を提供し、No-Cloning 定理は、システムに関する情報とそれに対して発生した問題の基本的なトレードオフを回避するために侵入できるバックドアがないことを示しています。
