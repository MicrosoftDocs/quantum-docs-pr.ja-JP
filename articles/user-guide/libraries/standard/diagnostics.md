---
title: 'Q # 標準ライブラリの診断'
description: 'クォンタムプログラムで間違いやエラーをキャッチするために使用される、Q # 標準ライブラリの診断関数と操作について説明します。'
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 324753cfa1b7d940bf5a0bbe7665f19cc6dda82c
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870636"
---
# <a name="diagnostics"></a>診断 #

従来の開発と同様に、クォンタムプログラムで間違いやエラーを診断できることが重要です。
Q # 標準ライブラリには、「」で詳しく説明されているように、クォンタムプログラムの正確性を確保するためのさまざまな方法が用意されて <xref:microsoft.quantum.guide.testingdebugging> います。
主に、このサポートには、ホストプログラムまたは開発者に追加の診断情報を提供するように対象コンピューターに指示するか、関数または操作の呼び出しで表現される条件と不変性を強制的に適用するための関数と操作の形式が使用されます。

## <a name="machine-diagnostics"></a>コンピューターの診断 ##

典型的な値に関する診断は、関数を使用して、 <xref:microsoft.quantum.intrinsic.message> コンピューターに依存する方法でメッセージをログに記録することによって取得できます。
既定では、文字列がコンソールに書き込まれます。
挿入文字列と共に使用することで、 <xref:microsoft.quantum.intrinsic.message> 従来の値に関する診断情報を簡単にレポートできるようになります。

```Q#
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> `Message`には `(String -> Unit)` 、Q # 内からデバッグログメッセージの出力を確認することはできません。

と呼び出しによって、 <xref:microsoft.quantum.diagnostics.dumpmachine> <xref:microsoft.quantum.diagnostics.dumpregister> ターゲットコンピューターは、現在割り当てられている qubits または特定の qubits のレジスタに関する診断情報をそれぞれ提供するように指示します。
各ターゲットコンピューターは、ダンプ命令への応答として提供される診断情報によって異なります。
たとえば、[完全な状態シミュレーター](xref:microsoft.quantum.machines.full-state-simulator)ターゲットコンピューターは、ホストプログラムに対して、内部で使用されて qubits のレジスタを表す状態ベクターを提供します。
これに対して、 [Toffoli シミュレーター](xref:microsoft.quantum.machines.toffoli-simulator)ターゲットコンピューターは、qubit ごとに1つのクラシックビットを提供します。

 [完全な状態シミュレーターの](xref:microsoft.quantum.machines.full-state-simulator)出力の詳細については `DumpMachine` 、「[テストおよびデバッグ](xref:microsoft.quantum.guide.testingdebugging#dump-functions)」の記事の「ダンプ関数」を参照してください。


## <a name="facts-and-assertions"></a>ファクトとアサーション ##

「[テストおよびデバッグ](xref:microsoft.quantum.guide.testingdebugging)」で説明したように、シグネチャまたはを持つ関数または操作は、 `Unit -> Unit` `Unit => Unit` それぞれ*単体テスト*としてマークできます。
各単体テストは、通常、小さいクォンタムプログラムと、そのプログラムの正確性をチェックする1つ以上の条件で構成されます。
これらの条件は、入力の値を確認する_ファクト_、または入力として渡された1つ以上の qubits の状態をチェックする_アサーション_のいずれかの形式で指定できます。

たとえば、は、 `EqualityFactI(1 + 1, 2, "1 + 1 != 2")` $1 + 1 = $2 という数学的な事実を表しますが、は `AssertQubit(One, qubit)` 測定が確実性を `qubit` 持つを返す条件を表し `One` ます。
前者の場合は、値のみを指定して条件の正確性を確認できます。後者の場合、アサーションを評価するには、qubit の状態に関する情報を把握しておく必要があります。

Q # 標準ライブラリには、次のようなファクトを表すためのさまざまな機能が用意されています。

- <xref:microsoft.quantum.diagnostics.fact>
- <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact>
- <xref:microsoft.quantum.diagnostics.nearequalityfactc>
- <xref:microsoft.quantum.diagnostics.equalityfacti>


### <a name="testing-qubit-states"></a>Qubit 状態のテスト ###

実際には、アサーションは、クォンタム機構の古典シミュレーションが、[複製なしの定理](https://arxiv.org/abs/quant-ph/9607018)に従う必要がないという事実に依存しています。これは、ターゲットマシンにシミュレーターを使用するときに、非物理測定とアサーションを行うことができるようにするためです。
そのため、ハードウェアに展開する前に、古典シミュレーターで個々の操作をテストすることができます。
アサーションの評価が許可されていないターゲットコンピューターでは、の呼び出しは <xref:microsoft.quantum.diagnostics.assertmeasurement> 無視しても安全です。

一般的に、この操作は、指定されたすべての指定された qubits が指定された <xref:microsoft.quantum.diagnostics.assertmeasurement> 結果を常に取得することをアサートします。
アサーションが失敗した場合、指定したメッセージを使用してを呼び出すことにより、実行が終了し `fail` ます。
既定では、この操作は実装されていません。これをサポートするシミュレーターは、ランタイムチェックを実行する実装を提供する必要があります。
`AssertMeasurement`に署名があり `((Pauli[], Qubit[], Result, String) -> ())` ます。
`AssertMeasurement`は、出力の種類として空のタプルを持つ関数であるため、を呼び出すことによる影響 `AssertMeasurement` は、Q # プログラム内では監視できません。

操作関数は、指定された型の指定された <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> qubits を測定することをアサートします。これは、一定の許容範囲内で指定された確率で特定の結果を取得します。
許容範囲は加法です (など `abs(expected-actual) < tol` )。
アサーションが失敗した場合、指定したメッセージを使用してを呼び出すことにより、実行が終了し `fail` ます。
既定では、この操作は実装されていません。これをサポートするシミュレーターは、ランタイムチェックを実行する実装を提供する必要があります。
`AssertMeasurementProbability`に署名があり `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)` ます。 1つ目のパラメーターは、 `Double` 結果の目的の確率を示し、2番目のパラメーターは許容範囲です。

1つの測定値をアサートする以外にも、シミュレーターで使用される古典的な情報を使用して qubit の内部状態を表すことが、コピーに適しているということを使用します。これは、実際にアサーションをテストするために測定を実行する必要がないためです。
具体的には、これにより、実際のハードウェアでは不可能な*互換性*のない測定を行うことができます。

`P : Qubit => Unit`入力が $ \ket $ という状態にあるときに、状態 $ \ket{\psi} $ を準備する操作であるとし {0} ます。
$ \Ket{\psi '} $ を、によって準備された実際の状態にし `P` ます。
$ \Ket{\psi} = \ket{\psi '} $ は、$ \ket{\psi} $ によって記述された軸で $ \ket{\psi '} $ を測定する場合に限り、常にを返し `Zero` ます。
つまり、\begin{align} \ket{\psi} = \ket{\psi '} \ text{if と only} \braket{\psi | \ psi '} = 1 です。
\end{align} 準備で定義されているプリミティブ演算を使用して、 `Zero` $ \ket{\psi} $ がいずれかの Pauli 演算子の eigenstate の場合にを返す測定値を直接実行できます。


この操作 <xref:microsoft.quantum.diagnostics.assertqubit> には、アサーション $ \ket{\psi} = \ket $ をテストする場合に特に便利なショートハンドが用意されて {0} います。
これは一般的に、たとえば、ancilla qubits を $ \ket $ に戻してから解放する場合などです {0} 。
$ \Ket $ に対するアサート {0} は、2つの状態 `P` の準備と操作の両方が `Q` 同じ状態を準備し、サポートする場合にも役立ち `Q` `Adjoint` ます。
特に、

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

ただし、一般に、Pauli オペレーターの eigenstates と一致しない状態に関するアサーションにアクセスできない場合があります。
たとえば、$ \ket{\psi} = (\ket {0} + e ^ {i \ pi/8} \ket {1} )/\ sqrt {2} $ は、pauli 演算子の eigenstate ではなく、を使用して <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> 状態 $ \ket{\psi '} $ が $ \ket{\psi} $ と等しいことを一意に特定することはできません。
代わりに、アサーション $ \ket{\psi '} = \ket{\psi} $ を、シミュレーターでサポートされているプリミティブを使用して直接テストできる仮定に分解する必要があります。
これを行うには、$ \ket{\psi} = \ alpha \ket {0} + \ beta \ket {1} $ に複素数 $-alpha = a \_ r + a \_ i $ and $ \ beta $ を使用します。
この式では、 \{ \_ \_ \_ \_ \} 各複素数を実数部と虚数部の合計として表現できるため、$ a r、a i、b r、b i $ という4つの実数が必要であることに注意してください。
ただし、グローバルフェーズでは $a \_ i = $0 を選択できます。これにより、1つの単 qubit 状態を一意に指定するために必要なのは、3つの実数だけです。

したがって、予想される状態をアサートするために、互いに独立した3つのアサーションを指定する必要があります。
これを行うには、 `Zero` 指定された $-alpha $ および $-beta $ に対して観測する確率を調べ、それぞれを独立してアサートします。
$、$Y $、$z $ be `Result` の値を、それぞれ p$x li $X $、$Y $、および $Z $ の各測定値として使用します。
次に、クォンタム測定の尤度関数を使用して、\begin{align}/pr (x = \texttt{Zero} | \ alpha, \ ベータ) & = \frac12 + a \_ r b \_ r + a \_ i i \_ \\ \\ Pr (y = \texttt{Zero} |-alpha, \ ベータ) & = \frac12 + a \_ r b \_ i-a \_ i b \_ r \\ \\ \ Pr (z = \texttt{Zero} | \ alpha, \ ベータ) & = \frac12\left (1 + a \_ r ^ 2 + a \_ i ^ 2 + b \_ r ^ 2 + b \_ i ^ 2)。
\end{align}

操作は、 <xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> 型の値として $ \ alpha $ と $ \ beta $ の表現を指定して、これらのアサーションを実装し <xref:microsoft.quantum.math.complex> ます。
これは、予想される状態を数学的に計算できる場合に便利です。

### <a name="asserting-equality-of-quantum-operations"></a>クォンタム操作が等しいかどうかをアサートしています ###

これまでに、特定の状態を準備するためのテスト操作について説明しました。
ただし、多くの場合、1つの固定入力ではなく、任意の入力に対して操作がどのように動作するかに注目します。
たとえば、 `U : ((Double, Qubit[]) => () : Adjoint)` $U (t) $ というファミリに対応する演算を実装し、を使用する代わりに明示的なブロックを提供したとし `adjoint` `adjoint auto` ます。
$T $ が進化時間を表している場合は、期待どおりに ^ & $U ^ (t) = U (-t) $ をアサートすることをお勧めします。

これまでに説明した2つの方法で、2つの操作を行い、同じように動作させることができ `U` `V` ます。
まず、で各状態が保持されていることを確認でき `U(target); (Adjoint V)(target);` ます。
2番目の方法として、力 `U(target); (Adjoint V)(target);` のある状態の半分に作用していることを確認して、その entangを維持します。
これらの戦略は、それぞれキャノンの操作とによって実装されてい <xref:microsoft.quantum.diagnostics.assertoperationsequalinplace> <xref:microsoft.quantum.diagnostics.assertoperationsequalreferenced> ます。

> [!NOTE]
> 前述した参照されているアサーションは、 [Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality)に基づいて動作します。このフレームワークでは、$ 2n $ qubits で $n $ qubits に対する操作が関連付けられています。
> 特に、$n $ qubits での id 操作は、ありの州 $ \ket{\ beta_ {00} } \mathrel{: =} (\ket {00} + \ket {11} )/\ sqrt $ の $n $ コピーによって表され {2} ます。
> 操作は、 <xref:microsoft.quantum.preparation.preparechoistate> この isomorphism を実装し、指定された操作を表す状態を準備します。

大まかに言えば、これらの戦略は時間と領域のトレードオフによって区別されます。
各入力状態の反復処理には時間がかかりますが、参照として結び付き使用するには追加の qubits を格納する必要があります。
操作によって、計算ベースの状態の動作だけを対象として、元に戻すことができる従来の操作が実装されている場合は、 <xref:microsoft.quantum.diagnostics.assertoperationsequalinplacecompbasis> この制限付きの入力セットに対して等しいかどうかをテストします。

> [!TIP]
> 入力状態に対する反復処理は、列挙操作およびによって処理され <xref:microsoft.quantum.canon.iteratethroughcartesianproduct> <xref:microsoft.quantum.canon.iteratethroughcartesianpower> ます。
> これらの操作は、通常、2つ以上のセット間でデカルト積の各要素に操作を適用する場合に便利です。

ただし、この2つの方法では、調査中の操作のさまざまなプロパティをテストします。
インプレースアサーションでは各操作が複数回呼び出されるため、各入力状態につき1回、ランダムな選択と測定の結果が呼び出し間で変わる可能性があります。
これに対し、参照されるアサーションは、各操作を1回だけ呼び出します。これにより、操作が1回の*ショットで*等しいことが確認されます。
これらのテストはどちらも、クォンタムプログラムの正確性を確保するために役立ちます。


## <a name="further-reading"></a>もっと読む ##

- <xref:microsoft.quantum.guide.testingdebugging>
- <xref:microsoft.quantum.diagnostics>
