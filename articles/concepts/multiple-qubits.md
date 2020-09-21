---
title: 複数の qubits の説明: 2 つ以上の qubits に対して操作を実行する方法について説明します。
author: bradben uid: benbra: v-ms. date: 12/11/2017 ミリ秒。 topic: article no loc (場所: 記事の場所):
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

# <a name="multiple-qubits"></a>複数の Qubits

シングル qubit ゲートには、特定の時点で複数の状態にする機能など、いくつかのカウンター直感的な機能がありますが、1つのクォンタムコンピューターに存在するものがシングル qubit ゲートの場合は、計算能力を備えたデバイスを使用します。これは、電卓でも古典的な cray で dwarfed ます。
クォンタムコンピューティングの真の力は、qubits の数を増やすと明らかになります。
クォンタムの状態ベクターのベクター空間の次元が、qubits の数で指数関数的に増加するため、この機能は部分的に発生します。
つまり、1つの qubit をモデル化することはできますが、50-qubit クォンタムの計算をシミュレートすると、既存のスーパースーパーの制限が確実にプッシュされます。
1つの追加の qubit だけで計算のサイズを大きくすると、状態を格納するために必要なメモリが *倍増* し、計算時間が約 *2 倍* になります。
このように計算能力が急速に倍増するのは、比較的少数の qubits を使用しているクォンタムコンピューターが、今日の最も強力なスーパースーパーコンピューターと明日のコンピューティングタスクに比べてはるかに長いためです。

クォンタムの状態ベクターに指数的な増加があるのはなぜですか。  このセクションの目的は、シングル qubit 状態からマルチ qubit 状態を構築するために使用されるルールを確認することと、一般的な多対ビットクォンタムコンピュータを形成するためにゲートセットに含める必要があるゲート操作について説明することです。
これらのツールは、コードで一般的に使用されるゲートセットを理解するために必要です Q# 。また、結び付きや干渉などの量子効果が古典のコンピューティングより強力なものである理由についても理解するために必要です。

## <a name="representing-two-qubits"></a>2つの Qubits を表す
2つの状態の間の主な違いは、2つの値が2次元ではなく4次元であることです。
これは、2つの状態の計算基準が、1つの "1 つの" 状態のすべての製品によって形成されているためです。  たとえば、 \begin{align}
00 \equiv \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 1 0 0 0 \end{bmatrix} & = \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} 、 \qquad 01 \equiv \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} = \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \\\\ 0 \end{bmatrix} 、\\\\
10 \equiv \begin{bmatrix} 0 \\\\ 1 1 0 0 0 \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} & = \begin{bmatrix} \\\\ \\\\ 1 \\\\ 0 \end{bmatrix} 、 \qquad 11 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} = \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} 0 0 0 1。
\end{align}

$ $ $ $ この構築を使用して、n qubits のクォンタムの状態がディメンション 2 ^ n の単位ベクトルで表されるのが一般的であることがわかります。  ベクター

$$
\begin{bmatrix}\alpha _ { 00 } 01 \\\\ 10 \alpha   _ { } \\\\ \alpha _ { 11 } \\\\ \alpha   _ { }  \end{bmatrix}
$$

$ | \alpha _ { 00 } | ^ 2 | + \alpha _ { 01 } | ^ 2 + | \alpha _ { 10 } | ^ 2 | + \alpha _ { 11 } | ^ 2 = 1 $ の場合、2つの qubits のクォンタム状態を表します。 1つの qubits の場合と同様に、複数の qubits のクォンタム状態ベクトルには、システムの動作を説明するために必要なすべての情報が格納されます。

2つの独立した qubits があるとします。1つは状態で、もう1つは $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ 状態で2番目の qubits $ \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $ です。    

$$
\begin{bmatrix} \alpha \\\\  \beta \end{bmatrix} \otimes \begin{bmatrix} \gamma \\\\  \delta \end{bmatrix} 
=\begin{bmatrix} \alpha \begin{bmatrix} \gamma \\\\  \delta \end{bmatrix} \\\\ \beta \begin{bmatrix}\gamma \\\\  \delta \end{bmatrix} \end{bmatrix}
= \begin{bmatrix} \alpha\gamma \\\\  \alpha\delta \\\\  \beta\gamma \\\\  \beta\delta \end{bmatrix}, $$

この操作 $ \otimes $ は、ベクターの Kronecker (または製品) と呼ばれます。 2つの single qubit 状態の最新の状態を常に取得し、2つの1つの状態を形成することはできますが、2つの単一 qubit 状態のすべての状態を2つの1つの状態のままにして書き込むことはできません。
たとえば、状態はありません。また、その $ \psi = \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ $ \phi = \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $ 状態が状態であることもあります。     

$$\psi\otimes\phi = \begin{bmatrix}1/ \sqrt { 2 } \\\\ 0 \\\\ 0 \\\\ 1/ \sqrt { 2 } \end{bmatrix} 。$$ 

このような2つの qubit 状態は、シングル qubit 状態の管理されていない製品として記述することはできません。2つの qubits は、 [*あり*](https://en.wikipedia.org/wiki/Quantum_entanglement)であると言います。  疎に言うと、クォンタムの状態は、1つの qubit 状態の状態を維持したものと考えることはできません。そのため、状態が保持する情報は、qubit のいずれかに限定されません。  この情報は、2つの状態の間の相関関係でローカルではなく保存されます。  このような非局所情報は、古典的なコンピューティングに対するクォンタムコンピューティングの主要な特徴の1つであり、クォンタムの電話と[クォンタムのエラー修正](xref:microsoft.quantum.libraries.error-correction)[を含むさまざま](https://github.com/microsoft/Quantum/tree/main/samples/getting-started/teleportation)なクォンタムプロトコルに不可欠です。

## <a name="measuring-two-qubit-states"></a>2つのビット状態の測定 ##
2つのビット状態の測定は、単一の qubit 測定と非常によく似ています。 状態の測定

$$
    \begin{bmatrix}
        \alpha_ { 00 } 01 \\\\ \alpha _ { }\\\\ 
        \alpha_ { 10 } 11 \\\\ \alpha _ {}
    \end{bmatrix}
$$

確率 $ が $ $ | \alpha _ { 00 } | ^ 2、 $ $ 01 $ が $ 確率が 01 ^ 2、10が確率が 10 ^ 2、および確率が 11 ^ 2 である00を生成します。 | \alpha _ { } | $ $ $ $ | \alpha _ { } | $ $ $ $ | \alpha _ { } | $ 変数 $ \alpha _ { 00 } 、 \alpha _ { 01 } 、 \alpha _ { 10 } 、 $ および $ 11 は、この接続を明確にするために意図的に名前が付けられていました。 \alpha _ { } $ 測定の後、結果が00の場合、 $ $ 2 つの qubit システムのクォンタムの状態が折りたたまれ、現在の状態になります。

$$
    モスクワ \equiv
    \begin{bmatrix}
        1 \\\\ 
        0 \\\\ 
        0 \\\\ 
        0 \end{bmatrix} 。
$$

2つの qubit クォンタム状態の1つの qubit だけを測定することもできます。 Qubits の1つだけを測定する場合、測定の影響はわずかに異なります。これは、状態全体が1つのサブシステムにのみ折りたたまれるのではなく、すべての状態が計算ベースの状態に折りたたまれないためです。  言い換えると、1つの qubit だけを測定すると、サブシステムの1つだけが折りたたまれますが、すべてが折りたたまれるわけではありません。  

これを確認するには、次の状態の最初の qubit を測定することを検討し $ ます。これは、 $ 最初に "0" 状態に設定された2つの Qubit に Hadamard transform H を適用することによって形成されます。 $$
H ^ 2 (1 0 1 0) 1 2 1 1 1 1 1 1-1 1-1 1 1-1-1 1-1-1 1-1-1 1-1-1 1 0 0 0 1 1 1 1 1 1 件の { \otimes } \left \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \right = \frac { } { } \begin{bmatrix} & & & \\\\ & & & \\\\ & & & \\\\ & & & \end{bmatrix} \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} = \frac { } { } \begin{bmatrix} 結果 0 1 2 \\\\ \\\\ \\\\ \end{bmatrix} \mapsto \begin{cases} \text { } = & \frac { } { \sqrt { } } \begin{bmatrix} 1 \\\\ 1 0 0 \\\\ \\\\ \end{bmatrix} \\\\ \text { 結果 } = 1 & \frac { 1 } { \sqrt { 2 } } \begin{bmatrix} 0 \\\\ 0 1 1 \\\\ \\\\ \end{bmatrix} \\\\ \end{cases} 。  
$$
どちらの結果も50% の発生確率があります。  どちらの場合も、結果は50% の確率で intuited ことができます。これは、最初の量子状態ベクトルが、 $ $ 最初の $ qubit の0とのスワップで不変であるという事実からです $ 。

最初または2番目の qubit を測定するための数学的規則は単純です。  $E_k $ が $ k ^ { rm 番目の計算ベースのベクトルになるようにし、が } $ $ $ すべての e_k のセットになるようにします。これは、 $ 問題の $ qubit が $ $ その値 k の値1を受け取るようにし $ $ ます。  たとえば、最初の qubit の測定に関心がある場合、 $ $ は $ e_1 \equiv 10 $ と $ e_3 11 で構成され \equiv $ ます。  同様に、2番目の qubit に関心がある場合は、 $ $ $ e_2 \equiv 01 $ と e_3 11 で構成され $ \equiv $ ます。  その後、選択された qubit を1に測定する確率 $ $ は、状態ベクターになります。 $\psi$

$$
P ( \text { 結果 } = 1) = \sum _ { e_k \text { セット } S } \psi ^ \dagger e_k e_k ^ \dagger \psi です。
$$

> [!NOTE]
> このドキュメントでは、リトルエンディアン形式を使用して計算のラベルを付けています。 リトルエンディアンフォーマットでは、最下位ビットが最初に表示されます。 たとえば、リトルエンディアン形式の4番目の数値は、ビット001の文字列で表されます。

各 qubit 測定 $ では0または1のみが生成されるため $ $ $ 、0を測定する確率 $ $ は単に $ 1-P ( \text { 結果 } = 1) になり $ ます。  その理由は、1を測定する確率に対してのみ、式を明示的に指定するためです $ $ 。

このような測定値が状態にあるアクションは、として数学的に表現できます。

$$
\psi\mapsto \frac{\sum_ { e_k \text { セット } S } e_k e_k ^ \dagger \psi } { \sqrt { P ( \text { 結果 } = 1) } } です。
$$

注意リーダーは、測定の確率がゼロの場合に何が起こるかについて心配することがあります。  この場合、結果の状態は技術的に未定義ですが、確率がゼロであるため、このような eventualities について心配する必要はありません。


$ \psi $ 上記の uniform state vector を使用して、最初の qubit の測定に関心がある場合は、 

$$
P ( \text { 最初の qubit 1 の測定値 } = ) = ( \psi ^ \dagger e_1) (e_1 ^ \dagger \psi ) + ( \psi ^ \dagger e_3) (e_3 ^ \dagger \psi ) = | e_1 ^ \dagger \psi | ^ 2 + | e_3 ^ \dagger \psi | ^ 2。
$$

これは、結果10と11を測定するために期待される2つの確率の合計のみであることに注意 $ $ して $ $ ください。
この例では、次のように評価されます。

$$
\frac{1 4 0 0 1 0 1 1 1 1 } { } \left | \begin{bmatrix} & & & \end{bmatrix} \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} \right | ^ 2 + \frac { 1 4 0 0 0 1 1 1 1 1 } { } \left | \begin{bmatrix} & & & \end{bmatrix} \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} \right | ^ 2 = \frac { 1 } { 2 } 。
$$

これは、直感がどのような確率を示すかということに完全に一致します。  同様に、状態はとして書き込むことができます。

$$
\frac{\frac{e_1 } { 2 } + \frac { e_3 } { 2 } } { \sqrt { \frac { 1 } { 2 } } } = \frac { 1 } { \sqrt { 2 } } \begin{bmatrix} 0 \\\\ 0 \\\\ 1 \\\\ 1\end{bmatrix}
$$

ここでも、直感に従っています。

## <a name="two-qubit-operations"></a>2つの Qubit 操作
シングル qubit の場合と同様に、すべてのユニタリ変換は、qubit で有効な操作です。 一般に、 $ n qubits での $ 長さの変換は、 $ サイズ 2 ^ n $ $ \times 2 ^ n $ (サイズ 2 ^ n のベクトルで動作するように、 $ $ $ u ^ { -1 } = u ^ \dagger $ ) のマトリックス U です。
たとえば、CNOT (制御された) ゲートは、一般的に使用される2つの qubit ゲートであり、次のような種類の表で表されています。

$$
\operatorname{CNOT 1 \ 0 \ 0 \ 0 0 \ 1 \ 0 \ 0 0 \ 0 \ 0 \ } = \begin{bmatrix}  \\\\ \\\\  1 \\\\  0 \ 0 \ 1 \ 0 \end{bmatrix}
$$

両方の qubit にシングル qubit ゲートを適用して、2つの qubit ゲートを形成することもできます。 たとえば、ゲートを適用する場合は、 

$$
\begin{bmatrix}
a \ b \\\\ c \ d \end{bmatrix}
$$

and

$$\begin{bmatrix}
e \ f \\\\ g \ h \end{bmatrix}
$$

1番目と2番目の qubits に対して、これは、次のようになります。 $$\begin{bmatrix}
a \ b \\\\ c \ d \end{bmatrix}
\otimes 
\begin{bmatrix}
e \ f \\\\ g \ h \end{bmatrix}=
    \begin{bmatrix}
    ae \ af \ bf \\\\
    ag \ ah \ bg \ bh \\\\
    ce \ cf \ de \ df \\\\
    cg \ ch \ dg \ dh \end{bmatrix} 。$$
そのため、いくつかの既知のシングル qubit ゲートの最新の製品を利用して、2つの qubit ゲートを形成できます。 2つの qubit ゲートの例 $ とし \otimes $ て、h h、 $ x \otimes \boldone $ 、および $ x Z があり \otimes $ ます。

いずれの2つのシングル qubit ゲートでも2つのビットゲートが定義されていますが、その場合は、元の状態のままであることに注意してください。 すべての2つのビットゲートが、シングル qubit ゲートの全製品として書き込まれるとは限りません。  このようなゲートは、 *entangling* ゲートと呼ばれます。 Entangling ゲートの一例として、CNOT gate が挙げられます。

制御されていないゲートの背後にある直感は、任意のゲートに汎用化できます。  一般に、制御されたゲートは、特定の qubit が1の場合を除き、id として機能するゲートです (ie にはアクションがありません) $ $ 。  ここでは、制御されたユニタリを示します。この例では、x というラベルが付いた $ x $ $ \Lambda \_ (U) を使用し $ ます。  例として、 $ \Lambda 0 (u) e \_ { 1 } \otimes { \psi } = e \_ { 1 } \otimes U { \psi } $ と $ \Lambda \_ 0 (u) e \_ { 0 } \otimes { \psi } = e \_ { 0 です } \otimes { \psi } $ 。ここで、 $ e \_ 0 $ と $ e \_ 1 $ は、値 $ 0 および1に対応する1つの qubit の計算ベースのベクトルです $ $ $ 。  たとえば、次のような制御された $ z ゲートを考えてみます。 $$$
\Lambda\_0 (Z) 1 0 0 0 0 1 0 0 0 1 0 0 0 0 = \begin{bmatrix} & & & \\\\ & & & \\\\ & & & \\\\ & & & -1 \end{bmatrix} = ( \boldone \otimes h) \operatorname { cnot } ( \boldone \otimes h)。
$$

制御された unitaries 効率的な方法で構築することは、大きな課題です。  これを実装する最も簡単な方法は、基本的なゲートの制御されたバージョンのデータベースを形成し、元のすべての位置合わせ操作のすべての基本ゲートを、制御される対応するに置き換えることです。  多くの場合、これはかなり無駄であり、巧妙な洞察を使用して、いくつかのゲートを制御されたバージョンに置き換えるだけで、同じ影響を得ることができます。  このため、最適化された手作業でチューニングされたバージョンがわかっている場合は、ユーザーが制御されたバージョンのユニタリを定義できるようにするための、単純な方法をフレームワークに提供します。

また、典型的情報を使用してゲートを制御することもできます。  たとえば、クラシックデプロイで制御されていないゲートゲートは、単なる通常のゲートではありませんが、古典ビットが $ クォンタムビットではなく1である場合にのみ適用され $ ます。  この意味では、クラシックデプロイ制御ゲートは、コードの1つの分岐でのみゲートが適用されるように、クォンタムコード内の if ステートメントと考えることができます。


Single qubit の場合と同様に、2つの qubit ゲートセットは、 $ \times $ このセットから任意の有効桁数になるゲートの製品によって近似される 4 4 つのすべての粒度行列を持つことができます。
ユニバーサルゲートセットの一例として、Hadamard ゲート、T ゲート、CNOT gate があります。 これらのゲートの製品を作成することによって、2つの qubits 上のすべてのユニタリ行列を概算することができます。

## <a name="many-qubit-systems"></a>多対ビットシステム
ここでは、2つのビットケースで調査したのとまったく同じパターンに従って、小規模なシステムから多数の qubit クォンタムの状態を構築します。  このような状態は、より小さい状態の製品を作成することによって構築されます。  たとえば、 $ クォンタムコンピューターにビット文字列1011001をエンコードすることを検討してください $ 。  これを次のようにエンコードできます。

$$
1011001 \equiv \begin{bmatrix} 0 \\\\ 1 1 \end{bmatrix} \otimes \begin{bmatrix} \\\\ 0 0 \end{bmatrix} \otimes \begin{bmatrix} \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 1 1 0 \end{bmatrix} \otimes \begin{bmatrix} \\\\ 1 0 \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} 。
$$

クォンタムゲートは、まったく同じ方法で動作します。  たとえば、 $ $ 最初の qubit に X ゲートを適用し、2番目と3番目の qubit の間で cnot を実行する場合、この変換は次のように表現することができます。

\begin{align}
&(X \otimes \operatorname { cnot } _ { 12 } \otimes \boldone \otimes \boldone \otimes \boldone \otimes \boldone ) \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ 0 1 0 1 1 0 1 0 0 1\end{bmatrix}\\\\
&\qquad\qquad\equiv 0011001。 \end{align}

多くの qubit システムでは、多くの場合、クォンタムコンピューターの一時的なメモリとして機能する qubit を割り当てたり、割り当てを解除したりする必要があります。  このような qubit は ancilla と呼ばれます。  既定では、qubit 状態は割り当て時に e_0 に初期化されると仮定し $ $ ます。  また、割り当てを解除する前に e_0 するために再び返されると想定 $ $ しています。  この想定は重要です。そのため、ancilla qubit が割り当て解除されたときに別の qubit レジスタを使用すると、割り当て解除のプロセスによって ancilla が破損する可能性があります。  このため、このような qubits は解放される前に初期状態に戻されると常に想定されています。

最後に、2つの qubit クォンタムコンピューターに対してユニバーサルクォンタムコンピューティングを実現するために、ゲートセットに新しいゲートを追加する必要がありましたが、マルチ qubit ケースでは新しいゲートを導入する必要はありません。  ゲート $ H $ 、T、cnot は、多くの $ $ qubits に対して設定されたユニバーサルゲートを形成しません。これは、一般的なすべてのデータ長変換を、一連の2つの qubits 回転に分割できるためです。  次に、2つのビットケースに対して開発された理論を活用し、多くの qubit があるときに、ここでもう一度使用します。

これまでに使用してきた線形代数表記は、マルチ qubit の状態を示すために使用されていますが、状態のサイズを大きくするにつれて煩雑になる傾向があります。  たとえば、長さ7ビット文字列の結果として得られる列ベクトルは $ 128 $ 次元で、前に説明した表記法を使用して表現されます。  このため、次に、このような高次元ベクターを簡潔に記述できるように、クォンタムコンピューティングに共通の表記を示しています。
