---
title: 'Q # の手法-テストとデバッグ |Microsoft Docs'
description: 'Q # の手法-テストとデバッグ'
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 25679331f1bed9f98b86c6eb20f511c891bac1af
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183490"
---
# <a name="testing-and-debugging"></a>テストとデバッグ

従来のプログラミングと同様に、クォンタムプログラムが意図したとおりに動作することを確認し、正しくないクォンタムプログラムを診断できるようにすることが不可欠です。
このセクションでは、クォンタムプログラムをテストおよびデバッグするための Q # によって提供されるツールについて説明します。

## <a name="unit-tests"></a>単体テスト

クラシックプログラムをテストする一般的な方法の1つは、ライブラリ内のコードを実行する*単体テスト*と呼ばれる小さなプログラムを記述し、その出力を予想される出力と比較することです。
たとえば、 *priori*が $ 2 ^ 2 = $4 であることがわかっているため、`Square(2)` が `4`を返すようにすることができます。

Q # は、クォンタムプログラムの単体テストの作成をサポートしています。これは、 [Xunit](https://xunit.github.io/)単体テストフレームワーク内でテストとして実行できます。

### <a name="creating-a-test-project"></a>テストプロジェクトの作成

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Visual Studio 2019 を開きます。 `File` メニューにアクセスし、[`New` > `Project...`] を選択します。
プロジェクトテンプレートエクスプローラーの `Installed` > `Visual C#`で、`Q# Test Project` テンプレートを選択します。

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[コマンドライン/Visual Studio Code](#tab/tabid-vscode)

お気に入りのコマンドラインから、次のコマンドを実行します。
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

どちらの場合も、新しいプロジェクトに2つのファイルが開かれます。
最初のファイル `Tests.qs`は、新しい Q # の単体テストを定義するための便利な場所です。
初期状態では、このファイルには1つのサンプル単体テスト `AllocateQubitTest` が含まれています。これは、新しく割り当てられた qubit が $ \ket{0}$ 状態であることを確認し、メッセージを出力します。

```qsharp
    operation AllocateQubitTest () : Unit {
        using (q = Qubit()) {
            Assert([PauliZ], [q], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

`(Unit -> Unit)` と互換性のある型 `(Unit => Unit)` または関数と互換性のある Q # 操作は、単体テストとして実行できます。 

2番目のファイル `TestSuiteRunner.cs` には、Q # の単体テストを検出して実行するメソッドが含まれています。 これは `OperationDriver` 属性で注釈が付けられた `TestTarget` メソッドです。
`OperationDriver` 属性は、Xunit 拡張機能ライブラリの一部であり、"、" です。
単体テストフレームワークは、検出されたすべての Q # 単体テストに対して `TestTarget` メソッドを呼び出します。
フレームワークは `op` 引数を使用して、単体テストの説明をメソッドに渡します。 次のコード行を実行します。
```csharp
op.TestOperationRunner(sim);
```
`QuantumSimulator`で単体テストを実行します。

既定では、単体テストの検出メカニズムは、次のプロパティを満たすすべての Q # 関数または互換性のある型の操作を検索します。
* `OperationDriver` 属性で注釈が付けられたメソッドと同じアセンブリ内にあります。
* `OperationDriver` 属性で注釈が付けられたメソッドと同じ名前空間にあります。
* には `Test`で終わる名前があります。

アセンブリ、名前空間、および単体テスト関数と操作のサフィックスは、`OperationDriver` 属性の省略可能なパラメーターを使用して設定できます。
* `AssemblyName` パラメーターは、テスト用に検索されるアセンブリの名前を設定します。
* `TestNamespace` パラメーターは、テスト用に検索される名前空間の名前を設定します。
* 単体テストと見なされる操作名または関数名のサフィックスを `Suffix` 設定します。

また、`TestCasePrefix` 省略可能なパラメーターを使用すると、テストケースの名前のプレフィックスを設定できます。 操作名の前にあるプレフィックスが、テストケースの一覧に表示されます。 たとえば、`TestCasePrefix = "QSim:"` によって `AllocateQubitTest` が検出されたテストの一覧に `QSim:AllocateQubitTest` として表示されます。 これは、たとえば、テストの実行に使用されるシミュレーターを示すのに便利です。

### <a name="running-q-unit-tests"></a>Q # の単体テストの実行

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

ソリューションごとの1回限りの設定として、`Test` メニューにアクセスし、[`Test Settings` > `Default Processor Architecture` > `X64`] を選択します。

> [!TIP]
> Visual Studio の既定のプロセッサアーキテクチャ設定は、各ソリューションのソリューションオプション (`.suo`) ファイルに格納されます。
> このファイルを削除する場合は、プロセッサのアーキテクチャとして [`X64`] を選択する必要があります。

プロジェクトをビルドし、[`Test`] メニューにアクセスして、[`Windows` > `Test Explorer`] を選択します。 `Not Run Tests` グループ内のテストの一覧に `AllocateQubitTest` が表示されます。 `Run All` を選択するか、この個別のテストを実行して、合格する必要があります。

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[コマンドライン/Visual Studio Code](#tab/tabid-vscode)

テストを実行するには、プロジェクトフォルダー (`Tests.csproj`を含むフォルダー) に移動し、次のコマンドを実行します。

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

***

## <a name="logging-and-assertions"></a>ログとアサーション

Q # の関数には副作用がないという事実が1つあります。これは、出力の種類が空の `()` タプルである関数を実行した場合の影響は、Q # プログラム内からは確認できないということです。
つまり、ターゲットコンピューターは、この省略によって次の Q # コードの動作が変更されないことを保証して `()` を返す関数を実行しないことを選択できます。
これにより、アサーションを埋め込み、デバッグロジックを Q # プログラムに組み込むための便利なツール `()` を返す関数が作成されます。 

### <a name="logging"></a>ログ記録

組み込み関数 <xref:microsoft.quantum.intrinsic.message> 型 `(String -> Unit)` で、診断メッセージを作成できます。

`QuantumSimulator` の `onLog` アクションを使用して、Q # コードが `Message`を呼び出すときに実行されるアクションを定義できます。 既定では、ログに記録されたメッセージは標準出力に出力されます。

単体テストスイートを定義する場合、ログに記録されたメッセージをテスト出力に送ることができます。 プロジェクトが Q # Test プロジェクトテンプレートから作成されると、このリダイレクトはスイート用に事前構成され、既定では次のように作成されます。

```qsharp
using (var sim = new QuantumSimulator())
{
    // OnLog defines action(s) performed when Q# test calls operation Message
    sim.OnLog += (msg) => { output.WriteLine(msg); };
    op.TestOperationRunner(sim);
}
```

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

テストエクスプローラーでテストを実行し、テストをクリックすると、テストの実行に関する情報がパネルに表示されます (成功/失敗の状態、経過時間、および "出力" リンク)。 [出力] リンクをクリックすると、新しいウィンドウでテスト出力が開きます。

![テスト出力](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[コマンドライン/Visual Studio Code](#tab/tabid-vscode)

各テストの成功/失敗の状態は、`dotnet test`によってコンソールに出力されます。
失敗したテストについては、上記の `output.WriteLine(msg)` 呼び出しの結果として記録された出力もコンソールに出力され、エラーの診断に役立ちます。

***

### <a name="assertions"></a>表明

同じロジックを、アサーションの実装にも適用できます。 単純な例を考えてみましょう。

```qsharp
function AssertPositive(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

ここで、キーワード `fail` は、計算が続行されないことを示し、Q # プログラムを実行しているターゲットコンピューターで例外が発生します。
定義上、Q # 内では、この種のエラーを確認することはできません。これは、`fail` ステートメントに達した後に、それ以上の Q # コードが実行されないためです。
したがって、`AssertPositive`の呼び出しを続けて実行した場合は、入力が肯定的であることが保証されます。

これらのアイデアを基にして、準備には、`()`に対する操作としてモデル化さ[れた](xref:microsoft.quantum.libraries.standard.prelude)、<xref:microsoft.quantum.intrinsic.assert> と <xref:microsoft.quantum.intrinsic.assertprob> の2つの便利なアサーションが用意されています。 これらのアサーションは、特定の対象測定、測定を実行するクォンタムレジスタ、および仮定の結果を記述する P# li オペレーターを受け取ります。
シミュレーションによって動作するターゲットコンピューターでは、[複製なしの定理](https://en.wikipedia.org/wiki/No-cloning_theorem)によってバインドされていないため、このようなアサーションに渡されたレジスタに支障をきたすことなく、このような測定を実行できます。
シミュレーターは、上記の `AssertPositive` 関数と同様に、実際の結果が実際に観察されない場合に計算を中止できます。

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

物理的なクォンタムハードウェアでは、複製なしの定理がクォンタムの状態を検査できない場合、`Assert` 操作と `AssertProb` 操作は単に `()` を返します。これ以外の影響はありません。

<xref:microsoft.quantum.diagnostics> 名前空間には、より高度な条件をチェックできるようにする、`Assert` ファミリの機能がいくつか用意されています。 

## <a name="dump-functions"></a>ダンプ関数

クォンタムプログラムのトラブルシューティングに役立つように、<xref:microsoft.quantum.diagnostics> 名前空間には、ターゲットコンピューターの現在の状態をファイルにダンプできる2つの関数 (<xref:microsoft.quantum.diagnostics.dumpmachine> と <xref:microsoft.quantum.diagnostics.dumpregister>) が用意されています。 それぞれのの生成された出力は、ターゲットコンピューターによって異なります。

### <a name="dumpmachine"></a>DumpMachine

Quantum 開発キットの一部として配布された完全な状態のクォンタムシミュレーターは、ファセットの1次元配列として、クォンタムシステム全体の[wave 関数](https://en.wikipedia.org/wiki/Wave_function)をファイルに書き込みます。各要素は、計算基準の状態を測定する確率 $ \ket{n} $ ($ \ket{n} = \ket{b_{n-1}...)b_1b_0} $ for bits $\{b_i\}$。 たとえば、2つの qubits が割り当てられていて、クォンタム状態が $ $ \begin{align} \ket{\psi}{2}{1}= \ket{00}-\frac{(1 + i)}{2} \ket{10}であるコンピューターでは、\end{align} $ $ の呼び出し <xref:microsoft.quantum.diagnostics.dumpmachine> はこの出力を生成します:

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

最初の行は、対応する qubits の Id を持つコメントを有意な順序で提供します。
残りの行は、デカルト形式と極座標形式の両方で、basis 状態ベクター $ \ket{n} $ を測定する確率の振幅を示しています。 最初の行の詳細は次のとおりです。

* この行 **`∣0❭:`** `0` の計算基準の状態に対応します
* **`0.707107 +  0.000000 i`** : デカルト形式の確率の振幅。
* **` == `** : `equal` sign は、両方の同等表現を seperates します。
* **`**********  `** : 大きさをグラフィカルに表現したもので、`*` の数は、この状態ベクターを測定する確率に比例します。
* **`[ 0.500000 ]`** : 大きさの数値
* **`    ---`** : 振幅のフェーズをグラフィックで表現したもの (下記参照)。
* **`[ 0.0000 rad ]`** : フェーズの数値 (ラジアン)。

大きさとフェーズの両方がグラフィック表示で表示されます。 マグニチュード表現は、水平方向であり、`*`の棒を示すので、棒が大きくなる確率が大きくなります。 フェーズでは、次の記号を使用して範囲に基づく角度を表します。

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

次の例は、いくつかの一般的な状態の `DumpMachine` を示しています。

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
  > Qubit の id は実行時に割り当てられ、必ずしも qubit が割り当てられた順序、または qubit レジスタ内の位置に一致するとは限りません。


#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > コードにブレークポイントを配置し、qubit 変数の値を調べることで、Visual Studio で qubit id を調べることができます。次に例を示します。
  > 
  > ![Visual Studio での qubit id の表示](~/media/qubit_id.png)
  >
  > `register2` のインデックス `0` を持つ qubit の id =`3`、インデックス `1` の qubit には id =`2`が使用されています。

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[コマンドライン/Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > <xref:microsoft.quantum.intrinsic.message> 関数を使用し、メッセージに qubit 変数を渡すことによって、qubit id を確認できます。次に例を示します。
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > 次のような出力が生成できます。
  >```
  > 0=q:3; 1=q:2
  >```
  > これは、`register2` のインデックス `0` が指定された qubit に id =`3`があることを意味します。これは、インデックス `1` の qubit の id が`2`であることを意味します。


***

<xref:microsoft.quantum.diagnostics.dumpmachine> は <xref:microsoft.quantum.diagnostics> 名前空間の一部であるため、これを使用するには `open` ステートメントを追加する必要があります。

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

<xref:microsoft.quantum.diagnostics.dumpregister> は <xref:microsoft.quantum.diagnostics.dumpmachine>のように機能しますが、情報の量を対応する qubits にのみ制限するために、qubits の配列を受け取る点が異なります。

<xref:microsoft.quantum.diagnostics.dumpmachine>と同様に、<xref:microsoft.quantum.diagnostics.dumpregister> によって生成される情報はターゲットコンピューターによって異なります。 完全な状態のクォンタムシミュレーターでは、ファイルに書き込みます。これは、指定された qubits によって生成されるクォンタムサブシステムのグローバルフェーズまで、wave 関数を <xref:microsoft.quantum.diagnostics.dumpmachine>と同じ形式で作成します。  たとえば、2つの qubits が割り当てられ、クォンタム状態が $ $ \begin{align} \ket{\psi} = \ frac{1}{\ sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10} =-e ^ {-i \ pi/4} ((\ frac{1}{/sqrt{2}} \) のコンピューターを再度実行します。k{0}-\frac{(1 + i)}{2} \ket{1}) \ otimes \frac{-(1 + i)} {\ sqrt{2}} \ket{0})、\end{align} $ $ <xref:microsoft.quantum.diagnostics.dumpregister> を呼び出すと、この出力が生成されます。

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

また、`qubit[1]` の <xref:microsoft.quantum.diagnostics.dumpregister> を呼び出すと、次の出力が生成されます。

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

一般に、別のレジスタによって使用されるレジスタの状態は、純粋な状態ではなく混合状態になります。 この場合、<xref:microsoft.quantum.diagnostics.dumpregister> は次のメッセージを出力します。

```
Qubits provided (0;) are entangled with some other qubit.
```

次の例では、Q # コードで <xref:microsoft.quantum.diagnostics.dumpregister> と <xref:microsoft.quantum.diagnostics.dumpmachine> の両方を使用する方法を示します。

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

`Assert` と `Dump` の関数と操作の上で、Q # は標準の Visual Studio デバッグ機能のサブセットをサポートします。コードの[ブレークポイントの設定](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)、 [F10 を使用したコードのステップ実行](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)、および[クラシック変数の値の検査](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)は、シミュレーターでのコードの実行中に可能です。

Visual Studio Code でのデバッグはまだサポートされていません。
