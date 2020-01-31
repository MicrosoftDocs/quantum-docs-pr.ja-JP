---
title: 'Q # 標準ライブラリ-diagnostics |Microsoft Docs'
description: 'Q # 標準ライブラリ-診断'
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 67ec6780d8cbbda7223d46026a9df97cebc92b33
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820982"
---
# <a name="diagnostics"></a>Diagnostics #

従来の開発と同様に、クォンタムプログラムで間違いやエラーを診断できることが重要です。
Q # 標準ライブラリには、<xref:microsoft.quantum.techniques.testing-and-debugging>で詳しく説明されているように、クォンタムプログラムの正確性を確保するためのさまざまな方法が用意されています。
ほとんどの場合、このサポートには、ホストプログラムまたは開発者に追加の診断情報を提供するように対象コンピューターに指示する関数と操作の形式、または条件とインバリアントの正確性を強制的に適用する機能が含まれます。関数または操作の呼び出しによって。

## <a name="machine-diagnostics"></a>コンピューターの診断 ##

<xref:microsoft.quantum.intrinsic.message> 関数を使用して、コンピューターに依存する方法でメッセージをログに記録することにより、従来の値に関する診断を取得できます。
既定では、文字列がコンソールに書き込まれます。
<xref:microsoft.quantum.intrinsic.message> 補間文字列と共に使用することで、従来の値に関する診断情報を簡単にレポートできるようになります。

```Q#
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> `Message` にはシグネチャ `(String -> Unit)`があります。これに対して、Q # 内からデバッグログメッセージを出力することはできません。

<xref:microsoft.quantum.diagnostics.dumpmachine> と <xref:microsoft.quantum.diagnostics.dumpregister> 呼び出しによって、ターゲットマシンは、現在割り当てられている qubits の診断情報、または特定の qubits のレジスタに関する診断情報を提供するように指示します。
各ターゲットコンピューターは、ダンプ命令への応答として提供される診断情報によって異なります。
たとえば、[完全な状態シミュレーター](xref:microsoft.quantum.machines.full-state-simulator)ターゲットコンピューターは、ホストプログラムに対して、内部で使用されて qubits のレジスタを表す状態ベクターを提供します。
これに対して、 [Toffoli シミュレーター](xref:microsoft.quantum.machines.toffoli-simulator)ターゲットコンピューターは、qubit ごとに1つのクラシックビットを提供します。

 [完全な状態シミュレーターの](xref:microsoft.quantum.machines.full-state-simulator)`DumpMachine` 出力の詳細については、「[テストおよびデバッグ](xref:microsoft.quantum.techniques.testing-and-debugging#dump-functions)」の記事の「ダンプ関数」を参照してください。


## <a name="facts-and-assertions"></a>ファクトとアサーション ##

「[テストおよびデバッグ](xref:microsoft.quantum.techniques.testing-and-debugging)」で説明したように、シグネチャ `Unit -> Unit` または `Unit => Unit`を持つ関数または操作は、それぞれ*単体テスト*としてマークできます。
各単体テストは、通常、小さいクォンタムプログラムと、そのプログラムの正確性をチェックする1つ以上の条件で構成されます。
これらの条件は、入力の値を確認する_ファクト_、または入力として渡された1つ以上の qubits の状態をチェックする_アサーション_のいずれかの形式で指定できます。

たとえば、`EqualityFactI(1 + 1, 2, "1 + 1 != 2")` は $1 + 1 = $2 の算術事実を表し、`AssertQubit(One, qubit)` は `qubit` を測定して `One` を正確に返す条件を表します。
前者の場合は、値のみを指定して条件の正確性を確認できます。後者の場合、アサーションを評価するには、qubit の状態に関する情報を把握しておく必要があります。

Q # 標準ライブラリには、次のようなファクトを表すためのさまざまな機能が用意されています。

- <xref:microsoft.quantum.diagnostics.fact>
- <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact>
- <xref:microsoft.quantum.diagnostics.nearequalityfactc>
- <xref:microsoft.quantum.diagnostics.equalityfacti>


### <a name="testing-qubit-states"></a>Qubit 状態のテスト ###

実際には、アサーションは、クォンタム機構の古典シミュレーションが、[複製なしの定理](https://arxiv.org/abs/quant-ph/9607018)に従う必要がないという事実に依存しています。これは、ターゲットマシンにシミュレーターを使用するときに、非物理測定とアサーションを行うことができるようにするためです。
そのため、ハードウェアに展開する前に、古典シミュレーターで個々の操作をテストすることができます。
アサーションの評価が許可されていないターゲットコンピューターでは、<xref:microsoft.quantum.intrinsic.assert> の呼び出しを無視してもかまいません。

一般に、<xref:microsoft.quantum.intrinsic.assert> 操作では、指定された演算子の指定された qubits を測定すると、常に指定された結果が得られます。
アサーションが失敗した場合、指定したメッセージを使用して `fail` を呼び出すことにより、実行が終了します。
既定では、この操作は実装されていません。これをサポートするシミュレーターは、ランタイムチェックを実行する実装を提供する必要があります。
`Assert` に署名 `((Pauli[], Qubit[], Result, String) -> ())`があります。
`Assert` は出力型として空のタプルを持つ関数なので、`Assert` を呼び出しても、Q # プログラム内で監視できます。

<xref:microsoft.quantum.intrinsic.assertprob> operation 関数は、指定された型の指定された qubits を測定することをアサートします。これは、ある程度の許容範囲内で、指定された確率で特定の結果が得られます。
許容範囲は加法です (例: `abs(expected-actual) < tol`)。
アサーションが失敗した場合、指定したメッセージを使用して `fail` を呼び出すことにより、実行が終了します。
既定では、この操作は実装されていません。これをサポートするシミュレーターは、ランタイムチェックを実行する実装を提供する必要があります。
`AssertProb` に署名 `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)`があります。 最初の `Double` パラメーターは、結果の確率を指定し、2つ目のパラメーターは許容範囲を示します。

1つの測定値をアサートする以外にも、シミュレーターで使用される古典的な情報を使用して qubit の内部状態を表すことが、コピーに適しているということを使用します。これは、実際にアサーションをテストするために測定を実行する必要がないためです。
具体的には、これにより、実際のハードウェアでは不可能な*互換性*のない測定を行うことができます。

`P : Qubit => Unit` は、入力が $ \ket{0}$ の状態にあるときに、状態 $ \ket{\psi} $ を準備する操作であるとします。
$ \Ket{\psi '} $ を `P`によって準備された実際の状態にします。
次に、$ \ket{\psi} = \ket{\psi '} $ は、$ \ket{\psi} $ によって表される軸で $ \ket{\psi '} $ を測定する場合に常に `Zero`を返します。
つまり、\begin{align} \ket{\psi} = \ket{\psi '} \ text{if と only} \braket{\psi | \ psi '} = 1 です。
\end{align} 準備で定義されているプリミティブ演算を使用して、$ \ket{\psi} $ がいずれかの p Li 演算子の eigenstate である場合は、`Zero` を返す測定値を直接実行できます。


操作 <xref:microsoft.quantum.diagnostics.assertqubit> には、アサーション $ \ket{\psi} = \ket{0}$ をテストする場合に特に便利なショートハンドが用意されています。
これは一般的に、たとえば、ancilla qubits を $ \ket{0}$ に戻してから解放する場合などです。
$ \Ket{0}$ に対してアサートすることは、2つの状態準備 `P` と `Q` 操作の両方で同じ状態を準備し、`Q` が `Adjoint`をサポートする場合にも役立ちます。
特に、

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

ただし、一般に、Pauli オペレーターの eigenstates と一致しない状態に関するアサーションにアクセスできない場合があります。
たとえば、$ \ket{\psi} = (\ket{0} + e ^ {i \ pi/8} \ket{1})/\ sqrt{2}$ は、Pauli 演算子の eigenstate ではなく、<xref:microsoft.quantum.intrinsic.assertprob> を使用して、状態 $ \ket{\psi '} $ が $ \ket{\psi} $ と等しいことを一意に特定することはできません。
代わりに、アサーション $ \ket{\psi '} = \ket{\psi} $ を、シミュレーターでサポートされているプリミティブを使用して直接テストできる仮定に分解する必要があります。
これを行うには、$ \ket{\psi} = \ alpha \ket{0} + \ ベータ \ket{1}$ for complex number $-alpha = a\_r + a\_i i $ and $ \ beta $ とします。
この式では、各複素数を実数部と虚数部の合計として表すことができるため、\_r、a\_i、b\_r、b\_i\}$ という4つの\{実数が必要であることに注意してください。
ただし、グローバルフェーズにより、$a\_i = $0 を選択できます。このような場合、1つの単 qubit 状態を一意に指定するために必要なのは3つの実数だけです。

したがって、予想される状態をアサートするために、互いに独立した3つのアサーションを指定する必要があります。
これを行うには、指定された $-alpha $ および $-beta $ に対して `Zero` を観察する確率を調べ、それぞれを独立してアサートします。
$、$Y $、および $z $ を $x して、それぞれ P# li $X $、$Y $、および $Z $ の測定値を `Result` します。
次に、クォンタム測定に対して尤度関数を使用して、\begin{align} \ Pr (x = \texttt{Zero} | \ alpha, \ ベータ) & = \frac12 + a\_r b\_r + a\_i b\_i \\\\ (y = \texttt{Zero} | \ アルファ) \ ベータ) & = \frac12 + a\_r b\_i-a\_i b\_r \\\\ \ Pr (z = \texttt{Zero} | \ alpha, \ ベータ) & = \frac12\left (1 + a\_r ^ 2 + a\_i ^ 2 + b\_r ^ 2 + b\_i ^ 2 \ 右)。
\end{align}

<xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> 操作では、型 <xref:microsoft.quantum.math.complex>の値として $ \ alpha $ と $ \ beta $ の表現を指定して、これらのアサーションを実装します。
これは、予想される状態を数学的に計算できる場合に便利です。

### <a name="asserting-equality-of-quantum-operations"></a>クォンタム操作が等しいかどうかをアサートしています ###

これまでに、特定の状態を準備するためのテスト操作について説明しました。
ただし、多くの場合、1つの固定入力ではなく、任意の入力に対して操作がどのように動作するかに注目します。
たとえば、`adjoint auto`を使用するのではなく、$U (t) $ という一連の `adjoint` に対応する操作 `U : ((Double, Qubit[]) => () : Adjoint)` が実装されているとします。
$T $ が進化時間を表している場合は、期待どおりに ^ & $U ^ (t) = U (-t) $ をアサートすることをお勧めします。

これまでに説明した2つの方法では、2つの操作 `U` し、`V` 動作を同じにすることができます。
まず、`U(target); (Adjoint V)(target);` が各状態を一定の単位で保持していることを確認します。
2番目の方法として、ありがある状態の半分に `U(target); (Adjoint V)(target);` 動作することを確認できます。
これらの戦略は、それぞれキャノンの操作 <xref:microsoft.quantum.diagnostics.assertoperationsequalinplace> と <xref:microsoft.quantum.diagnostics.assertoperationsequalreferenced>によって実装されています。

> [!NOTE]
> 前述した参照されているアサーションは、 [Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality)に基づいて動作します。このフレームワークでは、$ 2n $ qubits で $n $ qubits に対する操作が関連付けられています。
> 特に、$n $ qubits での id 操作は、あり状態 $ \ket{\ beta_{00}} \mathrel{: =} (\ket{00} + \ket{11})//sqrt{2}$ の $n $ コピーによって表されます。
> 操作 <xref:microsoft.quantum.preparation.preparechoistate> は、この isomorphism を実装し、指定された操作を表す状態を準備します。

大まかに言えば、これらの戦略は時間と領域のトレードオフによって区別されます。
各入力状態の反復処理には時間がかかりますが、参照として結び付き使用するには追加の qubits を格納する必要があります。
操作によって、計算ベースの状態の動作のみを目的として、元に戻すことができる従来の操作が実装されている場合、<xref:microsoft.quantum.diagnostics.assertoperationsequalinplacecompbasis> は、この制限された一連の入力で等しいかどうかをテストします。

> [!TIP]
> 入力状態に対する反復処理は、列挙操作 <xref:microsoft.quantum.canon.iteratethroughcartesianproduct> および <xref:microsoft.quantum.canon.iteratethroughcartesianpower>によって処理されます。
> これらの操作は、通常、2つ以上のセット間でデカルト積の各要素に操作を適用する場合に便利です。

ただし、この2つの方法では、調査中の操作のさまざまなプロパティをテストします。
インプレースアサーションでは各操作が複数回呼び出されるため、各入力状態につき1回、ランダムな選択と測定の結果が呼び出し間で変わる可能性があります。
これに対し、参照されるアサーションは、各操作を1回だけ呼び出します。これにより、操作が1回の*ショットで*等しいことが確認されます。
これらのテストはどちらも、クォンタムプログラムの正確性を確保するために役立ちます。


## <a name="further-reading"></a>参考情報 ##

- <xref:microsoft.quantum.techniques.testing-and-debugging>
- <xref:microsoft.quantum.diagnostics>
