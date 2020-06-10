---
title: ディラックの記法
description: Dirac 表記を使用して、クォンタムの状態を表し、クォンタム操作をシミュレートする方法について説明します。
author: QuantumWriter
uid: microsoft.quantum.concepts.dirac
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
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
ms.openlocfilehash: 958910452109fc722999acddd70894c458e38357
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630380"
---
# <a name="dirac-notation"></a>Dirac 表記

列ベクトル表記は、線形代数では広く使用されていますが、多くの場合、特に複数の qubits を処理する場合、クォンタムコンピューティングでは煩雑です。  たとえば、$-psi をベクトルとして定義した場合、 $ $ \ psi $ が行または列のベクターであるかどうかは明示的に明確にはされません。  したがって、$/phi と $-psi がベクターの場合、$ $ $ /phi $ と $-psi の形状が $ コンテキストで不明確になることがあるため、$-phi \ psi が定義されている場合にも、同様に不明確になり $ ます。  ベクターの形状についてはあいまいではなく、前に紹介した線形代数表記を使用して単純なベクターを表現することは非常に面倒です。 たとえば、 $ 各 qubit が値 $0 を受け取る $n qubit 状態を記述する場合は、 $ 状態を正式に次のように表現します。 

$ $ \ begin{ bmatrix } 1 \\ \\ 0 & end{ bmatrix } \begin bmatrix } 1 \\ \\ 0 \ end{ bmatrix } です (& o)。 $$  

ベクターは指数関数的に大きくなるため、このような製品を評価するのは現実的ではありません。この表記は、実際には、前の表記法を使用して指定できる状態の最適な説明です。  

[*Dirac 表記*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation)では、クォンタム機構の正確なニーズに合わせて新しい言語を提示することで、これらの問題を解決します。  このため、このセクションの例は、クォンタムの状態を記述する方法を厳密に説明することをお勧めしませんが、クォンタムのアイデアを簡潔に表現するための提案として閲覧者に伝えることをお勧めします。

Dirac 表記には、 *bra* vector と*k* vector という2種類のベクトルがあります。これは、一緒に配置すると、 *braket*または内部の製品を形成するためです。  $ \ Psi $ が列ベクターの場合は、Dirac 表記で $ \ket \ psi $ として書き込むことができます { } 。 $ \ket/ { cdot $ は、 } これが unit 列ベクトル (つまり、 *k* vector) であることを示します。  同様に、行ベクター $ \ psi ^ \ ダガー $ は $ \bra/psi $ として表され { } ます。 つまり、$-psi $ の転置の要素にエントリごとに複雑な活用形を適用することで、$/psi ^ を取得 $ できます。 Bra k 記法は、$ \braket-psi { | \ psi } $ がそれ自体を持つ vector $ \ psi の内部積であることを意味し $ ます。これは、定義 $1 によって決まり $ ます。  

一般的に、$ \ psi $ と $/phi $ がクォンタム状態ベクトルの場合、内部製品は $ \braket { \ phi | \ psi } $ となります。これは、state $ \ket { \ psi } $ を $ \ket/phi $ に測定する確率が { } $ | \braket/ { phi | } | ^ 2 $ であることを意味します。  

次の規則は、0と1の値をエンコードするクォンタムの状態を記述するために使用されます。

$ $ \ begin{ bmatrix } 1 \\ \\ 0 \ end{ bmatrix } = \ket{0 } , \qquad \ begin{ bmatrix } 0 \\ \\ 1 \ end{ bmatrix } = \ket{1 } .
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a>例: Dirac 表記を使用した Hadamard 操作の表現

次の表記は、Hadamard ゲートを $ \ket{0 $ および $ \ket{1 $ に適用した結果として得られる状態を示すためによく使用され } } ます (これは、Bloch 球の $ + x と $ x の方向の単位ベクトルに対応し $ $ ます)。

$ $ \frac{1 } {\ sqrt{2 } } \ begin{ bmatrix } 1 \\ \\ 1 & end{ bmatrix } = h \ket {0 } = \ket { +}, \qquad \frac{1 } {\ sqrt{2 } } \ begin{ bmatrix } 1 \\ \\ -1, end{ bmatrix } = H \ket {1 } = \ket { }.
$$

これらの状態は、Dirac 表記を使用して、$ \ket{0 } $ と $ \ket{1 $ の合計として拡張することもでき } ます。

$ $ \ket { +} = \frac{1 } {\ sqrt{2 } } (\ket{0 } + \ket{1 } )、\qquad \ket { -} = \frac{1 } {\ sqrt{2 } } (\ket{0 } -\ket{1 } )。
$$

### <a name="computational-basis-vectors"></a>計算ベースベクター
これは、これらの状態がしばしば*コンピューティングベース*と呼ばれる理由を示しています。すべてのクォンタム状態は常に計算ベースベクターの合計として表現でき、そのような合計は dirac 表記を使用して簡単に表現できます。  また、この逆も同様です。これは、 { "$ \ket +} $ { " と "$ \ket-} $" がクォンタム状態の基準となることもあります。  これは次のように表示されます。

$ $ \ket{0 } = \frac{1 } {\ sqrt{2 } } (\ket { +} + \ket { -})、\qquad \ket{1 } = \frac{1 } {\ sqrt{2 } } (\ket { +}-\ket { -})。
$$

Dirac 表記の例として、$0 ~ $1 の内部積である braket $ \braket{0 | 1 $ について考えてみ } $ $ ます。  このファイルは、 

$ $ \braket{0 | 1 } = \ begin{ bmatrix } 1 & 0 \ end{ bmatrix } \ begin{ bmatrix } 0 \\\\ 1 \end { bmatrix } = 0. $ $

これは、$ \ket{0 } $ と $ \ket{1 } $ が直交ベクトルであることを示しています。これは、$ \braket{0 | 1 } = \braket{1 | 0 = 0 であることを意味 } $ します。  また、definition $ \braket{0 | 0 } = \braket{1 | 1 } = 1 でもあり $ ます。これは、2つの計算ベースベクトルを*orthonormal*として呼び出すことができることを意味します。
これらの orthonormal プロパティは、次の例で役に立ちます。 状態が $ \ket { \ psi } = {\frac{3 } {5} } \ket{1 } + {\frac{4 } {5 } } \ket{0 } $ の場合、$ \braket{1 | 0 = 0 であるため } $ 、$1 を測定する確率 $ は  

$ $ \ big | \braket{1 | \ psi } \ big | ^ 2 = \ left | \frac{3 } {5 } \braket{1 | 1 } + \frac{4 } {5 } \braket{1 | 0 } \ right | ^ 2 = \frac{9 } {25 } . $ $ 

### <a name="tensor-product-notation"></a>その他の製品表記
Dirac 表記には、その中に、暗黙的な、または製品構造も含まれています。  これは、クォンタムコンピューティングでは、2つの非相関クォンタムレジスタによって記述された状態ベクトルが2つの状態ベクトルの3つの状態ベクトルに含まれるため、重要です。  クォンタムの計算について説明する場合は、その製品構造を簡潔に説明したり、その構造を簡潔に記述したりすることが重要です。  これは、 $ すべての2つのクォンタム状態ベクトル $ $ /phi と $/psi を $ \ket/psi \ket として作成できることを意味し $ ます。ただし、$ \ket/psi/phi $ として明示的に記述されている場合も { } { } あり { } { } $ ますが、ベクター間での $ otimes の記述は不要です。  たとえば、2つの qubits がゼロ状態に初期化された状態は、

$ $ \ begin{ bmatrix } 1 \\ \\ 0 0 \\ \\ \\ \\ 0 \ end{ bmatrix } = \ begin{ bmatrix } 1 \\ \\ 0 & end{/ bmatrix } otimes \ begin{ bmatrix } 1 \\ \\ 0 \ end{ bmatrix } = \ket{0/ } otimes \ket{0 } = \ket{0 } \ket{0 } です。
$$

同様に、整数 $p の状態 $ \ket{p $ は、 } $ $p 整数をバイナリ表現でエンコードするクォンタム状態を表し $ ます。  たとえば、 $ 符号なしのバイナリエンコーディングを使用して数値 $5 を表現する場合は、次のように表現することもできます。

$ $ \ket{1 } \ket{0 } \ket{1 } = \ket{101 } = \ket{5 } .
$$

この記法では、$ \ket{0 } $ は単 qubit 状態を参照する必要はありませんが、$0 のバイナリエンコードを格納する*qubit レジスタ*を必要とし $ ます。  これら2つの表記の違いは、通常、コンテキストから明らかになります。  この規則は、次のいずれかの方法で記述できる最初の例を簡略化するために役立ちます。

$ $ \ begin{ bmatrix } 1 \\ \\ 0 & end{ bmatrix } \ otimes \ cドット/otimes \begin { bmatrix } 1 \\ \\ 0 \ end{ bmatrix } = \ket{0 } \ket{0 } = | 0 \cdots 0 \rangle = \ket{0 } ^ {/otimes n } = \ket{0 } です (& o)。
$$

### <a name="example-describing-superposition-with-dirac-notation"></a>例: Dirac 表記で法則を記述する
Dirac 表記を使用してクォンタムの状態を記述するもう1つの例として、次のように同等のクォンタム状態を記述する方法を検討してください。これは、法則になる可能性のあるすべてのビット文字列に対して同じである必要があり $n$

$ $ H ^ {\ otimes n } \ket{0 } = \frac{1 } {2 ^ {n/2 } } \ sum_ {j = 0 } ^ {2 ^ n-1 } \ket{j } = \ket { +} ^ {/otimes n } .
$$

ここで、合計が $0 から $ $ 2 ^ {n } -1 $ の $n ビットになるのはなぜですか $ 。  まず、$n ビットには、$ 2 ^ {n $ の異なる構成があることに注意 } $ してください。  これは、1つのビットが $2 の値を受け取ることはでき $ ますが、2つのビットが $4 の値を受け取る可能性があることに注意してください $ 。 一般に、これは、$ 2 ^ n 異なる可能性のあるビット文字列がありますが、 $ $1 \cdots 1 = 2 ^ n-1 でエンコードされた最大値であるため、合計の上限になり $ ます。
この例では、$ \ket { +} ^ {\ otimes n } = \ket { +} $ を $ \ket{0 ^ {\ otimes n = \ket{0 $ と同じように使用していません } } } 。この数値表記規約は、通常、すべての qubit が0に初期化されています。  このような規則は、この場合には実用的なものですが、クォンタムコンピューティングの資料には採用されていません。

### <a name="expressing-linearity-with-dirac-notation"></a>Dirac 表記を使用した直線性の表現
Dirac 表記のもう1つの優れた機能は、これが線形であるということです。  4つのクォンタム状態ベクトルに対して書き込みを行う場合は、 

$ $ (\ alpha \ket { \ psi } + \ ベータ \ket { } ) \ otimes (\ gamma \ket { \ カイ } + \ delta \ket- { オメガ } ) = \ alpha \ket/ \gamma psi \ket/ { } { カイ +- } alpha \ket/ \delta psi \ket/ { } { オメガ } \gamma \ket { } { } \delta \ket { } { } +-beta/phi \ket/カイ +/ベータ/phi \ket \

つまり、状態ベクター間での整理された製品の作成が通常の乗算と同じになるように、「Dirac 表記」で、「」という表記を配布することができます。

Bra ベクターは、k ベクターと同様の規則に従います。  たとえば、vector $ \bra { \ psi \bra/ } { phi } $ は、state vector $ \ psi ^ \ ダガー-otimes/phi ^-ダガー (-psi- = \otimes phi) ^/ダガーと同等です $ 。 K vector $ \ket { \ psi } $ が $ \ alpha \ket{0 } + \ beta \ket{1 $ の場合、 } ベクターの bra vector バージョンは $ \bra { \ psi } = \ket/ { psi } ^ \ ダガー = (- } al/alpha ^ * +-al{1} } *) $ になります。

例として、状態 { } } } } } } } を $ \ket{0 { +} $ または $ \ket-} $ として測定するために、クォンタムプログラムを使用して、$ \ket \ psi = \frac{3 {5 \ket{1 + \frac{4 {5 \ket $ という { 状態を測定する確率を計算したいとします。 デバイスが出力する確率は、状態が $ \ket-} $ であることを { 示します。 

$ $ | \braket { -| \ psi } | ^ 2 = \ 左 | \frac{1 } {\ sqrt{2 } } (& b) ( } } \frac{3 } {5 } \ket{1 } + \frac{4 } {5 } \ket{0 } ) \ right ^ 2 \ \frac{3 {5 { | = | } \sqrt 2 } } + \frac{4 } {5 \sqrt {2 } } \ 右 | ^ 2 = \frac{1 { } 50 } . $ $

確率の計算で負の符号が表示されるのは、クォンタムの干渉の取り組みです。これは、クォンタムコンピューティングが古典的なコンピューティングよりも優れているというメカニズムの1つです。

## <a name="ketbra-or-outer-product"></a>ketbra または外側の製品
Dirac 表記で説明する最後の項目は、 *ketbra*または outer 製品です。  外側の製品は、Dirac 表記では $ \ket { \ psi \bra \ phi $ として表され、 } { } bras と kets は brakets と逆の順序で発生するため、ketbras と呼ばれることもあります。  外側の製品は、マトリックス乗算を使用して、 { } { } $ クォンタム状態ベクトル $ \ psi と $ phi の $ \ket \ psi \bra/phi = \ psi \ phi ^ \ ダガーと $ して定義され $ ます。  この表記法の最も単純で最も一般的な例を次に示します。

$ $ \ket{0 } } = \ begin{ bmatrix } 1 \\\\ 0 \ end{\ begin{} 1 bmatrix } bmatrix&0 \ end{ bmatrix } = \ begin{ bmatrix } 1 &0 0 &0 {\qquad \ket{1/end{/begin{} 0 \\\\ \end bmatrix } } } bmatrix \\\\ bmatrix } bmatrix&1 & end{= \ begin{} 0 bmatrix } bmatrix &0 \\\\ 0 &1 \end {に bmatrix } なりました。
$$

Ketbras は、クォンタム状態を固定値に射影するため、多くの場合、プロジェクターと呼ばれます。  これらの操作は、(ベクターの基準を維持するのではなく)、また、クォンタムコンピューターがプロジェクターを確定的に適用できないということではありません。  しかし、プロジェクターは、クォンタムの状態に対して測定されるアクションを記述する美しいジョブを実行します。  たとえば、$ \ket \ psi $ という状態を $0 に測定した場合、 { } 状態が $ 測定の結果として得られる変換は、次のようになります。

  $ $ \ket { \ psi } \rightarrow \ frac { (\ket{0/ } } ) \ket/ { psi } } {| \braket{0 | \ psi } |}= \ket{0 } 、$ $

これは、状態を測定して $ \ket{0 $ として検出した場合に想定し } ます。  繰り返しますが、このようなプロジェクターは、クォンタムコンピューターの状態に対して確定的には適用できません。  代わりに、 } いくつかの固定確率で表示される結果 $ \ket{0 $ を使用して、ランダムに適用することができます。  このような測定値の確率は、その状態のクォンタムプロジェクターの予測値として記述できます。

$ $ \bra { \ psi } (\ket{0 } } /) \ket { /psi } = | \braket { \ psi | 0 } | ^ 2, $ $

つまり、プロジェクターは測定プロセスを表現する新しい方法を提供しています。

代わりに、マルチ qubit 状態の最初の qubit を $1 に測定することを検討する場合は、 $ プロジェクターと Dirac 表記を使用して、このプロセスを簡単に記述することもできます。

$ $ P (\ text{first qubit = 1 } ) = \bra { } (\ket{1 } } ) \ket/psi (} {/otimes n-1 } \ right) { \ psi } です。
$$

ここでは、id 行列を Dirac 表記で簡単に記述できます。

$ $ \ \ket{1 done = \ket{0 } \ ロウ } } } { bmatrix } 1&0 \\\\ 0&1 & end{ですが、このように bmatrix } なります。
$$

2つの場合、プロジェクターは次のように拡張できます。 

$ $ \ket{1 } } \ket{1 } } } } = \ket{10 \bra{10 + \ket{11 \bra{11 のようにして、$ $ = \ket{1 (\ket{0 } } ) = } } + } } します。
$$

これは、列ベクトル表記を使用する multiqubit の likelihoods の測定値についての説明と一致していることがわかります。

$ $ P (\ text1> 最初の qubit = 1 } ) = \ psi ^ \ ダガー (e e \_ {10} \_ {10 } ^ \ ダガー + e \_ {11} e \_ {11 } ^-ダガー)/psi = | e \_ {10 } ^ & ダガー-psi | ^ 2 + | e \_ {11 } ^ \ ダガー \ psi | ^ 2, $ $

これは、multi-factor bit の測定に関する議論に一致します。  ただし、この結果をマルチ qubit ケースに汎化することは、列ベクトル表記よりも Dirac 表記法を使用する方が少し単純で、前の処理とまったく同じです。

## <a name="density-operators"></a>密度演算子

Dirac 表記を使用して表すもう1つの便利な演算子は、*密度演算子*です。これは、*状態演算子*とも呼ばれます。
クォンタム状態ベクトルの密度演算子は、$ \rho = \ket-psi \bra/psi $ という形式に { } { } なります。
このように、ベクターではなく、マトリックスとして状態を表すこの概念は、確率の計算を表す便利な方法を提供し、同じ形式内のクォンタムの不確実性だけでなく統計の不確実性を示すこともできるため便利です。
一般的なクォンタム状態の演算子は、ベクターではなく、クォンタムコンピューティングの一部の領域で広く使われていますが、フィールドの基本を理解する必要はありません。
興味のある読者については、「」で提供されている参照資料のいずれ[かを参照](xref:microsoft.quantum.more-information)してください。

## <a name="q-gate-sequences-equivalent-to-quantum-states"></a>"クォンタム" 状態に相当する Q # ゲートシーケンス
クォンタム表記と Q # プログラミング言語については、最後に説明します。このドキュメントでは、クォンタムの状態がクォンタムコンピューティングにおける情報の基本的なオブジェクトであることを説明しました。  その後、Q # では、クォンタム状態の概念がないことが不思議になるかもしれません。  すべての状態は、その準備に使用された操作によってのみ記述されます。  前の例は、このことを示す優れた図解です。  レジスタ内のすべてのクォンタムビット文字列に対して uniform 法則を表現するのではなく、結果を ^ {/otimes n \ket{0 $ の $H として表すことができ } } ます。  これは、その理由をクラシックデプロイことができるという利点だけでなく、アルゴリズムを実装するためにソフトウェアスタックを通じて伝達される必要がある操作を簡潔に定義することもできます。  このため、Q # はクォンタムの状態ではなくゲートシーケンスを生成するように設計されています。ただし、理論的なレベルでは、2つのパースペクティブは同等です。
