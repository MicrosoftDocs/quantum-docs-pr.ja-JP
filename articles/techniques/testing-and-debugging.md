---
title: Q# プログラムのテストとデバッグ
description: 単体テスト、ファクトとアサーション、およびダンプ関数を使用してクォンタム プログラムをテストおよびデバッグする方法について説明します。
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: caf15b7273b7efed1da87a2edd62c06cd4357593
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030584"
---
# <a name="testing-and-debugging"></a>テストとデバッグ

古典プログラミングと同様に、量子プログラムが意図したとおりに機能することを確認し、間違った量子プログラムを診断できることが不可欠です。
このセクションでは、クォンタム プログラムのテストとデバッグに関する Q# のツールについて説明します。

## <a name="unit-tests"></a>単体テスト

古典的なプログラムをテストする一般的なアプローチの 1 つは、ライブラリでコードを実行し、その出力を予想される出力と比較する*単体テスト*と呼ばれる小さなプログラムを作成することです。
たとえば、2^2 = 4$`4`という*事前設定*を知っているので、`Square(2)`必ず返すことを確認できます。

Q# は、クォンタム プログラムの単体テストの作成をサポートしており[、xUnit](https://xunit.github.io/)単体テスト フレームワーク内でテストとして実行できます。

### <a name="creating-a-test-project"></a>テスト プロジェクトの作成

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Visual Studio 2019 を開きます。 メニューに`File`移動し、`New` > `Project...`を選択します。
右上隅で を検索`Q#`し、テンプレートを選択します。 `Q# Test Project`

#### <a name="command-line--visual-studio-code"></a>[コマンドライン/Visual Studio Code](#tab/tabid-vscode)

好みのコマンド ラインから、次のコマンドを実行します。
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

新しいプロジェクトには単一のファイル`Tests.qs`が含まれます。
最初にこのファイルには、新しく`AllocateQubit`割り当てられた qubit が $\ket{0}$ 状態であることを確認し、メッセージを出力する 1 つのサンプル単体テストが含まれています。

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

:new: 型`Unit`の引数を受け取り、戻り値`Unit`を持つ Q# の操作または`@Test("...")`関数は、属性を使用して単体テストとしてマークできます。 上記の属性の引数は`"QuantumSimulator"`、テストが実行されるターゲットを指定します。 複数のターゲットに対して 1 つのテストを実行できます。 たとえば、上`@Test("ResourcesEstimator")``AllocateQubit`に属性を追加します。 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
ファイルを保存し、すべてのテストを実行します。 次に、2 つの単体テストが必要です。 

Q# コンパイラは、組み込みのターゲット "QuantumSimulator"、"トフォリシミュレータ"、および "リソース推定子" を単体テストの有効な実行ターゲットとして認識します。 また、任意の完全修飾名を指定して、カスタム実行ターゲットを定義することもできます。 

### <a name="running-q-unit-tests"></a>Q# 単体テストの実行

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

ソリューションごとの 1 回限りのセットアップとして、メニューに`Test`移動し、`Test Settings` > `Default Processor Architecture` > `X64`を選択します。

> [!TIP]
> Visual Studio の既定のプロセッサ アーキテクチャ設定は、ソリューションごとに`.suo`ソリューション オプション ( ) ファイルに格納されます。
> このファイルを削除した場合は、プロセッサ アーキテクチャとして`X64`再度選択する必要があります。

プロジェクトをビルドし、メニューに`Test`移動して`Windows` > `Test Explorer`を選択します。 `AllocateQubit`グループ内のテストのリストに表示されます`Not Run Tests`。 この`Run All`個々のテストを選択または実行すると、合格するはずです!

#### <a name="command-line--visual-studio-code"></a>[コマンドライン/Visual Studio Code](#tab/tabid-vscode)

テストを実行するには、プロジェクト フォルダー (含まれている`Tests.csproj`フォルダー) に移動し、コマンドを実行します。

```bash
$ dotnet restore
$ dotnet test
```

次のような出力が表示されます。

```
Build started, please wait...
Build completed.

Test run for C:\Users\chgranad.REDMOND\tmp\Tests\bin\Debug\netcoreapp2.0\Tests.dll(.NETCoreApp,Version=v2.0)
Microsoft (R) Test Execution Command Line Tool Version 15.3.0-preview-20170628-02
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.5864002]   Discovering: Tests
[xUnit.net 00:00:00.7073844]   Discovered:  Tests
[xUnit.net 00:00:00.7453826]   Starting:    Tests
[xUnit.net 00:00:00.9590439]   Finished:    Tests

Total tests: 1. Passed: 1. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.9607 Seconds
```

単体テストは、名前や実行ターゲットに従ってフィルター処理できます。

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

組み込<xref:microsoft.quantum.intrinsic.message>み関数`(String -> Unit)`は型を持ち、診断メッセージの作成を可能にします。

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

テスト エクスプローラーでテストを実行し、テストをクリックすると、テスト実行に関する情報がパネルに表示されます: 成功/失敗状態、経過時間、および 「出力」リンク。 「出力」リンクをクリックすると、テスト出力が新しいウィンドウで開きます。

![テスト出力](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[コマンドライン/Visual Studio Code](#tab/tabid-vscode)

各テストの合格/不合格ステータスは、 によって`dotnet test`コンソールに出力されます。
失敗したテストの場合、失敗の診断に役立つ出力もコンソールに出力されます。

***

## <a name="facts-and-assertions"></a>事実とアサーション

Q# の関数には_論理的な_副作用がないため、出力型が空の組である関数を実行するその_他の種類_の効果は、Q# プログラム内からは観察`()`できません。
つまり、ターゲット マシンは、この省略が、次の Q# コードの動作を変更しないことを保証して戻る`()`関数を実行しないことを選択できます。
これにより、関数が`()`返される (つまり`Unit`) アサーションを埋め込み、ロジックを Q# プログラムにデバッグするための便利なツールになります。 

簡単な例を考えてみましょう。

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

このキーワード`fail`は、計算を進めないことを示し、Q# プログラムを実行しているターゲット マシンで例外を発生させます。
定義上、この種のエラーは、`fail`ステートメントに到達した後にそれ以上の Q# コードが実行されないので、Q# 内からは観察できません。
したがって、呼び出しを過ぎて`PositivityFact`進めば、その入力が正の値であったことが保証されます。

名前空間の関数を使用する場合と`PositivityFact`同じ動作[`Fact`](xref:microsoft.quantum.diagnostics.fact)を実装できること<xref:microsoft.quantum.diagnostics>に注意してください。

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

一方 *、アサーション*はファクトと同様に使用されますが、ターゲット マシンの状態に依存する可能性があります。 それに応じて、それらは操作として定義され、ファクトは(上記のように)関数として定義されます。
この違いを理解するために、アサーション内でのファクトの次の使用を考慮してください。

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

ここでは、使用できる量子ビットの<xref:microsoft.quantum.environment.getqubitsavailabletouse>数を返すために操作を使用しています。
これは明らかにプログラムのグローバル状態とその実行環境に依存するので、私たちの定義は同様`AssertQubitsAreAvailable`に操作でなければなりません。
ただし、関数への入力として単純な`Bool`値を生成するために、そのグローバル状態を`Fact`使用できます。

これらのアイデアに基づいて、[前奏曲は](xref:microsoft.quantum.libraries.standard.prelude)2つの特に有用な<xref:microsoft.quantum.intrinsic.assert>アサーション<xref:microsoft.quantum.intrinsic.assertprob>を`()`提供し、両方ともに操作としてモデル化されています. これらのアサーションは、それぞれ、関心のある特定の測定、測定を実行する量子レジスタ、および仮説結果を記述するPauli演算子を取ります。
シミュレーションで動作するターゲットマシンでは、[クローンなし定理](https://en.wikipedia.org/wiki/No-cloning_theorem)に縛られず、そのようなアサーションに渡されたレジスタを乱すことなく、そのような測定を行うことができます。
シミュレータは、上記の`PositivityFact`関数と同様に、実際には仮定の結果が観察されない場合に計算を中止することができます。

```qsharp
using (register = Qubit()) 
{
    H(register);
    Assert([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

非クローニング定理が量子状態の検査を妨げる物理量子ハードウェアでは、および`Assert``AssertProb`操作は単に他の効果を`()`伴わなく戻ります。

名前空間<xref:microsoft.quantum.diagnostics>は、より高度な条件を`Assert`チェックすることを可能にするファミリのいくつかのより多くの機能を提供します。 

## <a name="dump-functions"></a>ダンプ関数

クォンタム プログラムの<xref:microsoft.quantum.diagnostics>トラブルシューティングを支援するために、名前空間には、ターゲット マシンの現在の状態をファイルに<xref:microsoft.quantum.diagnostics.dumpmachine>ダンプ<xref:microsoft.quantum.diagnostics.dumpregister>できる 2 つの関数が用意されています。 生成される出力は、ターゲット マシンによって異なります。

### <a name="dumpmachine"></a>DumpMachine

量子開発キットの一部として配布されたフルステート量子シミュレータは、量子システム全体の[波動関数](https://en.wikipedia.org/wiki/Wave_function)を複素数の1次元配列としてファイルに書き込み、各要素は計算基準状態を測定する確率の振幅を表します。\ket{n}= \ket{b_{n-1}.ビット $b_i\}$\{のb_1b_0}$ たとえば、2 つの量子ビットのみが割り当てられ、量子状態のマシンでは、$$ \begin{align} \ket{\psi}{1}= \frac{2}{\sqrt} \ket{00} - \frac{(1 + i)}{2} \ケット{10}、\end{align} $$ 呼び出し<xref:microsoft.quantum.diagnostics.dumpmachine>は次の出力を生成します。

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

最初の行は、対応する量子ビットの ID を重要な順序でコメントします。
残りの行は、デカルト形式と極座標形式の両方で、基底状態ベクトル $\ket{n}$ を測定する確率振幅を表します。 最初の行の詳細:

* **`∣0❭:`** この行は計算基準状態`0`に対応します
* **`0.707107 +  0.000000 i`**: デカルト形式での確率振幅。
* **` == `**:`equal`符号は両方の等価表現を分け合います。
* **`**********  `**: 大きさをグラフィカルに表現した場合、`*`その数はこの状態ベクトルを測定する確率に比例します。
* **`[ 0.500000 ]`**: マグニチュードの数値
* **`    ---`**: 振幅の位相をグラフィカルに表現します(下記参照)。
* **`[ 0.0000 rad ]`**: 位相の数値(ラジアン単位)。

マグニチュードと位相の両方が、グラフィカルに表示されます。 大きさ表現はまっすぐです:バーが表示され`*`、バーが大きくなる確率が大きくなります。 フェーズでは、範囲に基づいて角度を表す次のシンボルを示します。

```
[ -π/16,   π/16)       ---
[  π/16,  3π/16)        /-
[ 3π/16,  5π/16)        / 
[ 5π/16,  7π/16)       +/ 
[ 7π/16,  9π/16)      ↑   
[ 8π/16, 11π/16)    \-    
[ 7π/16, 13π/16)    \     
[ 7π/16, 15π/16)   +\     
[15π/16, 19π/16)   ---    
[17π/16, 19π/16)   -/     
[19π/16, 21π/16)    /     
[21π/16, 23π/16)    /+    
[23π/16, 25π/16)      ↓   
[25π/16, 27π/16)       -\ 
[27π/16, 29π/16)        \ 
[29π/16, 31π/16)        \+
[31π/16,   π/16)       ---
```

次の例は`DumpMachine`、いくつかの一般的な状態を示しています。

### `∣0❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

### `∣1❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣1❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
```

### `∣+❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
```

### `∣-❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:    -0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]  ---     [  3.14159 rad ]
```


  > [!NOTE]
  > 量子ビットの id は実行時に割り当てられ、必ずしも qubit が割り当てられた順序や qubit レジスタ内での位置と一致しません。


#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > Visual Studio で、コードにブレークポイントを設定し、qubit 変数の値を調べることによって、qubit id を把握できます。
  > 
  > ![ビジュアルスタジオでクビット ID を表示する](~/media/qubit_id.png)
  >
  > `0`インデックスをオンに`register2`したクビットには`3`id= があり、インデックス`1`付きの`2`クビットは id= を持っています。

#### <a name="command-line--visual-studio-code"></a>[コマンドライン/Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > 関数を使用<xref:microsoft.quantum.intrinsic.message>して、メッセージに qubit 変数を渡すことによって、qubit id を把握できます。
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > この出力を生成する可能性があります。
  >```
  > 0=q:3; 1=q:2
  >```
  > `0`つまり、インデックスをオンに`register2`したクビットには id=`3`があり、インデックス`1`付きのク`2`ビットには id= があります。


***

<xref:microsoft.quantum.diagnostics.dumpmachine>は名前空間の<xref:microsoft.quantum.diagnostics>一部であるため、これを使用するには、ステートメントを`open`追加する必要があります。

```qsharp
namespace Samples {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {
        using (qubits = Qubit[2]) {
            H(qubits[1]);
            DumpMachine("dump.txt");
        }
    }
}
```


### <a name="dumpregister"></a>DumpRegister

<xref:microsoft.quantum.diagnostics.dumpregister>同様<xref:microsoft.quantum.diagnostics.dumpmachine>に動作しますが、情報の量を対応する量子ビットに関連する情報のみに制限するために、量子ビットの配列を取ります。

と同様<xref:microsoft.quantum.diagnostics.dumpmachine>に、によって<xref:microsoft.quantum.diagnostics.dumpregister>生成される情報はターゲット マシンによって異なります。 フルステートクォンタム シミュレータの場合、ファイルに、指定された量子ビットによって生成される量子サブシステムのグローバルフェーズまで、波動関数を同じ形式で<xref:microsoft.quantum.diagnostics.dumpmachine>書き込みます。  たとえば、 2 つの量子ビットのみが割り当てられ、量子状態のマシン $$ \begin{align} \ket{\psi} ={1}\frac{2}{\sqrt{00} } \ket - \frac{1 +{2} i)} \ket{10} = - e^{i\pi/4} ( (\frac{1}{\sqrt{1} {2}{0} <xref:microsoft.quantum.diagnostics.dumpregister> `qubit[0]` {2}} \ket{0} - \frac{(1 + i)}{2} \ケット ) \otimes \frac{-(1 + i)}{\sqrt } \ket) 、\end{align} 呼び出しを呼び出す $$ $$ この出力が生成されます。

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

を呼<xref:microsoft.quantum.diagnostics.dumpregister>`qubit[1]`び出すと、次の出力が生成されます。

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

一般に、別のレジスタと絡み合うレジスタの状態は、純粋な状態ではなく混合状態です。 この場合、<xref:microsoft.quantum.diagnostics.dumpregister>次のメッセージを出力します。

```
Qubits provided (0;) are entangled with some other qubit.
```

次の例は、Q# コード<xref:microsoft.quantum.diagnostics.dumpregister><xref:microsoft.quantum.diagnostics.dumpmachine>の両方を使用する方法を示しています。

```qsharp
namespace app
{
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {

        using (qubits = Qubit[2]) {
            X(qubits[1]);
            H(qubits[1]);
            R1Frac(1, 2, qubits[1]);
            
            DumpMachine("dump.txt");
            DumpRegister("q0.txt", qubits[0..0]);
            DumpRegister("q1.txt", qubits[1..1]);

            ResetAll(qubits);
        }
    }
}
```

## <a name="debugging"></a>デバッグ

関数と`Dump`操作`Assert`の上に、Q# は、標準的な Visual Studio デバッグ機能のサブセットをサポートしています:[行のブレークポイントを設定](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)する[、F10 を使用してコードをステップ実行](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)し、[クラシック変数の値を検査するすべての](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)シミュレータ上のコードの実行中に可能です。

Visual Studio コードでのデバッグは、オムニシャープによって提供される Visual Studio コード拡張機能の C# によって提供されるデバッグ機能を活用し、[最新バージョン](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)をインストールする必要があります。 
