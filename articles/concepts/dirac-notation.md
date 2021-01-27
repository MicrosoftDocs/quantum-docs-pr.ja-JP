---
title: Dirac 表記の説明: Dirac 表記を使用して、クォンタムの状態を表し、クォンタム操作をシミュレートする方法について説明します。
author: QuantumWriter uid: benbra: v-ms. date: 12/11/2017 ms. topic: 概念用のものはありません。
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

# <a name="dirac-notation"></a>Dirac 表記

列ベクトル表記は、線形代数では広く使用されていますが、多くの場合、特に複数の qubits を処理する場合、クォンタムコンピューティングでは煩雑です。  たとえば、がベクターとして定義されている場合、 $ \psi $ $ \psi $ が行または列のベクターであるかどうかは明示的に明確ではありません。  したがって $ \phi $ 、とがベクターの場合、 $ \psi $ $ \phi \psi $ との形状が $ \phi $ $ \psi $ コンテキストで不明確になるため、が定義されている場合は、も同様に不明確です。  ベクターの形状についてはあいまいではなく、前に紹介した線形代数表記を使用して単純なベクターを表現することは非常に面倒です。 たとえば、 $ $ 各 qubit が値0を受け取る n qubit 状態を記述する場合は、 $ $ 状態を正式に次のように表現します。 

$$\begin{bmatrix}1 \\\\ 0 \end{bmatrix} \otimes \cdots \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} 。 $$  

ベクターは指数関数的に大きくなるため、このような製品を評価するのは現実的ではありません。この表記は、実際には、前の表記法を使用して指定できる状態の最適な説明です。  

[*Dirac 表記*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) では、クォンタム機構の正確なニーズに合わせて新しい言語を提示することで、これらの問題を解決します。  このため、このセクションの例は、クォンタムの状態を記述する方法を厳密に説明することをお勧めしませんが、クォンタムのアイデアを簡潔に表現するための提案として閲覧者に伝えることをお勧めします。

Dirac 表記には、 *bra* vector と *k* vector という2種類のベクトルがあります。これは、一緒に配置すると、 *braket* または内部の製品を形成するためです。  $ \psi $ が列ベクターの場合は、dirac 表記でとして書き込むことができます。ここで、 $ \ket { \psi } $ $ \ket { \ cdot は、 } $ *k* vector の単位列ベクトルであることを示します。  同様に、行ベクター $ \psi ^ \dagger $ はとして表現され $ \bra { \psi } $ ます。 言い換えると、 $ \psi ^ \dagger $ は、の転置の要素にエントリごとに複雑な活用形を適用することによって取得され $ \psi $ ます。 Bra k notation は、 $ \braket { \psi | \psi } $ $ \psi $ これが定義1である vector の内部積 $ $ であることを直接意味します。  

一般的に、 $ \psi $ と $ \phi $ がクォンタム状態ベクトルである場合、その内部積は、 $ \braket { \phi | \psi } $ 状態 $ \ket { \psi } $ を測定する確率 $ \ket { \phi } $ が $ | \braket { \phi | \psi } | ^ 2 $ であることを意味します。  

次の規則は、0と1の値をエンコードするクォンタムの状態を記述するために使用されます。

$$
\begin{bmatrix}1 \\\\ 0 \end{bmatrix} = \ket { 0 } 、\qquad
\begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \ket { 1 } 。
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a>例: Dirac 表記を使用した Hadamard 操作の表現

次の表記は、Hadamard ゲートを0および1に適用した結果として得られる状態を示すためによく使用され $ \ket { } $ $ \ket { } $ $ ます (Bloch 球の + x および-x の各方向の単位ベクトルに対応し $ $ $ ます)。

$$
\frac{1 } { \sqrt { 2 } } \begin{bmatrix} 1 \\\\ 1 \end{bmatrix} = H \ket { 0 } = \ket { + } 、\qquad
\frac{1 } { \sqrt { 2 } } \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} = H \ket { 1 } = \ket { - } 。
$$

これらの状態は、dirac 表記を使用して $ \ket { 、0 } $ と $ \ket { 1 } $ の合計として拡張することもできます。

$$
\ket{+}= \frac{1 } { \sqrt { 2 } } ( \ket { 0 }  +  \ket { 1 } )、 \qquad \ket { - } = \frac { 1 } { \sqrt { 2 } } ( \ket { 0 }  -  \ket { 1 } )。
$$

### <a name="computational-basis-vectors"></a>計算ベースベクター

これは、これらの状態がしばしば *コンピューティングベース* と呼ばれる理由を示しています。すべてのクォンタム状態は常に計算ベースベクターの合計として表現でき、そのような合計は dirac 表記を使用して簡単に表現できます。  また、状態 $ \ket { + } $ と、 $ \ket { - } $ クォンタム状態の基礎を形成することもあります。  これは次のように表示されます。

$$
\ket{0 } = \frac { 1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } )、 \qquad \ket { 1 } = \frac { 1 } { \sqrt { 2 } } ( \ket { + }  -  \ket { - } )。
$$

Dirac 表記の例として、0 ~ 1 の内部積である braket 0 1 を考えてみ $ \braket { | } $ $ $ $ $ ます。  このファイルは、 

$$
\braket{0 | 1 1 } = \begin{bmatrix} 0 0 & 1 0 \end{bmatrix} \begin{bmatrix} \\\\ \end{bmatrix} = 。
$$

これ $ \ket { } $ は、0と $ \ket { 1 } $ が直交ベクトルであることを示し $ \braket { ます。つまり、0 | 1 } = \braket { 1 1 | 0 0 } = $ です。  また、定義 $ \braket { が 0 0 1 1 1 でもあり | } = \braket { | } = $ ます。これは、2つの計算ベースベクトルを *orthonormal* として呼び出すことができることを意味します。

これらの orthonormal プロパティは、次の例で役に立ちます。 状態が $ \ket { \psi } = { \frac { 3 } { 5 } } \ket { 1 }  +  { \frac { 4 } { 5 } } \ket { 0 } $ $ \braket { | } = $ の $ $ 場合、1 0 0 を測定する確率は 

$$
\big|\braket{1 | \psi } \big | ^ 2 = \left | \frac { 3 } { 5 } \braket { 1 | 1 }  + \frac { 4 } { 5 } \braket { 1 | 0 } \right | ^ 2 = \frac { 9 } { 25 } 。
$$

### <a name="tensor-product-notation"></a>その他の製品表記

Dirac 表記には、その中に、暗黙的な、または製品構造も含まれています。  これは、クォンタムコンピューティングでは、2つの非相関クォンタムレジスタによって記述された状態ベクトルが2つの状態ベクトルの3つの状態ベクトルに含まれるため、重要です。  クォンタムの計算について説明する場合は、その製品構造を簡潔に説明したり、その構造を簡潔に記述したりすることが重要です。  このように、 $ \psi \otimes \phi $ すべての2つのクォンタム状態ベクトルに対して書き込みを行うことができ $ \phi $ $ \psi $ $ \ket { \psi } \ket { \phi } $ ます。ただし、として明示的に記述されることもあり $ \ket { \psi } \otimes \ket { \phi } $ $ \otimes $ ますが、ベクター間での記述は不要です。  たとえば、2つの qubits がゼロ状態に初期化された状態は、

$$
\begin{bmatrix}1 0 0 0 1 = 1 0 0 0 \\\\ \\\\ \\\\ \end{bmatrix} = \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} = \ket { } \otimes \ket { } = \ket { } \ket { } です。
$$

同様に、 $ \ket { 整数 p の状態 p は、 } $ $ $ 整数 p をバイナリ表現でエンコードするクォンタム状態を表し $ $ ます。  たとえば、 $ $ 符号なしのバイナリエンコーディングを使用して番号5を表現する場合は、次のように表現することもできます。

$$
\ket{1 } \ket { 0 } \ket { 1 } = \ket { 101 } = \ket { 5 } 。
$$

この記法では、 $ \ket { 0 は } $ 単 qubit 状態を参照する必要はありませんが、バイナリエンコーディングを0として格納する *qubit レジスタ* である必要があり $ $ ます。  これら2つの表記の違いは、通常、コンテキストから明らかになります。  この規則は、次のいずれかの方法で記述できる最初の例を簡略化するために役立ちます。

$$
\begin{bmatrix}1 0 1 0 0 0 0 \\\\ \end{bmatrix} \otimes \cdots \otimes \begin{bmatrix} \\\\ \end{bmatrix} = \ket { } \otimes \cdots \otimes \ket { } = | \cdots \rangle = \ket { } ^ { \otimes } = \ket { } です。
$$

### <a name="example-describing-superposition-with-dirac-notation"></a>例: Dirac 表記で法則を記述する

Dirac 表記を使用してクォンタムの状態を記述するもう1つの例として、長さ n のすべての可能なビット文字列に対して同じ法則を持つクォンタム状態を記述する次のような同等の方法を検討してください。 $$

$$
H ^ { \otimes n } \ket { 0 } = \frac { 1 } { 2 ^ { n/2 } } \sum _ { j = 0 } ^ { 2 ^ n-1 } \ket { j } = \ket { + } ^ { \otimes n }
$$

ここでは、 $ n ビットの合計が 0 $ ~ $ 2 ^ { n-1 である理由を不思議に思うかもしれ } $ $ $ ません。  まず、 $ n ビットには 2 ^ n の異なる構成があることに注意 { } $ $ して $ ください。  これは、1つのビットが2つの $ 値を取り $ 、2つのビットが4つの $ $ 値を受け取ることができることに注目してください。 一般に、これは $ 2 つの異なる可能性のあるビット文字列がありますが、 $ $ 1 \cdots 1 = 2 ^ n-1 でエンコードされた最大値であるため、 $ 合計の上限になります。
この例では、この $ \ket { + } ^ { \otimes } = \ket { + } $ $ \ket { } ^ { \otimes } = \ket { } $ 数値表記規則は通常、すべての qubit がゼロに初期化された計算ベースの状態用に予約されているため、この例では n を 0 n 0 として使用しませんでした。  このような規則は、この場合には実用的なものですが、クォンタムコンピューティングの資料には採用されていません。

### <a name="expressing-linearity-with-dirac-notation"></a>Dirac 表記を使用した直線性の表現

Dirac 表記のもう1つの優れた機能は、これが線形であるということです。  4つのクォンタム状態ベクトルに対して書き込みを行う場合は、 

$$( \alpha \ket { \psi }  + \beta \ket { \phi } ) \otimes (- \gamma \ket { カイ }  +  \delta \ket { \omega } )- = \alpha \gamma \ket { \psi } \ket { カイ- }  +  \alpha \delta \ket { \psi } \ket { \omega } + \beta \gamma \ket { \phi } \ket { カイ } + \beta \delta \ket { \phi } \ket { \omega } 。$$

つまり、状態ベクター間での整理された製品の作成が通常の乗算と同じになるように、「Dirac 表記」で、「」という表記を配布することができます。

Bra ベクターは、k ベクターと同様の規則に従います。  たとえば、vector $ \bra { \psi } \bra { \phi } $ は state vector $ \psi ^ \dagger \otimes \phi ^ \dagger = ( \psi \otimes \phi ) ^ \dagger $ に相当します。 K vector $ \ket { \psi } $ が 0 1 の場合、 $ \alpha \ket { }  +  \beta \ket { } $ ベクターの bra vector バージョンは $ \bra { \psi } = \ket { \psi } ^ \dagger = ( \bra { 0 } \alpha ^ * + \bra { 1 } \beta ^ *) に $ なります。

たとえば、状態 $ \ket { \psi } = \frac { } { } \ket { }  +  \frac { } { } \ket { } $ をまたはに測定するクォンタムプログラムを使用して $ \ket { + } $ $ \ket { - } $ 、状態 3 5 1 4 5 0 を測定する確率を計算するとします。 デバイスが出力する確率は、次のようになります。 $ \ket { - } $ 

$$|\braket{- |\psi}|^ 2 = \left | \frac { 1 } { \sqrt { 2 } } ( \bra { 0 }  -  \bra { 1 } ) ( \frac { 3 } { 5 } \ket { 1 }  +  \frac { 4 } { 5 } \ket { 0 } ) \right | ^ 2 = \left | - \frac { 3 } { 5 \sqrt { 2 } }  +  \frac { 4 } { 5 \sqrt { 2 } } \right | ^ 2 = \frac { 1 } { 50 } 。$$

確率の計算で負の符号が表示されるのは、クォンタムの干渉の取り組みです。これは、クォンタムコンピューティングが古典的なコンピューティングよりも優れているというメカニズムの1つです。

## <a name="ketbra-or-outer-product"></a>ketbra または外側の製品

Dirac 表記で説明する最後の項目は、 *ketbra* または outer 製品です。  外側の製品は dirac 表記で表現され $ \ket { \psi } \bra { \phi } $ 、bras と kets は brakets と逆の順序で発生するため、ketbras と呼ばれることもあります。  外側の製品は、 $ \ket { \psi } \bra { \phi } = \psi \phi ^ \dagger $ クォンタムの状態ベクター $ \psi $ と $ \phi $ として行列乗算を使用して定義されます。  この表記法の最も単純で最も一般的な例を次に示します。

$$
\ket{0 0 } \bra { } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \begin{bmatrix} & \end{bmatrix} = \begin{bmatrix} & \\\\ & \end{bmatrix} \qquad \ket { } \bra { } = \begin{bmatrix} \\\\ \end{bmatrix} \begin{bmatrix} & \end{bmatrix} = \begin{bmatrix} & \\\\ & \end{bmatrix} 1 0 1 0 0 0 1 1 の場合は1
$$

Ketbras は、クォンタム状態を固定値に射影するため、多くの場合、プロジェクターと呼ばれます。  これらの操作は、(ベクターの基準を維持するのではなく)、また、クォンタムコンピューターがプロジェクターを確定的に適用できないということではありません。  しかし、プロジェクターは、クォンタムの状態に対して測定されるアクションを記述する美しいジョブを実行します。  たとえば、状態を0として測定した場合、 $ \ket { \psi } $ $ 状態が $ 測定の結果として得られる変換は次のようになります。

  $$\ket{\psi}\right \frac 矢印 {( \ket { 0 } \bra { 0 } ) \ket { \psi } } { | \braket { 0 | \psi } | } = \ket { 0 } 、$$

1つは、状態を測定して0であることを確認する場合 $ \ket { } $ です。  繰り返しますが、このようなプロジェクターは、クォンタムコンピューターの状態に対して確定的には適用できません。  代わりに、 $ \ket { } $ いくつかの固定確率で表示される結果0を使用して、ランダムに適用することができます。  このような測定値の確率は、その状態のクォンタムプロジェクターの予測値として記述できます。

$$
\bra{\psi}( \ket { 0 } \bra { 0 } ) \ket { \psi } = | \braket { \psi | 0 } | ^ 2、$$

つまり、プロジェクターは測定プロセスを表現する新しい方法を提供しています。

代わりに、マルチ qubit 状態の最初の qubit を1に測定する場合は $ 、 $ プロジェクターと dirac 表記を使用して、このプロセスを簡単に記述することもできます。

$$
P ( \text { 最初の qubit = 1 } ) = \bra { \psi } \left ( \ket { 1 } \bra { 1 } \otimes \boldone ^ { \otimes n-1 } \right ) \ket { \psi } 。
$$

ここでは、id 行列を Dirac 表記で簡単に記述できます。

$$
\boldone= \ket{0 0 1 1 1 1 } \bra { } + \ket { } \bra { } = \begin{bmatrix} & 0 0 \\\\ & 1 \end{bmatrix} 。
$$

2つの場合、プロジェクターは次のように拡張できます。 

$$
\ket{1 1 1 1 } \bra { } \otimes \id = \ket { } \bra { } \otimes ( \ket { 0 } \bra { 0 } + \ket { 1 1 } \bra { } ) = \ket { 10 } \bra { 10 }  +  \ket { 11 } \bra { 11 } 。
$$

これは、列ベクトル表記を使用する multiqubit の likelihoods の測定値についての説明と一致していることがわかります。

$$
P ( \text { 最初の qubit = 1 } ) = \psi ^ \dagger (e \_ { 10 } e \_ { 10 } ^ \dagger + e \_ { 11 } e \_ { 11 } ^ \dagger ) \psi = | e \_ { 10 } ^ \dagger \psi | ^ 2 + | e \_ { 11 } ^ \dagger \psi | ^ 2、$$

これは、multi-factor bit の測定に関する議論に一致します。  ただし、この結果をマルチ qubit ケースに汎化することは、列ベクトル表記よりも Dirac 表記法を使用する方が少し単純で、前の処理とまったく同じです。

## <a name="density-operators"></a>密度演算子

Dirac 表記を使用して表すもう1つの便利な演算子は、 *密度演算子* です。これは、 *状態演算子* とも呼ばれます。
クォンタム状態ベクトルの密度演算子は、\rho の形式 $ に = \ket { \psi } \bra { \psi } $ なります。
このように、ベクターではなく、マトリックスとして状態を表すこの概念は、確率の計算を表す便利な方法を提供し、同じ形式内のクォンタムの不確実性だけでなく統計の不確実性を示すこともできるため便利です。
一般的なクォンタム状態の演算子は、ベクターではなく、クォンタムコンピューティングの一部の領域で広く使われていますが、フィールドの基本を理解する必要はありません。
興味のある読者については、「」で提供されている参照資料のいずれ [かを参照](xref:microsoft.quantum.more-information)してください。

## <a name="no-locq-gate-sequences-equivalent-to-quantum-states"></a>Q# クォンタムの状態に相当するゲートシーケンス

クォンタム表記とプログラミング言語については、最後 Q# に説明します。このドキュメントでは、クォンタムの状態がクォンタムコンピューティングにおける情報の基本的なオブジェクトであることを説明しました。  その後、で Q# は、クォンタム状態の概念がないということに驚かれるかもしれません。  すべての状態は、その準備に使用された操作によってのみ記述されます。  前の例は、このことを示す優れた図解です。  レジスタ内のすべてのクォンタムビット文字列に対して uniform 法則を表現するのではなく、結果を $ H ^ n 0 として表すことができ { \otimes } \ket { } $ ます。  これは、その理由をクラシックデプロイことができるという利点だけでなく、アルゴリズムを実装するためにソフトウェアスタックを通じて伝達される必要がある操作を簡潔に定義することもできます。  このため、 Q# は、クォンタムの状態ではなくゲートシーケンスを生成するように設計されています。ただし、理論的なレベルでは、2つのパースペクティブは同等です。
