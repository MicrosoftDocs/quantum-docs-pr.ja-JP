---
title: Dirac 表記 |Microsoft Docs
description: Dirac 表記
author: QuantumWriter
uid: microsoft.quantum.concepts.dirac
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 33d964d079c94bd947e35d2c09516b29df1bba11
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184765"
---
# <a name="dirac-notation"></a>Dirac 表記

列ベクトル表記は、線形代数では広く使用されていますが、多くの場合、特に複数の qubits を処理する場合、クォンタムコンピューティングでは煩雑です。  たとえば、$-psi $ をベクターに定義した場合、$ \ psi $ が行または列のベクターであるかどうかは明示的に明確にはされません。  したがって、$ \ phi $ と $-psi $ がベクターである場合、$ \ phi \ psi $ が定義されていれば、$-phi $ と $/psi $ の形状がコンテキストで不明確になる可能性があるため、これも同様に不明確になります。  ベクターの形状についてはあいまいではなく、前に紹介した線形代数表記を使用して単純なベクターを表現することは非常に面倒です。 たとえば、各 qubit が値 $0 $ を受け取る $n $-qubit 状態を記述する場合は、状態を正式に次のように表現します。 

$ $ \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \otimes\begin{bmatrix}1 \\\\ 0 \end{bmatrix}. $$  

ベクターは指数関数的に大きくなるため、このような製品を評価するのは現実的ではありません。この表記は、実際には、前の表記法を使用して指定できる状態の最適な説明です。  

[*Dirac 表記*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation)では、クォンタム機構の正確なニーズに合わせて新しい言語を提示することで、これらの問題を解決します。  このため、このセクションの例は、クォンタムの状態を記述する方法を厳密に説明することをお勧めしませんが、クォンタムのアイデアを簡潔に表現するための提案として閲覧者に伝えることをお勧めします。

Dirac 表記には、 *bra* vector と*k* vector という2種類のベクトルがあります。これは、一緒に配置すると、 *braket*または内部の製品を形成するためです。  $ \ Psi $ が列ベクターの場合は、Dirac 表記で $ \ket{\psi} $ として書き込むことができます。 $ \ket{\cdot} $ は、これが unit 列ベクトル (つまり、 *k* vector) であることを示します。  同様に、行 vector $ \ psi ^ \ ダガー $ は $ \bra{\psi} $ として表現されます。 つまり、$-psi $ は、$ \ psi $ の転置要素にエントリごとに複雑な活用形を適用することによって取得されます。 Bra k 記法は、$ \braket{\psi | \psi} $ が、それ自体を含む vector $ \ psi $ の内部積であることを意味します。これは、定義 $1 $ です。  

より一般的には、$ \ psi $ と $/phi $ がクォンタム状態ベクトルの場合、内部製品は $ \braket{\phi | \psi} $ になります。これは、状態 $ \ket{\psi} $ を $ \ket{\phi} $ として測定する確率が $ | \braket{\phi | \psi} | ^ 2 $ であることを意味します。  

次の規則は、0と1の値をエンコードするクォンタムの状態を記述するために使用されます。

$ $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \ket{0}、\qquad \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} = \ket{1}。
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a>例: Dirac 表記を使用した Hadamard 操作の表現

次の表記は、Hadamard ゲートを $ \ket{0}$ および $ \ket{1}$ に適用した結果として得られる状態を示すためによく使用されます。これは、Bloch 球の $ + x $ と $-x $ の方向の単位ベクトルに対応します。

$ $ \ frac{1}{\ sqrt{2}} \begin{bmatrix} 1 \\\\ 1 \end{bmatrix} = H\ket{0} = \ket{+}、\qquad/frac{1}{\ sqrt{2}} \begin{bmatrix} 1 \\\\-1 \end{bmatrix} = H\ket{1} = \ket{-}。
$$

これらの状態は、Dirac 表記を使用して、$ \ket{0}$ と $ \ket{1}$ の合計として拡張することもできます。

$ $ \ket{+} = \ frac{1}{\ sqrt{2}} (\ket{0} + \ket{1})、\qquad \ket{-} = \ frac{1}{\ sqrt{2}} (\ket{0}-\ket{1})。
$$

### <a name="computational-basis-vectors"></a>計算ベースベクター
これは、これらの状態がしばしば*コンピューティングベース*と呼ばれる理由を示しています。すべてのクォンタム状態は常に計算ベースベクターの合計として表現でき、そのような合計は dirac 表記を使用して簡単に表現できます。  また、この逆も同様です。これは、"$ \ket{+} $" と "$ \ket{-}$" という状態が、クォンタムの状態の基礎となります。  これは次のように表示されます。

$ $ \ket{0} = \ frac{1}{\ sqrt{2}} (\ket{+} + \ket{-})、\qquad \ket{1} = \ frac{1}{\ sqrt{2}} (\ket{+}-\ket{-})。
$$

Dirac 表記の例として、$0 $ と $1 $ の内部積である braket $ \braket{0 | 1} $ について考えてみます。  このファイルは、 

$ $ \braket{0 | 1} = \begin{bmatrix} 1 & 0 \end{bmatrix}\begin{bmatrix}0\\\\ 1 \ end {bmatrix} = 0. $ $

これは、$ \ket{0}$ と $ \ket{1}$ が直交ベクトルであることを示しています。これは、$ \braket{0 | 1} = \braket{1 | 0} = $0 であることを意味します。  また、definition $ \braket{0 | 0} = \braket{1 | 1} = 1 $ でもあります。これは、2つの計算ベースベクトルを*orthonormal*として呼び出すことができることを意味します。
これらの orthonormal プロパティは、次の例で役に立ちます。 状態が $ \ket{\psi} = {\ frac{3}{5}} \ket{1} + {/frac{4}{5}} \ket{0}$、$ \braket{1 | 0} = $0 であるため、$1 $ が測定される確率は次のようになります。  

$ $ \ big | \braket{1 | \psi}\big | ^ 2 = \ left | \ frac{3}{5}\braket{1 | 1} + \ frac{4}{5}\braket{1 | 0} \ right | ^ 2 = \ frac{9}{25}$ $ 

### <a name="tensor-product-notation"></a>その他の製品表記
Dirac 表記には、その中に、暗黙的な、または製品構造も含まれています。  これは、クォンタムコンピューティングでは、2つの非相関クォンタムレジスタによって記述された状態ベクトルが2つの状態ベクトルの3つの状態ベクトルに含まれるため、重要です。  クォンタムの計算について説明する場合は、その製品構造を簡潔に説明したり、その構造を簡潔に記述したりすることが重要です。  このように、"\ket{\psi}" という構造は、任意の2つのクォンタム状態ベクトル $ \ phi $ と $-psi $ を $ \ket{\phi} $ として書き込み、$ \ket{\psi}/otimes \ket{\phi} $ として明示的に記述することもできます。ただし、慣例では $ otimes $ と記述します。ベクターは不要です。  たとえば、2つの qubits がゼロ状態に初期化された状態は、

$ $ \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}。 otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \ket{0} \otimes \ket{0}= \ket{0} \ket{0}。
$$

同様に、整数 $p $ の state $ \ket{p} $ は、バイナリ表現でエンコードされるクォンタム状態を表します。これは、整数 $p $ です。  たとえば、符号なしのバイナリエンコーディングを使用して数値 $5 $ を表現する場合は、次のように表現することもできます。

$ $ \ket{1}\ket{0}\ket{1} = \ket{101} = \ket{5}。
$$

この記法 $ \ket{0}$ では、1つの-qubit 状態を参照する必要はありませんが、$0 $ のバイナリエンコードを格納する*qubit レジスタ*を参照する必要があります。  これら2つの表記の違いは、通常、コンテキストから明らかになります。  この規則は、次のいずれかの方法で記述できる最初の例を簡略化するために役立ちます。

$ $ \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \ cドット \otimes\begin{bmatrix}1 \\\\ 0 \end{bmatrix} = \ket{0}-otimes \ cドット/otimes \ket{0}= | 0 \ cドット 0 \ \rangle = \ket{0}^ {/otimes n} = \ket{0}。
$$

### <a name="example-describing-superposition-with-dirac-notation"></a>例: Dirac 表記で法則を記述する
Dirac 表記を使用してクォンタムの状態を記述するもう1つの例として、法則の可能性のあるすべてのビット文字列に対して同等のクォンタム状態を記述する次の同等の方法を検討してください $n $

$ $ H ^ {\ otimes n} \ket{0} = \ frac{1}{2 ^ {n/2}} & # {n = 0} ^ {2 ^ n-1} \ket{j} = \ket{+} ^ {/otimes n}。
$$

ここでは、合計が $0 $ から $ 2 ^ {n}-$1 ($n $ bit) になる理由を不思議に思うかもしれません。  まず、$ 2 ^ {n} $ 異なる構成 $n $ bits で使用できることに注意してください。  これは、1つのビットが $2 $ の値を取り、2つのビットが $4 $ の値を受け取ることができることに注目してください。 一般に、これは、$ 2 ^ n $ 異なる可能性のあるビット文字列ですが、$ 1 \ cdots 1 = 2 ^ n-$1 でエンコードされた最大値であるため、合計の上限になります。
この例では、$ \ket{+} ^ {\ otimes n} = \ket{+} $ を $ \ket{0}^ {\ otimes n} = \ket{0}$ と同様に使用しませんでした。この数値表記規約は、通常、すべての qubit が0に初期化された計算ベースの状態用に予約されているためです。  このような規則は、この場合には実用的なものですが、クォンタムコンピューティングの資料には採用されていません。

### <a name="expressing-linearity-with-dirac-notation"></a>Dirac 表記を使用した直線性の表現
Dirac 表記のもう1つの優れた機能は、これが線形であるということです。  4つのクォンタム状態ベクトルに対して書き込みを行う場合は、 

$ $ (\ alpha \ket{\psi} + \beta\ket{\phi}) \ otimes (\ gamma \ket{\chi} + \ delta \ket{\omega}) = \alpha\gamma \ket{\psi}\ket{\chi} + \alpha\delta \ket{\psi}\ket{\omega} + \beta\gamma\ket{\phi}\ket{\chi} + \beta\delta\ket{\phi}\ket{\omega}. $ $

つまり、状態ベクター間での整理された製品の作成が通常の乗算と同じになるように、「Dirac 表記」で、「」という表記を配布することができます。

Bra ベクターは、k ベクターと同様の規則に従います。  たとえば、vector $ \bra{\psi}\bra{\phi} $ は、state vector $ \ psi ^ \ ダガー-otimes/phi ^ \ ダガー = (\psi\otimes/phi) ^ \ ダガー $ と同等です。 K vector $ \ket{\psi} $ が $ \ alpha \ket{0} + \ ベータ \ket{1}$ の場合、ベクターの bra vector バージョンは $ \bra{\psi} = \ket{\psi} ^ \ ダガー = (\bra{0}\ alpha ^ * + \bra{1}\ beta ^ *) $ になります。

例として、州 $ \ket{\psi} = \ frac{3}{5} \ket{1} +-frac{4}{5} \ket{0}$ を測定するためのクォンタムプログラムを使用して、状態を $ \ket{+} $ または $ \ket に測定することを考えてみます。{-}$。 デバイスが出力する確率は、状態が $ \ket{-}$ であることを示します。 

$ $ | \braket{-| \psi} | ^ 2 = \ left | \ frac{1}{\ sqrt{2}} (\bra{0}-\bra{1}) (\ frac{3}{5} \ket{1}) & right | ^ 2 = \ left |-\ frac{4}{5 \ sqrt {5}} +/frac{4}{5 \ sqrt{2}} \ 右 | ^ 2 = \ frac{1}{50}. $ $

確率の計算で負の符号が表示されるのは、クォンタムの干渉の取り組みです。これは、クォンタムコンピューティングが古典的なコンピューティングよりも優れているというメカニズムの1つです。

## <a name="ketbra-or-outer-product"></a>ketbra または外側の製品
Dirac 表記で説明する最後の項目は、 *ketbra*または outer 製品です。  外部製品は、Dirac 表記では $ \ket{\psi} \bra{\phi} $ として表され、bras と kets は brakets と逆の順序で発生するため、ketbras と呼ばれることもあります。  外側の製品は、マトリックス乗算を使用して、クォンタム状態ベクター $ \ psi $ と $ ¥ phi $ の $ \ket{\psi} \bra{\phi} = \ psi \ phi ^ \ ダガー $ として定義されます。  この表記法の最も単純で最も一般的な例を次に示します。

$ $ \ket{0} \bra{0} = \begin{bmatrix}1\\\\ 0 \end{bmatrix}\begin{bmatrix}1 & 0 \end{bmatrix} = \begin{bmatrix}1 & 0\\\\ 0 & 0 \ end {bmatrix} \qquad \ket{1} \bra{1} = \begin{bmatrix}0\\\\ 1 \end{bmatrix}\begin{bmatrix}0 & 1 \end{bmatrix} = \begin{bmatrix}0 & 0\\\\ 0 & 1 \ end {bmatrix}。
$$

Ketbras は、クォンタム状態を固定値に射影するため、多くの場合、プロジェクターと呼ばれます。  これらの操作は、(ベクターの基準を維持するのではなく)、また、クォンタムコンピューターがプロジェクターを確定的に適用できないということではありません。  しかし、プロジェクターは、クォンタムの状態に対して測定されるアクションを記述する美しいジョブを実行します。  たとえば、$ \ket{\psi} $ という状態を $0 $ に測定した場合、状態が測定の結果として得られる変換は次のようになります。

  $ $ \ket{\psi} \rightarrow \frac{(\ket{0} \bra{0}) \ket{\psi}}{| \braket{0 | \psi} |}= \ket{0}、$ $

これは、状態を測定して $ \ket{0}$ として検出した場合に想定します。  繰り返しますが、このようなプロジェクターは、クォンタムコンピューターの状態に対して確定的には適用できません。  その代わりに、$ \ket{0}$ をいくつかの固定確率で示した結果をランダムに適用できます。  このような測定値の確率は、その状態のクォンタムプロジェクターの予測値として記述できます。

$ $ \bra{\psi} (\ket{0} \bra{0}) \ket{\psi} = | \braket{\psi | 0} | ^ 2, $ $

つまり、プロジェクターは測定プロセスを表現する新しい方法を提供しています。

代わりに、マルチ qubit 状態の最初の qubit を $1 $ に測定する場合は、プロジェクターと Dirac 表記を使用して、このプロセスを簡単に記述することもできます。

$ $ P (\ text{first qubit = 1}) = \bra{\psi}\left (\ket{1}\bra{1}{times/bold done ^ {/otimes n-1} \ right) \ket{\psi}.
$$

ここでは、id 行列を Dirac 表記で簡単に記述できます。

$ $ \ \ket ={0} \bra{0}+ \ket{1} \bra{1}= \begin{bmatrix}1 & 0\\\\ 0 & 1 \end{bmatrix}.
$$

2つの場合、プロジェクターは次のように拡張できます。 

$ $ \ket{1} \bra{1}/otimes \ id = \ket{1}\bra{1}/otimes (\ket{0} \bra{0}+ \ket{1} \bra{1}) = \ket{10}\bra{10} + \ket{11}\bra{11}。
$$

これは、列ベクトル表記を使用する multiqubit の likelihoods の測定値についての説明と一致していることがわかります。

$ $ P (\ text1> 最初の qubit = 1}) = \ psi ^ \ ダガー (e\_{10}e\_{10}^ \ ダガー + e\_{11}e\_{11}^-ダガー)-psi = | e\_{10}^-ダガー | ^ 2 + | e\_{11}^ \ダガー | ^ 2、$ $

これは、multi-factor bit の測定に関する議論に一致します。  ただし、この結果をマルチ qubit ケースに汎化することは、列ベクトル表記よりも Dirac 表記法を使用する方が少し単純で、前の処理とまったく同じです。

## <a name="density-operators"></a>密度演算子

Dirac 表記を使用して表すもう1つの便利な演算子は、*密度演算子*です。これは、*状態演算子*とも呼ばれます。
クォンタム状態ベクトルの密度演算子は、$ \rho = \ket{\psi} \bra{\psi} $ という形式になります。
このように、ベクターではなく、マトリックスとして状態を表すこの概念は、確率の計算を表す便利な方法を提供し、1つは統計の不確実性とクォンタムの不確実性の両方を示すことができるため便利です。同じ形式内にあります。
一般的なクォンタム状態の演算子は、ベクターではなく、クォンタムコンピューティングの一部の領域で広く使われていますが、フィールドの基本を理解する必要はありません。
興味のある読者については、「」で提供されている参照資料のいずれ[かを参照](xref:microsoft.quantum.more-information)してください。

## <a name="q-gate-sequences-equivalent-to-quantum-states"></a>"クォンタム" 状態に相当する Q # ゲートシーケンス
クォンタム表記と Q # プログラミング言語については、最後に説明します。このドキュメントでは、クォンタムの状態がクォンタムコンピューティングにおける情報の基本的なオブジェクトであることを説明しました。  その後、Q # では、クォンタム状態の概念がないことが不思議になるかもしれません。  すべての状態は、その準備に使用された操作によってのみ記述されます。  前の例は、このことを示す優れた図解です。  レジスタ内のすべてのクォンタムビット文字列に対して uniform 法則を表現するのではなく、結果を ^ {\ otimes n} \ket{0}$ $H として表すことができます。  これは、その理由をクラシックデプロイことができるという利点だけでなく、アルゴリズムを実装するためにソフトウェアスタックを通じて伝達される必要がある操作を簡潔に定義することもできます。  このため、Q # はクォンタムの状態ではなくゲートシーケンスを生成するように設計されています。ただし、理論的なレベルでは、2つのパースペクティブは同等です。

