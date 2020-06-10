---
title: 複数の量子ビット
description: 2つ以上の qubits に対して操作を実行する方法について説明します。
author: QuantumWriter
uid: microsoft.quantum.concepts.multiple-qubits
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
ms.openlocfilehash: 224bd5165f508f6cd1fdb85fb5c14ba2e23e59ea
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630377"
---
# <a name="multiple-qubits"></a>複数の Qubits

シングル qubit ゲートには、特定の時点で複数の状態にする機能など、いくつかのカウンター直感的な機能がありますが、1つのクォンタムコンピューターに存在するものがシングル qubit ゲートの場合は、計算能力を備えたデバイスを使用します。これは、電卓でも古典的な cray で dwarfed ます。
クォンタムコンピューティングの真の力は、qubits の数を増やすと明らかになります。
クォンタムの状態ベクターのベクター空間の次元が、qubits の数で指数関数的に増加するため、この機能は部分的に発生します。
つまり、1つの qubit をモデル化することはできますが、50-qubit クォンタムの計算をシミュレートすると、既存のスーパースーパーの制限が確実にプッシュされます。
1つの追加の qubit だけで計算のサイズを大きくすると、状態を格納するために必要なメモリが*倍増*し、計算時間が約*2 倍*になります。
このように計算能力が急速に倍増するのは、比較的少数の qubits を使用しているクォンタムコンピューターが、今日の最も強力なスーパースーパーコンピューターと明日のコンピューティングタスクに比べてはるかに長いためです。

クォンタムの状態ベクターに指数的な増加があるのはなぜですか。  このセクションの目的は、シングル qubit 状態からマルチ qubit 状態を構築するために使用されるルールを確認することと、一般的な多対ビットクォンタムコンピュータを形成するためにゲートセットに含める必要があるゲート操作について説明することです。
これらのツールは、Q # コードでよく使用されるゲートセットを理解するために必要です。また、結び付きや干渉などの量子効果が古典のコンピューティングより強力なものである理由についても理解するために必要です。

## <a name="representing-two-qubits"></a>2つの Qubits を表す
2つの状態の間の主な違いは、2つの値が2次元ではなく4次元であることです。
これは、2つの状態の計算基準が、1つの "1 つの" 状態のすべての製品によって形成されているためです。  たとえば、次のように配置します。}
00 \equiv \ begin{ bmatrix } 1 \\ \\ 0 & end{ bmatrix } \ otimes \ begin{ bmatrix } 1 \\ \\ 0 \ end{ bmatrix } &= \ begin{ bmatrix } 1 0 0 & \\ \\ \\\\ \\\\ end{ bmatrix } , \qquad 01 \equiv/begin{ bmatrix } 1 \\ \\ 0 & end{ bmatrix } /otimes & begin{} bmatrix 0 \\ \\ 1 \ end{ bmatrix } = \ begin{ bmatrix } 0 1 & end{ \\ \\ \\\\ \\\\ bmatrix } , \\ \\ 10 \equiv & begin{ bmatrix } 0 \\ \\ 1 & end{ bmatrix } \ otimes \ begin{ bmatrix } 1 \\ \\ 0 \ end{ bmatrix } &= \ begin{ bmatrix } 0 \\ \\ 0 \\\\ 1% \\\\ end{ bmatrix } , \qquad 11 \equiv/begin{ bmatrix } 0 \\ \\ 1 & end{} 0 0 bmatrix } bmatrix \\ \\ bmatrix } bmatrix \\ \\ \\\\ 0 0 \\\\ 1 \ end{ bmatrix } ですが、このようになります。
& end{align}

$ $ この構築を使用して、$n qubits のクォンタム状態がディメンション $ 2 ^ n の単位ベクトルで表されることがよくわかります。  ベクター

$ $ \ begin{ bmatrix } \ alpha_ {00 } \\ \\ \ alpha_ {01 } \\ \\ \ alpha_ {10 } \\ \\ \ alpha_ {11 \ } end{bmatrix}
$$

2つの qubits のクォンタム状態を表します ($ | \ alpha_ {00 } | ^ 2 + | \ alpha_ {01 } | ^ 2 + | \ alpha_ {10 | ^ 2 + | \ } alpha_ {11 } | ^ 2 = 1) $ 。 1つの qubits の場合と同様に、複数の qubits のクォンタム状態ベクトルには、システムの動作を説明するために必要なすべての情報が格納されます。

2つの独立した qubits が指定されている場合、1つは状態 $、begin{- bmatrix } alpha \ beta \ \\ \\ end{ bmatrix } $、2番目の qubits が state $ & begin{ bmatrix } \ gamma \\ \\ \ delta \ end{ bmatrix } $ となります。

$ $ & begin{- bmatrix } α \\ \\ \ ベータ bmatrix } bmatrix } \\ \\ \ & # {-& #-& #}bmatrix} 
= \ begin{ bmatrix } \ alpha \ begin{\ bmatrix } gamma \\ \\ bmatrix } \\ \\ bmatrix } \\ \\ bmatrix } \-& # 0; & # {-ガンマ \ デルタ \ end{& end{bmatrix}
= \ begin{- bmatrix } alpha \gamma \\ \\ \ α \ \delta \\ \\ ベータ \ ベータ \ & # \gamma \\ \\ \delta { bmatrix } , $ $

操作 $ otimes $ は、ベクターの Kronecker (または製品) と呼ばれます。 2つの single qubit 状態の最新の状態を常に取得し、2つの1つの状態を形成することはできますが、2つの単一 qubit 状態のすべての状態を2つの1つの状態のままにして書き込むことはできません。
たとえば、状態が $-psi = \ begin{-alpha- bmatrix } \\ \\ beta/end{ bmatrix } $ および $-phi/begin{-gamma {\ の場合、 = bmatrix } \\ \\ bmatrix } その状態は、状態であるため、 

$ $ \ psi \otimes \ phi = \ begin{ bmatrix } 1/\ sqrt {2 } \\ \\ 0 \\ \\ 0 \\ \\ 1/\ sqrt {2 } \ end{ bmatrix } . $ $ 

このような2つの qubit 状態は、シングル qubit 状態の管理されていない製品として記述することはできません。2つの qubits は、[*あり*](https://en.wikipedia.org/wiki/Quantum_entanglement)であると言います。  疎に言うと、クォンタムの状態は、1つの qubit 状態の状態を維持したものと考えることはできません。そのため、状態が保持する情報は、qubit のいずれかに限定されません。  この情報は、2つの状態の間の相関関係でローカルではなく保存されます。  このような非局所情報は、古典的なコンピューティングに対するクォンタムコンピューティングの主要な特徴の1つであり、クォンタムの電話と[クォンタムのエラー修正](xref:microsoft.quantum.libraries.error-correction)[を含むさまざま](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/teleportation)なクォンタムプロトコルに不可欠です。

## <a name="measuring-two-qubit-states"></a>2つのビット状態の測定 ##
2つのビット状態の測定は、単一の qubit 測定と非常によく似ています。 状態の測定

$ $ \ begin{bmatrix}
        \ alpha_ {00 } \\ \\ \ alpha_ {01 } \\ \\ \ alpha_ {10 } \\ \\ \ alpha_ {11}
    エンドbmatrix}
$$

確率が $ | \ $ alpha_ {00 | ^ 2、$1 が確率が $ | \ } $ $ alpha_ {01 | ^ 2、$10 が確率が $ } $ $ | \ alpha_ {10 } | ^ 2 $ 、$11 が $ 確率が $ | \ alpha_ {11 } | ^ 2 $ である $0 を使用して、を生成します。 変数 $ \ alpha_ {00 } , \ alpha_ {01 } , \ alpha_ {10 } , $ および $ \ alpha_ {11 $ は、 } この接続を明確にするために意図的に名前が付けられました。 測定の後、結果が $0 の場合、 $ 2 つの qubit システムのクォンタムの状態が折りたたまれ、現在の状態になります。

$ $0 \equivbmatrix}
        1 0 0 0 \\ \\ \\ \\ \\ \\ \ end{ bmatrix } .
$$

2つの qubit クォンタム状態の1つの qubit だけを測定することもできます。 Qubits の1つだけを測定する場合、測定の影響はわずかに異なります。これは、状態全体が1つのサブシステムにのみ折りたたまれるのではなく、すべての状態が計算ベースの状態に折りたたまれないためです。  言い換えると、1つの qubit だけを測定すると、サブシステムの1つだけが折りたたまれますが、すべてが折りたたまれるわけではありません。  

これを確認するには、次の状態の最初の qubit を測定することを検討します。これは、最初に "0" 状態に設定された2つの qubit の Hadamard transform $H を適用することによって形成され $ ます。 $ $ H ^ {\ otimes 2 } \ left (\ begin{ bmatrix } 1 \\ \\ 0/end{/ bmatrix } otimes \ begin{ bmatrix } 1 \\ \\ 0 \ end{ bmatrix } \ right) = \frac{1 } {2 & } begin{ bmatrix } 1 & 1 & 1 & 1 \\ \\ 1 &-1 & 1 &-1 \\ \\ 1 & 1 &-1 &-1 \\ \\ 1 &-1 &-1 & 1 & end{/ bmatrix } begin{ bmatrix } 1 0 0 0 \\\\ \\\\ \\\\ \end { bmatrix } = \frac{1 } {2 & } begin{ bmatrix } 1 1 1 1 1 \\\\ \\\\ \\\\ \end { bmatrix } \ map\frac{1 } } = 0 & } {\ sqrt{2}/beginになります。 } { bmatrix } 1 \\\\ 1 \\\\ 0 0% \\\\ end{ bmatrix } \\ \\ \ \frac{1} = 1 & } {\ sqrt{2 } } \ begin{ bmatrix } 0 \\\\ 0 \\\\ 1 1 & \\\\ end{} bmatrix } \\ \\ ケース } 。
$ $ 両方の結果が50% の確率で発生しています。  2つの結果を50% の確率で intuited ことができます。これは、最初の量子状態ベクトルが、最初の qubit の $0 と $1 をスワップした状態で不変であるという事実です $ $ 。

最初または2番目の qubit を測定するための数学的規則は単純です。  $E を $ $k ^ {\ rm th } $ 計算ベースのベクターに _k して、問題の $ $ qubit が $e の値に対して値 $1 を受け取るように、すべての _k $k のセットにすることを許可 $S し $ $ ます。  たとえば、最初の qubit の測定に関心がある場合、$S $ は $e _1 \equiv 10 $ および $e 3 11 で構成 \equiv さ $ れます。  同様に、2番目の qubit $S に関心がある場合、 $ $e _2 \equiv 01 $ と $e 3 \equiv 11 で構成され $ ます。  その後、選択された qubit を $1 に測定する確率 $ は、state vector $ \ psi$

$ $ P (\ text{結果 } = 1) = \ sum_ {e_k \ { 、Set} S- } psi ^ \ ダガー e_k e_k ^ \ ダガー \psi.
$$

> [!NOTE]
> このドキュメントでは、リトルエンディアン形式を使用して計算のラベルを付けています。 リトルエンディアンフォーマットでは、最下位ビットが最初に表示されます。 たとえば、リトルエンディアン形式の4番目の数値は、ビット001の文字列で表されます。

各 qubit 測定 $ では $0 または $1 のみが生成 $ されるため、$0 を測定する確率 $ は単に $1-P (\ text{結果 } = 1) $ となります。  これは、$1 を測定する確率の式のみを明示的に指定するためです $ 。

このような測定値が状態にあるアクションは、として数学的に表現できます。

$ $ \ psi \ mapo { \ sum_ {e_k \ { Set} S のテキスト } e_k e_k ^ \ ダガー \ psi } {\ sqrt{P (\ text{結果 } = 1)}}
$$

注意リーダーは、測定の確率がゼロの場合に何が起こるかについて心配することがあります。  この場合、結果の状態は技術的に未定義ですが、確率がゼロであるため、このような eventualities について心配する必要はありません。


$前に示した uniform state vector に $-psi を設定し、最初の qubit の測定に関心がある場合は、 

$ $ P (最初の qubit } = 1) = (\ psi ^-ダガー e_1) (e_1 ^-ダガー/psi) + (-psi e_3 e_3 ^-ダガー) = | e_1 ^-ダガー-psi | ^ 2 + | e_3 ^ \ ダガー/psi ^ 2 です (& t) | 。
$$

これは、結果 $10 と $11 を測定するために期待される2つの確率の合計のみであることに注意 $ $ してください。
この例では、次のように評価されます。

$ $ \frac{1 } {4 } \ 左 | \ begin{ bmatrix } 0&0&1&0 \end {\ bmatrix } begin{ bmatrix } 1 1 1 1 \\\\ \\\\ \\\\ \end { bmatrix } \ 右 | ^ 2 + \frac{1 } {4, } left | \ begin{ bmatrix } 0&0&0&1 \end {/ bmatrix } begin{ bmatrix } 1 1 1 1 \\\\ \\\\ \\\\ \end { bmatrix } \ 右 | ^ 2 = \frac{1 } {2 } .
$$

これは、直感がどのような確率を示すかということに完全に一致します。  同様に、状態はとして書き込むことができます。

$ $ \ frac { \frac{e_1 } {2 } + \frac{e_3 { } 2 } } {\ sqrt { \frac{1 } {2 } }} = \frac{1 } {\ sqrt{2 } } \ begin{ bmatrix } 0 \\\\ 0 \\\\ 1 \\\\ 1 \end {bmatrix}
$$

ここでも、直感に従っています。

## <a name="two-qubit-operations"></a>2つの Qubit 操作
シングル qubit の場合と同様に、すべてのユニタリ変換は、qubit で有効な操作です。 一般に、$n qubits でのユニタリ変換は、 $ サイズが $ $ 2 ^ n/times 2 ^ n (サイズが $ 2 ^ n) のマトリックス $U であり、 $ $ $U ^ {-1 } = U ^-ダガーのようになり $ ます。
たとえば、CNOT (制御された) ゲートは、一般的に使用される2つの qubit ゲートであり、次のような種類の表で表されています。

$ $ \ オペレーター名 {cnot } = \ begin{1 \ 0 \ 0 \ 0 0 \ 1 \ 0 \ 0 0 \ 0 \ 0 \ 1 0 \ 0 \ bmatrix } \\ \\ 1 \ 0 & \\ \\ \\ \\ end{bmatrix}
$$

両方の qubit にシングル qubit ゲートを適用して、2つの qubit ゲートを形成することもできます。 たとえば、ゲートを適用する場合は、 

$ $ \ begin{bmatrix}
a \ b \\\\ c \ d \ end{bmatrix}
$$

および

$ $ \ begin{bmatrix}
e \ f \\\\ g \ h \ end{bmatrix}
$$

1番目と2番目の qubits に対して、これは、次のようになります。 $ $ & begin{bmatrix}
a \ b \\\\ c \ d \ end{bmatrix}
\ otimes \ begin{bmatrix}
e \ f \\\\ g \ h \ end{ bmatrix } = \ begin{bmatrix}
    ae \ af \ "\\ bf \\ \\ ag \ ah \ bg \" を \\ \\ \\ \\ bmatrix } "にして、" 2 "の2つのビットゲートを形成することができます。これは、既知のシングル qubit ゲートの最新機能を使用して、2つの qubit ゲートを形成できるようにすることです。 2つの qubit ゲートの例としては、$H/otimes H $ 、$X/times $ /bold done、$X/Otimes Z などがあり $ ます。

いずれの2つのシングル qubit ゲートでも2つのビットゲートが定義されていますが、その場合は、元の状態のままであることに注意してください。 すべての2つのビットゲートが、シングル qubit ゲートの全製品として書き込まれるとは限りません。  このようなゲートは、 *entangling*ゲートと呼ばれます。 Entangling ゲートの一例として、CNOT gate が挙げられます。

制御されていないゲートの背後にある直感は、任意のゲートに汎用化できます。  一般に、制御されたゲートは、特定の qubit が $1 の場合を除き、id として機能するゲートです (ie にはアクションがありません) $ 。  ここでは、制御されたユニタリを示します。この例では、$x ラベルが付けられた qubit で制御さ $ れ、$-ラムダ \_ x (U) $ を使用します。  例として、$ \ Lambda_0 (U) e {1/otimes \_ } {-psi } = e \_ {1 } /otimes U { } /psi $ and $-ラムダ \_ 0 (u) e {0/otimes \_ } { } /psi = e \_ {0 } /otimes { } /psi $, ここで $e \_ 0 $ と $e \_ 1 は、 $ 値 $0 と $1 に対応する1つの qubit の計算ベースのベクトルです $ $ 。  たとえば、次のようになります。次の制御された $Z ゲートについて考えてみましょう $ 。 $ $ \ ラムダ \_ 0 (Z) = \ begin{ bmatrix } 1&0&0&0 0&1&0&0 0&0 \\ \\ \\ \\&1&0 \\ \\ 0&0&0 & -1、end{ bmatrix } = (-bold \otimes } \otimes done h)。
$$

制御された unitaries 効率的な方法で構築することは、大きな課題です。  これを実装する最も簡単な方法は、基本的なゲートの制御されたバージョンのデータベースを形成し、元のすべての位置合わせ操作のすべての基本ゲートを、制御される対応するに置き換えることです。  多くの場合、これはかなり無駄であり、巧妙な洞察を使用して、いくつかのゲートを制御されたバージョンに置き換えるだけで、同じ影響を得ることができます。  このため、最適化された手作業でチューニングされたバージョンがわかっている場合は、ユーザーが制御されたバージョンのユニタリを定義できるようにするための、単純な方法をフレームワークに提供します。

また、典型的情報を使用してゲートを制御することもできます。  たとえば、クラシックデプロイで制御されないゲートゲートは、単なる通常のゲートではありませんが、古典ビットが量子ビットではなく $1 である場合にのみ適用され $ ます。  この意味では、クラシックデプロイ制御ゲートは、コードの1つの分岐でのみゲートが適用されるように、クォンタムコード内の if ステートメントと考えることができます。


シングル qubit の場合と同様に、2つの qubit ゲートセットは、 \times $ このセットから任意の有効桁数になるゲートの製品によって、$4 4 つのすべてのインの行列を近似する場合にユニバーサルになります。
ユニバーサルゲートセットの一例として、Hadamard ゲート、T ゲート、CNOT gate があります。 これらのゲートの製品を作成することによって、2つの qubits 上のすべてのユニタリ行列を概算することができます。

## <a name="many-qubit-systems"></a>多対ビットシステム
ここでは、2つのビットケースで調査したのとまったく同じパターンに従って、小規模なシステムから多数の qubit クォンタムの状態を構築します。  このような状態は、より小さい状態の製品を作成することによって構築されます。  たとえば、クォンタムコンピューターにビット文字列 $1011001 をエンコードすることを検討してください $ 。  これを次のようにエンコードできます。

$ $1011001 \equiv \ begin{ bmatrix } 0 \\ \\ 1 & end{\ bmatrix } otimes \ begin{ bmatrix } 1 & \\ \\ bmatrix } bmatrix } \\ \\ bmatrix } bmatrix } \\ \\ bmatrix } bmatrix } \\ \\ bmatrix } bmatrix } \\ \\ bmatrix } bmatrix } \\ \\ bmatrix } end{{/otimes \ begin{0 1 & end{/otimes \ begin{0 1 & end{/otimes \ begin{1 0 & end{/otimes & begin{0 1 & end{..
$$

クォンタムゲートは、まったく同じ方法で動作します。  たとえば、 $ 最初の qubit に $X ゲートを適用し、2番目と3番目の qubit の間で CNOT を実行する場合は、この変換を次のように表現することができます。

& i)}
& (X/otimes \operatorname{CNOT}_{12] \ (& o) \ (& o) \ (& o) \ ole times \ (& o) \ @ times \ (& o) \ begin{1 & end{/otimes \ begin{1 0 \ end{/otimes \ begin{ } \otimes bmatrix } \\ \\ bmatrix } bmatrix } \\ \\ bmatrix } bmatrix } 0 \\ \\ 1 & end{/otimes-begin{1 bmatrix \qquad; } bmatrix } \\ \\ bmatrix } bmatrix } \\ \\ bmatrix } bmatrix } \\ \\ bmatrix } bmatrix } \\ \\ bmatrix } \\ \\ \qquad \equiv & end{/otimes & begin{1 0 \ end{/otimes & begin{0 1 \ end{& 0011001. (otimes)。
& end{align}

多くの qubit システムでは、多くの場合、クォンタムコンピューターの一時的なメモリとして機能する qubit を割り当てたり、割り当てを解除したりする必要があります。  このような qubit は ancilla と呼ばれます。  既定では、割り当て時に qubit 状態が 0 $e に初期化されるとし $ ます。  また、解放の前に0を $e するために再び返されると想定 $ しています。  この想定は重要です。そのため、ancilla qubit が割り当て解除されたときに別の qubit レジスタを使用すると、割り当て解除のプロセスによって ancilla が破損する可能性があります。  このため、このような qubits は解放される前に初期状態に戻されると常に想定されています。

最後に、2つの qubit クォンタムコンピューターに対してユニバーサルクォンタムコンピューティングを実現するために、ゲートセットに新しいゲートを追加する必要がありましたが、マルチ qubit ケースでは新しいゲートを導入する必要はありません。  ゲート $H $ 、$T、 $ および cnot は、多数の qubits に対して設定されたユニバーサルゲートを形成しません。これは、一般的なすべてのデータ長変換を、一連の2つの qubits 回転に分割できるためです。  次に、2つのビットケースに対して開発された理論を活用し、多くの qubit があるときに、ここでもう一度使用します。

これまでに使用してきた線形代数表記は、マルチ qubit の状態を示すために使用されていますが、状態のサイズを大きくするにつれて煩雑になる傾向があります。  たとえば、長さ7ビット文字列の結果として得られる列ベクトルは $128 $ 次元で、前に説明した表記法を使用して表現されます。  このため、次に、このような高次元ベクターを簡潔に記述できるように、クォンタムコンピューティングに共通の表記を示しています。
