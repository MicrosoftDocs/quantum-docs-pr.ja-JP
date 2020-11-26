---
title: テストとデバッグ
description: 単体テスト、ファクトとアサーション、およびダンプ関数を使用して、クォンタムプログラムをテストおよびデバッグする方法について説明します。
author: tcNickolas
ms.author: mamykhai
ms.date: 06/01/2020
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
no-loc:
- Q#
- $$v
ms.openlocfilehash: 17a67f0a6fa7ffb9436828178acd93e1cb87a8cd
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96233989"
---
# <a name="testing-and-debugging"></a>テストとデバッグ

従来のプログラミングと同様に、クォンタムプログラムが意図したとおりに動作することを確認し、正しくない動作を診断できるようにすることが不可欠です。
このセクションでは、 Q# クォンタムプログラムをテストおよびデバッグするためにに用意されているツールについて説明します。

## <a name="unit-tests"></a>単体テスト

従来のプログラムをテストする一般的な方法の1つは、 *単体テスト* と呼ばれる小さなプログラムを作成することです。これにより、ライブラリでコードを実行し、出力を予想される出力と比較します。
たとえば、 `Square(2)` `4` $ 2 ^ 2 = $4 の *priori* がわかっているため、がを返すようにすることができます。

Q# は、クォンタムプログラムの単体テストの作成をサポートしています。これは、 [Xunit](https://xunit.github.io/) 単体テストフレームワーク内でテストとして実行できます。

### <a name="creating-a-test-project"></a>テストプロジェクトの作成

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Visual Studio 2019 を開きます。 [**ファイル**] メニューにアクセスし、[**新しい > プロジェクト**] を選択します。右上隅にあるを検索し、 `Q#` **Q# テストプロジェクト** テンプレートを選択します。

#### <a name="command-line--visual-studio-code"></a>[コマンドライン/Visual Studio Code](#tab/tabid-vscode)

お気に入りのコマンドラインから、次のコマンドを実行します。
```dotnetcli
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

新しいプロジェクトには `Tests.qs` 、新しい単体テストを定義するための便利な場所を提供する1つのファイルがあり Q# ます。
初期状態では、このファイルに `AllocateQubit` は、新しく割り当てられた qubit が $ \ket $ 状態であることを確認し、メッセージを出力するサンプル単体テストが1つ含まれてい {0} ます。

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            AssertMeasurement([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

Q#型の引数を受け取り、を返すすべての操作または関数は `Unit` `Unit` 、属性を使用して単体テストとしてマークでき `@Test("...")` ます。 前の例では、その属性の引数が、 `"QuantumSimulator"` テストを実行するターゲットを指定しています。 1つのテストを複数のターゲットで実行できます。 たとえば、の前に属性を追加し `@Test("ResourcesEstimator")` `AllocateQubit` ます。 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
ファイルを保存し、すべてのテストを実行します。 ここで、2つの単体テストがあります。1つはで実行され、もう1つは `AllocateQubit` `QuantumSimulator` で実行さ `ResourcesEstimator` れます。 

コンパイラは、 Q# 組み込みのターゲット、、を、 `"QuantumSimulator"` `"ToffoliSimulator"` `"ResourcesEstimator"` 単体テストの有効な実行ターゲットとして認識します。 また、任意の完全修飾名を指定して、カスタム実行ターゲットを定義することもできます。 

### <a name="running-no-locq-unit-tests"></a>Q#単体テストの実行

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

ソリューションごとの1回限りの設定として、[ **テスト** ] メニューの [テストの設定] を選択し、[ **既定のプロセッサアーキテクチャ > X64 >** ます。

> [!TIP]
> Visual Studio の既定のプロセッサアーキテクチャ設定は、各ソリューションのソリューションオプション () ファイルに格納され `.suo` ます。
> このファイルを削除する場合は、プロセッサアーキテクチャとして **X64** を選択する必要があります。

プロジェクトをビルドし、[ **テスト** ] メニューを開き、[ **Windows > テストエクスプローラー**] を選択します。 **Allocatequbit** は、[ **テストを実行しない** ] グループのテストの一覧に表示されます。 [ **すべて実行** ] を選択するか、この個々のテストを実行します。

#### <a name="command-line--visual-studio-code"></a>[コマンドライン/Visual Studio Code](#tab/tabid-vscode)

テストを実行するには、プロジェクトフォルダー (を含むフォルダー) に移動 `Tests.csproj` し、次のコマンドを実行します。

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

単体テストは、名前または実行ターゲットに応じてフィルター処理できます。

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


**_

組み込み関数に <xref:Microsoft.Quantum.Intrinsic.Message> は型があり、 `(String -> Unit)` 診断メッセージを作成できます。

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

テストエクスプローラーでテストを実行し、テストをクリックすると、テストの実行に関する情報がパネルに表示されます (成功/失敗の状態、経過時間、および出力へのリンク)。 [_ *出力*] * をクリックして、新しいウィンドウでテスト出力を開きます。

![テスト出力](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[コマンドライン/Visual Studio Code](#tab/tabid-vscode)

各テストの成功/失敗の状態は、によってコンソールに出力され `dotnet test` ます。
失敗したテストの場合は、エラーの診断に役立つ出力もコンソールに出力されます。

**_

## <a name="facts-and-assertions"></a>ファクトとアサーション

の関数には Q# _論理的_ な副作用がないため、プログラム内から、 Q# 出力の種類が空のタプルである関数の実行によって他の種類の影響が発生しないようにすることはできません `()` 。
つまり、ターゲットコンピューターは、この省略によって `()` 次のコードの動作が変更されないことを保証して、が返す関数を実行しないことを選択でき Q# ます。
この動作により `()` 、関数 (など `Unit` ) が、アサーションの埋め込みとプログラムへのデバッグロジックに便利なツールとして返さ Q# れます。 

単純な例を考えてみましょう。

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

ここで、キーワードは、 `fail` 計算が続行されないことを示し、プログラムを実行しているターゲットコンピューターで例外を発生させ Q# ます。
定義上、この種のエラーは、 Q# ターゲットコンピューターが Q# ステートメントに到達した後にコードを実行しなくなったため、内からは確認できません `fail` 。
したがって、への呼び出しを実行した後にを続行すると、入力が肯定的であることが `PositivityFact` 保証されます。

名前空間の関数を使用するのと同じ動作を実装できることに注意して `PositivityFact` [`Fact`](xref:Microsoft.Quantum.Diagnostics.Fact) <xref:Microsoft.Quantum.Diagnostics> ください。

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

一方、_Assertions * はファクトと同様に使用されますが、ターゲットコンピューターの状態によって異なる場合があります。 それに応じて、これらは操作として定義されますが、ファクトは関数として定義されます (前の例のように)。
この違いを理解するには、アサーション内で次のファクトを使用することを検討してください。

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

ここでは、操作を使用して、 <xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse> 使用可能な qubits の数を返します。
これは、プログラムとその実行環境のグローバルな状態によって異なりますが、の定義 `AssertQubitsAreAvailable` も操作である必要があります。
ただし、そのグローバル状態を使用し `Bool` て、関数への入力として単純な値を生成することができ `Fact` ます。

これらのアイデアを基にして構築さ[れた準備は](xref:microsoft.quantum.libraries.standard.prelude)、2つの便利なアサーションを提供 <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> し、 <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> 両方とも操作としてモデル化されて `()` います。 これらのアサーションは、特定の対象測定、測定が実行されるクォンタムレジスタ、および仮定の結果を記述する P# li オペレーターを受け取ります。
シミュレーションによって動作するターゲットコンピューターは、 [複製なしの定理](https://en.wikipedia.org/wiki/No-cloning_theorem)によってバインドされないため、このようなアサーションに合格するレジスタに支障をきたすことなく、このような測定を実行できます。
次に、シミュレーターは、前の関数と同様に、 `PositivityFact` 仮定の結果が実際に観測されていない場合に計算を停止できます。

```qsharp
using (register = Qubit()) 
{
    H(register);
    AssertMeasurement([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

物理クォンタムハードウェアでは、複製なしの定理がクォンタムの状態を検査できない場合 `AssertMeasurement` 、 `AssertMeasurementProbability` 操作と操作は単 `()` に他の効果なしでを返します。

名前空間には、 <xref:Microsoft.Quantum.Diagnostics> `Assert` さらに高度な条件を確認できるファミリの機能がいくつか用意されています。 

## <a name="dump-functions"></a>ダンプ関数

クォンタムプログラムのトラブルシューティングに役立つように、名前空間には、 <xref:Microsoft.Quantum.Diagnostics> ターゲットコンピューターの現在の状態をファイルにダンプできる2つの関数 (および) が用意されて <xref:Microsoft.Quantum.Diagnostics.DumpMachine> <xref:Microsoft.Quantum.Diagnostics.DumpRegister> います。 それぞれのの生成された出力は、ターゲットコンピューターによって異なります。

### <a name="dumpmachine"></a>DumpMachine

Quantum 開発キットの一部として配布された完全な状態のクォンタムシミュレーターは、クォンタムシステム全体の [wave 関数](https://en.wikipedia.org/wiki/Wave_function) を、1次元の複素数の配列としてファイルに書き込みます。各要素は、コンピューティングベースの状態を測定する確率の振幅 ($ \ket{n} = \ket{b_ {n-1}...) を表します。b_1b_0} $ (bits $ \{ b_i $ の場合) \} 。 たとえば、2つの qubits のみが割り当てられ、クォンタム状態が $ $ \begin{align} \ket{\psi} = \ frac {1} {\ sqrt {2} } \ket {00} -\frac{(1 + i)} \ket であるコンピューターでは、 {2} {10} \end{align} $ $ を呼び出すと、次の出力が生成され <xref:Microsoft.Quantum.Diagnostics.DumpMachine> ます。

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

最初の行は、対応する qubits の id を持つコメントを有意な順序で提供します。
残りの行は、デカルト形式と極座標形式の両方で、basis 状態ベクター $ \ket{n} $ を測定する確率の振幅を示しています。 最初の行の詳細は次のとおりです。

* **`∣0❭:`** この行は、計算基礎の状態に対応します。 `0`
* **`0.707107 +  0.000000 i`**: デカルト形式の確率の振幅。
* **` == `**: 符号は、 `equal` 両方の同等の表現を分離します。
* **`**********  `**: 大きさをグラフィカルに表示します。の数は、 `*` この状態ベクターを測定する確率に比例します。
* **`[ 0.500000 ]`**: マグニチュードの数値
* **`    ---`**: 振幅のフェーズをグラフィカルに表示します (次の出力を参照してください)。
* **`[ 0.0000 rad ]`**: フェーズの数値 (ラジアン)。

大きさとフェーズの両方がグラフィック表示で表示されます。 マグニチュード表現は、水平方向です。の棒が大きいほど、 `*` 棒が大きくなる確率が大きくなります。 フェーズでは、次の記号を使用して範囲に基づく角度を表します。

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

次の例は、 `DumpMachine` いくつかの一般的な状態を示しています。

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


#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > コードにブレークポイントを配置し、qubit 変数の値を調べることで、Visual Studio で qubit id を見つけることができます。次に例を示します。
  > 
  > ![Visual Studio での qubit id の表示](~/media/qubit_id.png)
  >
  > インデックスがである qubit の `0` `register2` id = `3` 、qubit with index `1` は id = `2` です。

#### <a name="command-line--visual-studio-code"></a>[コマンドライン/Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > 関数を使用し、メッセージに qubit 変数を渡すことによって、qubit id を見つけることができ <xref:Microsoft.Quantum.Intrinsic.Message> ます。次に例を示します。
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > 次のような出力が生成できます。
  >```
  > 0=q:3; 1=q:2
  >```
  > これは、インデックスを持つ qubit の id がであることを意味します。これは、 `0` `register2` `3` インデックスを持つ qubit `1` が id = であることを意味し `2` ます。


**_

<xref:Microsoft.Quantum.Diagnostics.DumpMachine>は名前空間の一部 <xref:Microsoft.Quantum.Diagnostics> であるため、 `open` それにアクセスするためのステートメントを追加する必要があります。

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

<xref:Microsoft.Quantum.Diagnostics.DumpRegister> はと同じように動作し <xref:Microsoft.Quantum.Diagnostics.DumpMachine> ますが、情報の量を対応する qubits に限定するために、qubits の配列も取得する点が異なります。

と同様に <xref:Microsoft.Quantum.Diagnostics.DumpMachine> 、によって生成される情報は <xref:Microsoft.Quantum.Diagnostics.DumpRegister> ターゲットコンピューターによって異なります。 完全な状態のクォンタムシミュレーターでは、と同じ形式で指定された qubits によって生成されるクォンタムサブシステムのグローバルフェーズまで、wave 関数がファイルに書き込まれ <xref:Microsoft.Quantum.Diagnostics.DumpMachine> ます。  たとえば、2つの qubits のみが割り当てられ、クォンタム状態が $ $ \begin{align} \ket{\psi} = \ frac {1} {\ sqrt {2} } \ket {00} -\frac{(1 + i)} \ket =-e ^ {であるマシンをもう一度実行します。 {2} {10} -i \ pi/4} ((\ frac {1} {\ sqrt {2} } \ket {0} -\frac{(1 + i)} {2} \ket {1} ) \ otimes \frac{-(1 + i)} {\ sqrt {2} } \ket {0} )、\end{align} $ $ を呼び出すと <xref:Microsoft.Quantum.Diagnostics.DumpRegister> 、次の出力が生成され `qubit[0]` ます。

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     _******************* [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

とを呼び出すと、次 <xref:Microsoft.Quantum.Diagnostics.DumpRegister> の出力が生成され `qubit[1]` ます。

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

一般に、別のレジスタによって使用されるレジスタの状態は、純粋な状態ではなく混合状態になります。 この場合、は <xref:Microsoft.Quantum.Diagnostics.DumpRegister> 次のメッセージを出力します。

```
Qubits provided (0;) are entangled with some other qubit.
```

次の例は、 <xref:Microsoft.Quantum.Diagnostics.DumpRegister> コード内でとの両方を使用する方法を示してい <xref:Microsoft.Quantum.Diagnostics.DumpMachine> Q# ます。

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

`Assert`およびの `Dump` 関数と操作の上で、は、 Q# 標準の Visual Studio デバッグ機能のサブセットをサポートしています。[行ブレークポイントの設定](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)、 [F10 を使用したコードのステップ](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)実行、および[クラシック変数の値の検査](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)は、シミュレーターでコードを実行するときにすべて可能です。

Visual Studio Code でのデバッグでは、OmniSharp によって強化された Visual Studio Code 拡張機能のために C# によって提供されるデバッグ機能を利用し、 [最新バージョン](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)をインストールする必要があります。 
