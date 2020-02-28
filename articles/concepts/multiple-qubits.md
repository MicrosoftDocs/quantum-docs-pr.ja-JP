---
title: 複数の量子ビット
description: 2つ以上の qubits に対して操作を実行する方法について説明します。
author: QuantumWriter
uid: microsoft.quantum.concepts.multiple-qubits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 2fa227c823cd87df9c799c043c699e4ce818b8e3
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907547"
---
# <a name="multiple-qubits"></a>複数の Qubits

シングル qubit ゲートには、特定の時点で複数の状態にする機能など、いくつかのカウンター直感的な機能がありますが、1つのクォンタムコンピューターに存在するものがシングル qubit ゲートの場合は、コンピューティング能力を備えたデバイスを dwarfed電卓でも、従来の cray を使用することができます。
クォンタムコンピューティングの真の力は、qubits の数を増やすと明らかになります。
クォンタムの状態ベクターのベクター空間の次元が、qubits の数で指数関数的に増加するため、この機能は部分的に発生します。
つまり、1つの qubit をモデル化することはできますが、50-qubit クォンタムの計算をシミュレートすると、既存のスーパースーパーの制限が確実にプッシュされます。
1つの追加の qubit だけで計算のサイズを大きくすると、状態を格納するために必要なメモリが*倍増*し、計算時間が約*2 倍*になります。
このように計算能力が急速に倍増するのは、比較的少数の qubits を使用しているクォンタムコンピューターが、今日の最も強力なスーパースーパーコンピューターと明日のコンピューティングタスクに比べてはるかに長いためです。

クォンタムの状態ベクターに指数的な増加があるのはなぜですか。  このセクションの目的は、シングル qubit 状態からマルチ qubit 状態を構築するために使用されるルールを確認することと、一般的な多対ビットクォンタムコンピュータを形成するためにゲートセットに含める必要があるゲート操作について説明することです。
これらのツールは、Q # コードでよく使用されるゲートセットを理解するために必要です。また、結び付きや干渉などの量子効果が古典のコンピューティングより強力なものである理由についても理解するために必要です。

## <a name="representing-two-qubits"></a>2つの Qubits を表す
2つの状態の間の主な違いは、2つの値が2次元ではなく4次元であることです。
これは、2つの状態の計算基準が、1つの "1 つの" 状態のすべての製品によって形成されているためです。  たとえば、\begin{align} 00 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix}1 \\\\ 0\\\\ 0\\\\ 0 \end{bmatrix}、\qquad 01 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \begin{bmatrix}0 \\\\ 1\\\\ 0\\\\ 0 \end{bmatrix}、\\\\ 10 \equiv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} & \\\begin{bmatrix}0 \\\\0 \\\\1 \\ \\0 \end{bmatrix}、\qquad 11 \equiv \begin{bmatrix}0 \\ \\1 \end{bmatrix}\otimes \begin{bmatrix}0 \\ \\1 \end{bmatrix} = \begin{bmatrix}0 \\\\0 \\ @no__ 0t_40_ \\ 1 \end{bmatrix}.\\
\end{align}

この構築を使用して、$n $ qubits のクォンタムの状態がディメンション $ 2 ^ n $ の単位ベクトルで表されることがよくわかります。  ベクター

$ $ \begin{bmatrix} \ alpha_{00} \\\\ \ alpha_{01} \\\\ \ alpha_{10} \\\\ \ alpha_{11} \end{bmatrix} $ $

2つの qubits のクォンタム状態を表します ($ | \ alpha_{00}| ^ 2 + | \ alpha_{01}| ^ 2 + | \ alpha_{10}| ^ 2 + | \ alpha_{11}| ^ 2 = 1 $)。 1つの qubits の場合と同様に、複数の qubits のクォンタム状態ベクトルには、システムの動作を説明するために必要なすべての情報が格納されます。

2つの独立した qubits が指定されている場合、1つは状態 $ \begin{bmatrix} \ alpha \\\\ \ ベータ \end{bmatrix} $、2番目の qubits が state $ \begin{bmatrix} \ gamma \\\\ \ delta \end{bmatrix} $

$ $ \begin{bmatrix}-alpha \\\\ \ ベータ \end{bmatrix} \begin{bmatrix} \ \\\\-delta \end{bmatrix} = \begin{bmatrix}-alpha \begin{bmatrix}-gamma \\\\ \end{bmatrix} \begin{bmatrix}\gamma \end{bmatrix} \\\\ \end{bmatrix} \begin{bmatrix} \\\\ \alpha\gamma \\\\ \alpha\delta \\\\ \beta\gamma \beta\delta を \\して \\ \end{bmatrix}, $$

操作 $ otimes $ は、ベクターの Kronecker (または製品) と呼ばれます。 2つの single qubit 状態の最新の状態を常に取得し、2つの1つの状態を形成することはできますが、2つの単一 qubit 状態のすべての状態を2つの1つの状態のままにして書き込むことはできません。
たとえば、状態が $ \ psi = \begin{bmatrix}-alpha \\\\ \ ベータ \end{bmatrix} $ および $ \ phi = \begin{bmatrix}/gamma \\\\-delta \end{bmatrix} $ ではなく、その状態は 

$ $ \psi\otimes \ phi = \begin{bmatrix} 1/\ sqrt{2} \\\\ 0 \\\\ 0 \\\\ 1/\ sqrt{2} \end{bmatrix}. $ $ 

このような2つの qubit 状態は、シングル qubit 状態の管理されていない製品として記述することはできません。2つの qubits は、[*あり*](https://en.wikipedia.org/wiki/Quantum_entanglement)であると言います。  疎に言うと、クォンタムの状態は、1つの qubit 状態の状態を維持したものと考えることはできません。そのため、状態が保持する情報は、qubit のいずれかに限定されません。  この情報は、2つの状態の間の相関関係でローカルではなく保存されます。  このような非局所情報は、古典的なコンピューティングに対するクォンタムコンピューティングの主要な特徴の1つであり、クォンタムの電話と[クォンタムのエラー修正](xref:microsoft.quantum.libraries.error-correction)[を含むさまざま](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/teleportation)なクォンタムプロトコルに不可欠です。

## <a name="measuring-two-qubit-states"></a>2つのビット状態の測定 ##
2つのビット状態の測定は、単一の qubit 測定と非常によく似ています。 状態の測定

$ $ \begin{bmatrix} \ alpha_{00} \\\\ \ alpha_{01} \\\\ \ alpha_{10} \\\\ \ alpha_{11} \end{bmatrix} $ $

確率 $ | \ alpha_{00}| ^ $2、$1 $ (確率 $ | \ alpha_{01}| ^ $2、$10 $ (確率 $ | \ alpha_{10}| ^ $2、$11 $ と確率 $ | \ alpha_{11}| ^ $2) を使用して $0 $ を生成します。 変数 $ \ alpha_{00}、\ alpha_{01}、\ alpha_{10}、$、$ \ alpha_{11}$ は、この接続を明確にするために意図的に名前が付けられました。 測定の後、結果が $0 $ の場合、2つの qubit システムのクォンタムの状態が折りたたまれ、現在の状態になります。

$ $0 \equiv \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix}.
$$

2つの qubit クォンタム状態の1つの qubit だけを測定することもできます。 Qubits の1つだけを測定する場合、測定の影響はわずかに異なります。これは、状態全体が1つのサブシステムにのみ折りたたまれるのではなく、すべての状態が計算ベースの状態に折りたたまれないためです。  言い換えると、1つの qubit だけを測定すると、サブシステムの1つだけが折りたたまれますが、すべてが折りたたまれるわけではありません。  

これを確認するには、次の状態の最初の qubit を測定することを検討します。これは、Hadamard 変換を適用することによって形成されます。これは、最初に "0" 状態に設定される2つの qubit の $H $ です。 $ $ H ^ {\ otimes 2} \ left (\begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix}) = \ frac{1}{2}\begin{bmatrix}1 & 1 & 1 & 1 \\\\ 1 & 1 & 1 &-1 \\\\ 1 & 1 &-1 &-1 \\\\ 1 &-1 &-1 & 1 \end{bmatrix}\begin{bmatrix}1\\\\ 0\\\\ 0\\\\ 0 \ 終了 {bmatrix} = \ frac{1}{2}\begin{bmatrix}1\\\\ 1\\\\ 1\\\\ 1 \ 終了 {bmatrix} \ map\end{bmatrix} \begin{cases}\text{outcome} = 0 &{1}1{2}\\0 \\\\0 \\\\ \ \begin{bmatrix}0} = 1 & \end{cases}.{1}{\ sqrt{2}}\\\\ 0\\\\ 1\\\\ 1 \end{bmatrix}\\\\\\\\\\
$ $ 両方の結果が50% の確率で発生しています。  両方に対して50% の確率の結果を intuited にすることができます。これは、最初の量子状態ベクトルが、最初の qubit の $0 $ と $1 $ のスワップで不変であるという事実です。

最初または2番目の qubit を測定するための数学的規則は単純です。  _K $ を $k ^ {\ rm th} $ の計算ベースベクターに $e する場合は $S $ を $e $ の値に $1 $ として指定します。これにより、は _k $ の値に $ の値を取ります。  たとえば、最初の qubit の測定に関心がある場合、$S $ は $e _2 \ http-equiv $10 と $e http-equiv $11 で構成されます。  同様に、2番目の qubit $S に関心がある場合、$ は $e _1 \ http-equiv $1 および $e 3 \equiv $11 で構成されます。  次に、選択した qubit を $1 $ に測定する確率を、state vector $ \ psi $ に対して指定します。

$ $ P (\text{outcome} = 1) = \ sum_ {e_k \ text{in set} S} \ psi ^ \ ダガー e_k e_k ^、ダガー \psi.
$$

各 qubit 測定では $0 $ または $1 $ のみが生成されるため、$0 $ を測定する確率は単に $1-P (\text{outcome} = 1) $ となります。  これは、$1 $ を測定する確率の式のみを明示的に指定するためです。

このような測定値が状態にあるアクションは、として数学的に表現できます。

$ $ \ psi \ map\frac{\ sum_ {e_k \ text{in set} S} e_k e_k ^ \psi}{\sqrt{P (\text{outcome} = 1)}}。
$$

注意リーダーは、測定の確率がゼロの場合に何が起こるかについて心配することがあります。  この場合、結果の状態は技術的に未定義ですが、確率がゼロであるため、このような eventualities について心配する必要はありません。


前に示した uniform state vector に $-psi $ を使用して、最初の qubit の測定に関心がある場合は、 

$ $ P (-最初の qubit} = 1) = (\ psi ^ \ ダガー e_2) (e_2 ^-ダガー/psi) + (-psi e_3 e_3 ^-ダガー) = | e_2 ^-ダガー/psi | ^ 2 + | e_3 ^/ダガー | ^ 2 の値を持ちます。
$$

これは、結果を測定するために期待される2つの確率の合計のみであることに注意してください $10 $ と $11 $ は、測定されるすべての qubits でした。
この例では、次のように評価されます。

$ $ \ frac{1}{4}\ 左 | \begin{bmatrix}0 & 0 & 1 & 0 \ 終了 {bmatrix} \ 開始 {bmatrix} 1\\\\ 1\\\\ 1\\\\ 1 \ 終了 {bmatrix} \ right | ^ 2 +-frac{1}{4}\ 左 | \begin{bmatrix}0 & 0 & 0 & 1 \ 終了 {bmatrix} \ 開始 {bmatrix} 1\\\\ 1\\\\ 1\\\\ 1 \ end {bmatrix} \ right | ^ 2 = \ frac{1}{2}します。
$$

これは、直感がどのような確率を示すかということに完全に一致します。  同様に、状態はとして書き込むことができます。

$ $ \frac{\frac{e_2}{2}+ \frac{e_3}{2}} {\ sqrt{\ frac{1}{2}}} = \ frac{1}{\ sqrt{2}} \begin{bmatrix} 0\\\\ 0\\\\ 1\\\\ 1 \ end {bmatrix} $ $

ここでも、直感に従っています。

## <a name="two-qubit-operations"></a>2つの Qubit 操作
シングル qubit の場合と同様に、すべてのユニタリ変換は、qubit で有効な操作です。 一般に、$n $ qubits では、{-1} のサイズが $ 2 ^ n \ times 2 ^ n $ (サイズが $ 2 ^ n $ のベクトルで動作するように、$ 2 ^ n \ $U) の $U $ n $ となります。 たとえば、CNOT (制御された) ゲートは、一般的に使用される2つの qubit ゲートであり、次のような種類の表で表されています。

$ $ \ オペレーター名 {cnot} = \begin{bmatrix} 1 \ 0 \ 0 \ 0 \\\\ 0 \ 1 \ 0 \ 0 \\\\ 0 \ 0 \ 0 \ 1 \\\\ 0 \ 0 \ 1 \ 0 \end{bmatrix} $ $

両方の qubit にシングル qubit ゲートを適用して、2つの qubit ゲートを形成することもできます。 たとえば、ゲートを適用する場合は、 

$ $ \begin{bmatrix} a \ b\\\\ c \ d \end{bmatrix} $ $

and

$ $ \begin{bmatrix} e \ f\\\\ g \ h \end{bmatrix} $ $

1番目と2番目の qubits に対して、これは、次のようになります。 $ $ \begin{bmatrix} a \ b\\\\ c \ d \end{bmatrix}/otimes \begin{bmatrix} e \ f\\\\ g \ h \end{bmatrix} = \begin{bmatrix} ae \ af \ a \ bf \\\\ ag \ ah \ bg \ bh \\\\ ce \ cf \ de \ df \\\\ cg \ ch \ dg \ dh \end{bmatrix}. $ $ であるため、既知のシングル qubits ゲートの最新の製品を使用して2つの qubits ゲートを形成できます。 2つの qubit ゲートの例としては、H $、$X-otimes、$H $、$X/otimes Z $ などがあります。

いずれの2つのシングル qubit ゲートでも2つのビットゲートが定義されていますが、その場合は、元の状態のままであることに注意してください。 すべての2つのビットゲートが、シングル qubit ゲートの全製品として書き込まれるとは限りません。  このようなゲートは、 *entangling*ゲートと呼ばれます。 Entangling ゲートの一例として、CNOT gate が挙げられます。

制御されていないゲートの背後にある直感は、任意のゲートに汎用化できます。  一般に、制御されたゲートは、特定の qubit が $1 $ の場合を除き、id として機能するゲートです (ie にはアクションがありません)。  ここでは、制御されたユニタリを示します。この例では、$-ラムダ\_x (U) $ を使用して $x $ というラベルが付いた qubit に制御されます。  例として、$ \ Lambda_0 (U) e\_{1}-otimes {\psi} = e\_{1}/otimes U {\psi} $ and $-ラムダ\_0 (U) e\_{0}/otimes {\psi} = e\_{0}\otimes{\psi} $, ここで $e\_$0 と $e\_$1 は、$0 $ と $1 $ の値に対応する1つの qubit の計算ベースのベクトルです。  たとえば、次の制御された $Z $ gate を考えてみます。 $ $-ラムダ\_0 (Z) = \begin{bmatrix}1 & 0 & 0 & 0\\\\0 & 1 & 0 & 0\\\\0 & 0 & 1 & 0\\\\0 & 0 & 0 &-1 \end{bmatrix} = (\ bold one/otimes H) \ 演算子名 {cnot} (\ bold one/otimes H)。
$$

制御された unitaries 効率的な方法で構築することは、大きな課題です。  これを実装する最も簡単な方法は、基本的なゲートの制御されたバージョンのデータベースを形成し、元のすべての位置合わせ操作のすべての基本ゲートを、制御される対応するに置き換えることです。  多くの場合、これはかなり無駄であり、巧妙な洞察を使用して、いくつかのゲートを制御されたバージョンに置き換えるだけで、同じ影響を得ることができます。  このため、最適化された手作業でチューニングされたバージョンがわかっている場合は、ユーザーが制御されたバージョンのユニタリを定義できるようにするための、単純な方法をフレームワークに提供します。

また、典型的情報を使用してゲートを制御することもできます。  たとえば、クラシックデプロイで制御されないゲートゲートは、単なる通常のゲートではありませんが、古典ビットが量子ビットではなく $1 $ の場合にのみ適用されます。  この意味では、クラシックデプロイ制御ゲートは、コードの1つの分岐でのみゲートが適用されるように、クォンタムコード内の if ステートメントと考えることができます。


シングル qubit の場合と同様に、2つの qubit ゲートセットは、このセットから任意の有効桁数になるゲートの製品によって近似されている $ 4 \ times $4 のすべてのイン-の場合に、ユニバーサルになります。
ユニバーサルゲートセットの一例として、Hadamard ゲート、T ゲート、CNOT gate があります。 これらのゲートの製品を作成することによって、2つの qubits 上のすべてのユニタリ行列を概算することができます。

## <a name="many-qubit-systems"></a>多対ビットシステム
ここでは、2つのビットケースで調査したのとまったく同じパターンに従って、小規模なシステムから多数の qubit クォンタムの状態を構築します。  このような状態は、より小さい状態の製品を作成することによって構築されます。  たとえば、クォンタムコンピューターにビット文字列 $1011001 $ をエンコードすることを検討してください。  これを次のようにエンコードできます。

$ $1011001 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}/otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}.
$$

クォンタムゲートは、まったく同じ方法で動作します。  たとえば、最初の qubit に $X $ gate を適用し、2番目と3番目の qubit の間で CNOT を実行する場合は、この変換を次のように表現することができます。

\begin{align} & (& o) (X/otimes >{12}/otimes \、{times \、{times \)-{times \ bold}/ole times/bold 完了 \ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}/otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes\begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\\\\ & \qquad\qquad\equiv 0011001。
\end{align}

多くの qubit システムでは、多くの場合、クォンタムコンピューターの一時的なメモリとして機能する qubit を割り当てたり、割り当てを解除したりする必要があります。  このような qubit は ancilla と呼ばれます。  既定では、割り当て時に qubit 状態が 0 $ $e に初期化されるとします。  また、割り当てを解除する前に、0 $ $e に再び返されると想定しています。  Ancilla qubit が割り当て解除されるときに別の qubit レジスタを使用すると、割り当て解除のプロセスによって ancilla が破損するため、この想定が重要になります。  このため、このような qubits は解放される前に初期状態に戻されると常に想定されています。

最後に、2つの qubit クォンタムコンピューターに対してユニバーサルクォンタムコンピューティングを実現するために、ゲートセットに新しいゲートを追加する必要がありましたが、マルチ qubit ケースでは新しいゲートを導入する必要はありません。  ゲート $H $, $T $ と CNOT は、多数の qubits に対して設定されたユニバーサルゲートを形成しません。これは、一般的なすべての種類の区切り変換を、一連の2つの qubits 回転に分割できるためです。  次に、2つのビットケースに対して開発された理論を活用し、多くの qubit があるときに、ここでもう一度使用します。

これまでに使用してきた線形代数表記は、マルチ qubit の状態を示すために使用されていますが、状態のサイズを大きくするにつれて煩雑になる傾向があります。  たとえば、長さ7ビット文字列の結果の列ベクトルは $128 $ 次元で、前述した表記法を使用して表現されます。  このため、次に、このような高次元ベクターを簡潔に記述できるように、クォンタムコンピューティングに共通の表記を示しています。
