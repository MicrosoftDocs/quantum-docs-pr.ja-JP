---
title: で qubit レベルのプログラムを作成およびシミュレートするQ#
description: 個々の qubit レベルで動作するクォンタムプログラムの記述とシミュレーションに関するステップバイステップのチュートリアル
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 10/06/2019
uid: microsoft.quantum.circuit-tutorial
ms.topic: tutorial
no-loc:
- Q#
- $$v
ms.openlocfilehash: 22c79e4e01db1a0d0c291d0dcff81dbfa8df5cd3
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869717"
---
# <a name="tutorial-write-and-simulate-qubit-level-programs-in-q"></a>チュートリアル: Q で qubit レベルのプログラムを記述してシミュレートする\#

個々の qubits で動作する基本的な量子プログラムの作成とシミュレーションに関する、Quantum 開発キットのチュートリアルへようこそ。 

Q#は主に大規模なクォンタムプログラム用の高レベルのプログラミング言語として作成されていますが、特定の qubits に直接対処するクォンタムプログラムの下位レベルを調べる場合にも簡単に使用できます。
の柔軟性に Q# より、ユーザーはこのような抽象化レベルから量子システムにアプローチできます。このチュートリアルでは、qubits 自体について説明します。
具体的には、多くの大きなクォンタムアルゴリズムに不可欠なサブルーチンである[Quantum フーリエ変換](https://en.wikipedia.org/wiki/Quantum_Fourier_transform)の内部を見てみます。

クォンタム情報処理のこの下位ビューは、システムの特定の qubits に対するゲートの順次アプリケーションを表す "[クォンタム回線](xref:microsoft.quantum.concepts.circuits)" の観点からよく説明されていることに注意してください。

したがって、順次適用される単一およびマルチ qubit 操作は、"サーキットダイアグラム" で簡単に表すことができます。
ここでは、 Q# 次のような表現をサーキットとして持つ、3つの-qubit クォンタムの完全変換を実行する操作を定義します。

<br/>
<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

## <a name="prerequisites"></a>前提条件

* 任意の言語および開発環境を使用して、Quantum 開発キットを[インストール](xref:microsoft.quantum.install)します。
* 既に QDK をインストールしている場合は、バージョンが[最新](xref:microsoft.quantum.update)であることを確認する


## <a name="in-this-tutorial-youll-learn-how-to"></a>このチュートリアルでは、次の方法について説明します。

> [!div class="checklist"]
> * クォンタム操作の定義Q#
> * Q#コマンドラインから直接、またはクラシックホストプログラムを使用して操作を呼び出す
> * Qubit 割り当てから測定出力へのクォンタム操作をシミュレートします
> * 操作全体でクォンタムシステムのシミュレートされた wavefunction がどのように変化するかを観察する

Microsoft の Quantum 開発キットでクォンタムプログラムを実行するのは、通常、次の2つの部分で構成されています。
1. プログラム自体は、クォンタムプログラミング言語を使用して実装され、 Q# クォンタムコンピューターまたはクォンタムシミュレーターで実行するために呼び出されます。 次のもので構成されます。 
    - Q#操作: クォンタムレジスタに作用するサブルーチン、および 
    - Q#functions: クォンタムアルゴリズム内で使用される古典サブルーチン。
2. クォンタムプログラムを呼び出すときに使用するエントリポイントと、実行するターゲットコンピューターを指定します。
    これは、コマンドラインから直接行うことも、Python や C# などの従来のプログラミング言語で記述されたホストプログラムを使用して行うこともできます。
    このチュートリアルでは、どの方法を使用するかについて説明します。

## <a name="allocate-qubits-and-define-quantum-operations"></a>Qubits の割り当てとクォンタム操作の定義

このチュートリアルの最初の部分では、 Q# 操作を定義します。この操作では、 `Perform3qubitQFT` 3 つの qubits でクォンタムフーリエ変換を実行します。 

さらに、関数を使用して、 [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) 3 つの qubit システムのシミュレートされた wavefunction が操作間でどのように変化するかを観察します。

最初の手順として、 Q# プロジェクトとファイルを作成します。
この手順は、プログラムの呼び出しに使用する環境によって異なります。詳細については、それぞれの[インストールガイド](xref:microsoft.quantum.install)を参照してください。

ここでは、ファイルのコンポーネントについて順を追って説明しますが、コードは以下の完全なブロックとしても使用できます。

### <a name="namespaces-to-access-other-no-locq-operations"></a>他の操作にアクセスするための名前空間 Q#
ファイル内では、最初に `NamespaceQFT` コンパイラによってアクセスされる名前空間を定義します。
この操作で既存の操作を使用するには Q# 、関連する `Microsoft.Quantum.<>` 名前空間を開きます。

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    // operations go here
}
```

### <a name="define-operations-with-arguments-and-returns"></a>引数と戻り値を使用して操作を定義する
次に、操作を定義し `Perform3qubitQFT` ます。

```qsharp
    operation Perform3qubitQFT() : Unit {
        // do stuff
    }
```

現時点では、この操作は引数を取らず、この例では何---も返されません。この場合、Python では、C# または空のタプルのに類似したオブジェクトを返すことを記述し `Unit` `void` `Tuple[()]` ます。
後で、評価結果の配列を返すようにこの値を変更し、その時点で `Unit` がに置き換えられ `Result[]` ます。 

### <a name="allocate-qubits-with-using"></a>に qubits を割り当てる`using`
この操作では Q# 、最初に次のステートメントを使用して、3つの qubits のレジスタを割り当て `using` ます。

```qsharp
        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

        }
```

では `using` 、qubits は $ \ket $ 状態で自動的に割り当てられ {0} ます。 これを確認するには、とを使用します。これにより [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) 、文字列とシステムの現在の状態がコンソールに出力されます。

> [!NOTE]
> およびの各関数は、 `Message(<string>)` `DumpMachine()` [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics) どちらもコンソールに直接出力されます。 実際のクォンタム計算と同じよう Q# に、では、qubit 状態に直接アクセスすることはできません。
> ただし、では、 `DumpMachine` ターゲットコンピューターの現在の状態が出力されるため、完全な状態シミュレーターと組み合わせて使用すると、デバッグと学習に関する貴重な洞察を得ることができます。


### <a name="applying-single-qubit-and-controlled-gates"></a>シングル qubit および制御ゲートの適用

次に、操作自体を構成するゲートを適用します。
Q#には、名前空間の操作として多くの基本的なクォンタムゲートが既に含まれてい [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) ますが、これらは例外ではありません。 

操作内では、呼び出し Q# 可能なものを呼び出すステートメントが順番に実行されます。
したがって、最初に適用するゲートは、 [`H`](xref:microsoft.quantum.intrinsic.h) 最初の qubit への (Hadamard) です。

<br/>
<img src="../media/qft_firstH.PNG" alt="Circuit diagram for three qubit QFT through first Hadamard" width="120">

レジスタから特定の qubit に操作を適用する (つまり、配列の1つの) 場合は、 `Qubit` `Qubit[]` 標準のインデックス表記を使用します。
そのため、を [`H`](xref:microsoft.quantum.intrinsic.h) レジスタの最初の qubit に適用すると、次のような形式になり `qs` ます。

```qsharp
            H(qs[0]);
```

`H`(Hadamard) ゲートを個々の qubits に適用するだけでなく、QFT 回線は主に制御された回転で構成され [`R1`](xref:microsoft.quantum.intrinsic.r1) ます。
`R1(θ, <qubit>)`一般的な操作では、 {0} qubit の $ \ket $ コンポーネントが変更されず、$ \ket $ コンポーネントに $e ^ {i-シータ} $ の回転が適用され {1} ます。

#### <a name="controlled-operations"></a>制御される操作

Q#を使用すると、1つまたは複数のコントロール qubits に対する操作の実行条件を非常に簡単に指定できます。
一般に、を呼び出しの前にを付けるだけで、 `Controlled` 操作の引数は次のように変更されます。

 `Op(<normal args>)`$ \ から $ `Controlled Op([<control qubits>], (<normal args>))` 。

Control qubits が1つの qubits であっても、配列として指定されている必要があることに注意してください。

の後、 `H` 次のゲートが最初の qubit に作用するゲートであることがわかり `R1` ます (さらに、2番目と3番目のゲートによって制御されます)。

<br/>
<img src="../media/qft_firstqubit.PNG" alt="Circuit diagram for three qubit QFT through first qubit" width="310">

次を使用してこれらを呼び出します。

```qsharp
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));
```

名前空間の関数を使用して、 [`PI()`](xref:microsoft.quantum.math.pi) pi ラジアンの観点から回転を定義していることに注意 [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) してください。
さらに、 `Double` `2.0` 整数で除算する `2` と型エラーがスローされるため、(例:) で除算します。 

> [!TIP]
> `R1(π/2)`と `R1(π/4)` は、 `S` and `T` 演算 (でも) に相当し `Microsoft.Quantum.Intrinsic` ます。


関連 `H` する操作および制御された回転を2番目と3番目の qubits に適用した後、次のようになります。

```qsharp
            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);
```

[`SWAP`](xref:microsoft.quantum.intrinsic.swap)回線を完成させるためにゲートを適用するだけです。

```qsharp
            SWAP(qs[2], qs[0]);
```

このことが必要なのは、クォンタムのフーリエ変換の性質によって qubits が逆順に出力されるためです。そのため、スワップにより、サブルーチンをより大きなアルゴリズムにシームレスに統合できます。

そのため、次の操作に、クォンタムのフーリエ変換の qubit レベルの操作を記述しました Q# 。

<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

ただし、まだ1日に呼び出すことはできません。
この qubits は、割り当てられたときに $ \ket $ という州にいましたが、実際には、私たちが発見したのと {0} Q# 同じ方法 (またはより良いもの) にする必要がありました。

### <a name="deallocate-qubits"></a>Qubits の割り当て解除

[`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine)もう一度を呼び出して操作後の状態を確認し、最後に [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) qubit レジスタに適用して、 {0} 操作が完了する前に qubit を $ \ket $ にリセットします。

```qsharp
            Message("After:");
            DumpMachine();

            ResetAll(qs);
```

すべての割り当て解除された qubits を明示的に $ \ket $ に設定すること {0} は、の基本的な機能です Q# 。これにより、他の操作で同じ qubits (希少リソース) の使用を開始したときに、その状態を正確に知ることができるようになります。
また、これにより、システム内の他の qubits との間では、それらの角度が等しくならないことが保証されます。
割り当てブロックの最後にリセットが実行されない場合は、 `using` ランタイムエラーがスローされます。

完全な Q# ファイルは次のようになります。

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    operation Perform3qubitQFT() : Unit {

        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("After:");
            DumpMachine();

            ResetAll(qs);
        }
    }
}
```


Q#ファイルと操作が完了すると、quantum プログラムを呼び出してシミュレートする準備ができました。

## <a name="execute-the-program"></a>プログラムを実行する

ファイルで操作を定義したので、この操作を呼び出して、 Q# `.qs` 返されたすべてのクラシックデータを観察する必要があります。
ここでは、返されるものはありません (上記の操作によって定義された操作が返されることを思い出して `Unit` ください) が、後で Q# 測定結果 () の配列を返すように操作を変更する場合 `Result[]` は、このことに対処します。

プログラムは、 Q# それを呼び出すために使用される環境全体にわたって普及していますが、そのための方法は当然変わります。 そのため、「コマンドラインアプリケーションからの作業」また Q# は「Python または C# でのホストプログラムの使用」に対応するタブの指示に従ってください。

#### <a name="command-line"></a>[コマンド ライン](#tab/tabid-cmdline)

Q#コマンドラインからプログラムを実行する場合は、ファイルにわずかな変更しか必要あり Q# ません。

`@EntryPoint()`操作の定義の前にある行にを追加するだけです。

```qsharp
    @EntryPoint()
    operation Perform3qubitQFT() : Unit {
        // ...
```

プログラムを実行するには、プロジェクトのフォルダーにあるターミナルを開き、「」と入力します。

```dotnetcli
dotnet run
```

実行すると、次の出力がコンソールに出力され `Message` `DumpMachine` ます。


#### <a name="python"></a>[Python](#tab/tabid-python)

Python ホストファイルを作成 `host.py` します。

ホストファイルは次のように構成されます。 
1. まず、モジュールをインポートし `qsharp` ます。これにより、モジュールローダーが相互運用性のために登録され Q# ます。 
    これにより、 Q# 名前空間 ( `NamespaceQFT` ファイルで定義されているなど Q# ) が Python モジュールとして表示され、そこから操作をインポートでき Q# ます。
2. 次 Q# に、直接呼び出す操作をインポートします。この場合は、--- `Perform3qubitQFT` ます。
    エントリポイントをプログラムにインポートする必要がある Q# (つまり、 _not_ `H` `R1` 他の操作によって呼び出され、 Q# クラシックホストによって呼び出されない、やなどの操作がない) 必要があります。
3. Q#操作または関数をシミュレートする場合は、フォームを使用して `<Q#callable>.simulate(<args>)` `QuantumSimulator()` ターゲットコンピューターで実行します。 

> [!NOTE]
> など、別のコンピューターで操作を呼び出す場合は、単にを `ResourceEstimator()` 使用 `<Q#callable>.estimate_resources(<args>)` します。
> 一般に、 Q# 操作は実行されているコンピューターに依存しませんが、などの一部の機能は `DumpMachine` 動作が異なる場合があります。

4. シミュレーションを実行すると、操作の呼び出しによって、ファイルで定義されている値が返され Q# ます。
    ここでは何も返されませんが、後でこれらの値を割り当てて処理する例を確認できます。
    最終的には、このデータを使用してデータを完成させることができます。

完全なファイルは次のようになり `host.py` ます。

```python
import qsharp
from NamespaceQFT import Perform3qubitQFT

Perform3qubitQFT.simulate()
```

Python ファイルを実行してコンソールに出力すると、以下の `Message` 出力と出力が表示され `DumpMachine` ます。 


#### <a name="c"></a>[C#](#tab/tabid-csharp)

[インストールガイド](xref:microsoft.quantum.install.cs)の手順に従って、C# ホストファイルを作成し、名前をに変更し `host.cs` ます。

C# ホストには、次の4つの部分があります。
1. 量子シミュレーターを構築します。
    次のコードでは、これが変数 `qsim` です。
2. 量子アルゴリズムに必要な引数を計算します。
    この例には何もありません。
3. 量子アルゴリズムを実行します。 
    各 Q# 操作では、同じ名前の C# クラスが生成されます。 
    このクラスには、操作を**非同期に**実行する `Run` メソッドがあります。
    実行が非同期とは、実際のハードウェアでの実行が非同期になるということです。 
    メソッドは非同期であるため `Run` 、メソッドを呼び出し `Wait()` ます。これは、タスクが完了するまで実行をブロックし、同期的に結果を返します。 
4. 返された操作の結果を処理します。
    現時点では、操作は何も返しません。


```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                Perform3QubitQFT.Run(qsim).Wait();
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}

```
アプリケーションを実行します。出力は次のようになります。
プログラムは、キーを押した後に終了します。
***

```Output
Initial state |000>:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
After:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
```

完全な状態シミュレーターで呼び出されると、は、 `DumpMachine()` クォンタム状態の wavefunction の複数の表現を提供します。 $N $-qubit システムの考えられる状態は、それぞれに対応する複合係数 (単なる振幅とフェーズ) を持つ、$ 2 ^ n $ の計算ベースの状態で表すことができます。
計算ベースの状態は、$---$n 長さのすべての可能なバイナリ文字列に対応します。これは、 {0} {1} 各バイナリ数字が個々の qubit に対応する、qubit 州 $ \ket $ と $ \ket $ のすべての可能な組み合わせです。

最初の行は、対応する qubits の Id を持つコメントを有意な順序で提供します。
Qubit が `2` "最も重要" であるということは、基本的な状態ベクトル $ \ket{i} $ のバイナリ表現で、qubit の状態が左端の数字に対応することを意味し `2` ます。 たとえば、$ \ket {6} = \ket {110} $ は qubits で、$ `2` `1` \ket {1} $ と qubits の両方で `0` $ \ket {0} $ にあります。


残りの行は、デカルト形式と極座標形式の両方で、basis 状態ベクター $ \ket{i} $ を測定する確率の振幅を示しています。
入力状態 $ \ket $ の最初の行について詳しく説明し {000} ます。
* **`|0>:`** この行は、計算基準の状態に対応してい `0` ます (初期の状態の後に割り当てられた値が $ \ket $ であることを前提として {000} います。これは、この時点での確率の振幅が唯一の状態であることを想定しています)。
* **`1.000000 +  0.000000 i`**: デカルト形式の確率の振幅。
* **` == `**: 符号は、 `equal` 両方の同等の表現を分離します。
* **`********************`**: 大きさをグラフィカルに表示します。の数は、 `*` この状態ベクターを測定する確率に比例します。 
* **`[ 1.000000 ]`**: マグニチュードの数値
* **`    ---`**: 振幅のフェーズをグラフィカルに表示します。
* **`[ 0.0000 rad ]`**: フェーズの数値 (ラジアン)。

大きさとフェーズの両方がグラフィック表示で表示されます。 大きさの表現は簡単です。の棒が表示され、 `*` 確率が高いほど、棒が大きくなります。 フェーズについては、「[テストおよびデバッグ:](xref:microsoft.quantum.guide.testingdebugging#dump-functions)山の範囲に基づいて可能なシンボル表現のダンプ関数」を参照してください。


そのため、この出力は、プログラミングされたゲートによって状態が変換されたことを示しています。

$ $ \ket{\psi} \_ {initial} = \ket {000} $ $

to 

$ $ \begin{align} \ket{\psi} \_ {final} &= \ frac {1} {\ sqrt {8} } \ 左 (\ket {000} + \ket {001} + \ket + \ket {010} {011} + \ket {100} + \ket {101} + \ket {110} + \ket {111} /right) \\ \\ &= \ frac {1} {\ sqrt{2 ^ n}} \ sum \_ {j = 0} ^ {2 ^ n-1} \ket{j}, \end{align} $ $

これは、3つの qubit フーリエ変換の動作です。 

他の入力状態にどのような影響があるかを知りたい場合は、変換前に qubit 操作を適用することをお勧めします。

## <a name="adding-measurements"></a>測定値の追加

残念ながら、量子力学の土台として、実際の quantum システムがこのような機能を持つことができないことがわかりました `DumpMachine` 。 代わりに、測定値を使用して情報を抽出することが強制されています。これは、完全なクォンタム状態を提供するだけでなく、システム自体を大幅に変更することもできます。
クォンタム測定にはさまざまな種類がありますが、1つの qubits で最も基本的な射影測定に焦点を当てます。
測定値に基づいて (計算基準 $ \{ \ket {0} 、\ket {1} \} $ など)、qubit 状態は---測定された基準のいずれかの状態に投影されるので、この2つの間の法則は破棄されます。

プログラム内で測定を実装するには、 Q# `M` 型を返す操作 (から) を使用し `Microsoft.Quantum.Intrinsic` `Result` ます。

まず、では `Perform3QubitQFT` なく、測定結果の配列を返すように操作を変更 `Result[]` `Unit` します。

```qsharp
    operation Perform3QubitQFT() : Result[] {
```

#### <a name="define-and-initialize-result-array"></a>配列の定義と初期化 `Result[]`

(つまり、ステートメントの前に) qubits を割り当てる前に `using` 、次の長さ3の配列を宣言してバインドし `Result` ます (各 qubits に1つ)。 

```qsharp
        mutable resultArray = new Result[3];
```

前にキーワードを付ける `mutable` と、コードの後で変数を再バインドできるようになり `resultArray` ます。たとえば、測定結果を追加するときに、---ます。

#### <a name="perform-measurements-in-a-for-loop-and-add-results-to-array"></a>ループで測定を実行 `for` し、結果を配列に追加する

ブロック内のフーリエ変換操作の後 `using` に、次のコードを挿入します。

```qsharp
            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }
```
[`IndexRange`](xref:microsoft.quantum.arrays.indexrange)配列 (qubits の配列など) で呼び出される関数は、 `qs` 配列のインデックスの範囲を返します。 ここでは、ループで使用して、 `for` ステートメントを使用して各 qubit を順番に測定し `M(qs[i])` ます。
各測定 `Result` 型 ( `Zero` または `One` ) は、の対応するインデックス位置に、 `resultArray` 更新と再割り当てのステートメントを使用して追加されます。

> [!NOTE]
> このステートメントの構文はに固有です Q# が、 `resultArray[i] <- M(qs[i])` F # や R などの他の言語で見られるような変数の再割り当てに相当します。

キーワードは、 `set` を使用してバインドされた変数を再割り当てするために常に使用され `mutable` ます。

#### <a name="return-resultarray"></a>返し`resultArray`

3つの qubits がすべて測定され、結果がに追加されたので `resultArray` 、以前と同じように qubits をリセットし、割り当てを解除します。
`using`ブロックの終了後に、を挿入します。

```qsharp
        return resultArray;
```
を実行すると、最終的に操作の出力が返されます。 

### <a name="understanding-the-effects-of-measurement"></a>測定の効果について

`DumpMachine`測定の前後に状態を出力するように関数の配置を変更してみましょう。
最終的な操作コードは次のようになります。 

```qsharp
    operation Perform3QubitQFT() : Result[] {

        mutable resultArray = new Result[3];

        using (qs = Qubit[3]) {

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("Before measurement: ");
            DumpMachine();

            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }

            Message("After measurement: ");
            DumpMachine();

            ResetAll(qs);
        }
        return resultArray;
    }
}
```

コマンドラインから作業している場合、返された配列は、実行の終了時にコンソールに直接出力されます。
それ以外の場合は、返された配列を処理するようにホストプログラムを更新します。

#### <a name="command-line"></a>[コマンド ライン](#tab/tabid-cmdline)

返される配列についての理解を深めるために、コンソールに出力され `Message` Q# ます。次のステートメントの直前に、ファイルにもう1つを追加でき `return` ます。

```qsharp
        Message("Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
        return resultArray;
```

プロジェクトを実行すると、出力は次のようになります。

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]
```

#### <a name="python"></a>[Python](#tab/tabid-python)

Python プログラムを次のように更新します。

```python
import qsharp
from NamespaceQFT import Perform3QubitQFT

measurementResult = Perform3QubitQFT.simulate()
print("\n")
print("Measured post-QFT state: [qubit0, qubit1, qubit2]")
print(measurementResult)

# reversing order to show corresponding basis state in binary form
binaryCompBasisState = ""
for i in measurementResult:
    binaryCompBasisState = str(i) + binaryCompBasisState
print("Corresponding basis state in binary:")
print("|" + binaryCompBasisState + ">")
```

ファイルを実行すると、出力は次のようになります。

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[1, 1, 0]

Corresponding basis state in binary:
|011>
```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

操作が結果を返すようになったので、メソッド呼び出しを `Wait()` プロパティのフェッチに置き換え `Result` ます。 これでも、前に説明したのと同じ同期が得られます。この値を直接変数にバインドすることができ `measurementResult` ます。

```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                var measurementResult = Perform3QubitQFT.Run(qsim).Result;
                System.Console.WriteLine(
                    $"Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
                System.Console.WriteLine(
                    measurementResult);

                // reversing order to show corresponding basis state in binary form
                string binaryCompBasisState = String.Empty;

                foreach (Result i in measurementResult)
                {
                    string iString = i.ToString();
                    binaryCompBasisState = iString + binaryCompBasisState;
                }
                binaryCompBasisState = "|" + binaryCompBasisState + ">";
                System.Console.WriteLine(
                    $"Corresponding basis state in binary:");
                System.Console.WriteLine(
                    binaryCompBasisState);
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}
```

プロジェクトを実行すると、出力は次のようになります。

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]

Corresponding basis state in binary:
|ZeroOneOne>

Press any key to continue...
```
***

この出力は、次のようないくつかの点を示しています。
1. 返された結果を事前測定値と比較する `DumpMachine` と、それ以降の状態に関する QFT 法則は明確に示さ_れません_。
    測定値で返されるのは、システムの wavefunction のその状態の振幅によって決まります。
2. この後の測定値から、測定値によって `DumpMachine` 状態が_変更_され、基準値に対応する1つの基礎状態に法則の初期状態から投影されます。

この操作を何度も繰り返す場合は、結果の統計情報が表示されます。これにより、各ショットに対してランダムな結果が得られる、QFT の状態の法則が均等に重み付けされます。
_ただし_、非効率的で不完全もありませんが、これによって、基本的な状態の相対的な振幅のみが再現されます。
後者はこの例では問題ではありませんが、QFT に対するより複雑な入力が $ \ket $ に指定されている場合は、相対フェーズが表示され {000} ます。

#### <a name="partial-measurements"></a>部分測定 
レジスタの一部の qubits だけを測定してシステムの状態に影響を与える方法を調べるには、 `for` ループ内で、測定行の後に次のコードを追加します。
```qsharp
                let iString = IntAsString(i);
                Message("After measurement of qubit " + iString + ":");
                DumpMachine();
```

関数にアクセスするに `IntAsString` は、追加する必要があることに注意してください。 
```qsharp
    open Microsoft.Quantum.Convert;
```
残りの名前空間ステートメントを使用し `open` ます。

結果の出力では、各 qubit が測定されたときに、サブスペースへの段階的な投影が表示されます。


## <a name="use-the-no-locq-libraries"></a>ライブラリを使用する Q#
概要で説明したように、のほとんどの機能は、 Q# 個々の qubits を処理する心配をすることができるという事実を備えています。
実際には、フルスケールの適用可能なクォンタムプログラムを開発する場合は、 `H` 特定のローテーションの前または後に操作が実行されるかどうかを心配します。 

これらのライブラリには、 Q# [qft](xref:microsoft.quantum.canon.qft)操作が含まれています。この操作は、任意の数の qubits に対して実行して適用することができます。
試してみるには、ファイル内にと同じ内容の新しい操作を定義し Q# `Perform3QubitQFT` ます。ただし、最初から2行目までのすべてのものを `H` `SWAP` 置き換えます。
```qsharp
            let register = BigEndian(qs);    //from Microsoft.Quantum.Arithmetic
            QFT(register);                   //from Microsoft.Quantum.Canon
```
最初の行は、 [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) qubits の割り当てられた配列の式を作成するだけです `qs` 。これは、 [qft](xref:microsoft.quantum.canon.qft)操作が引数として受け取るものです。
これは、レジスタ内の qubits のインデックスの順序に対応します。

これらの操作にアクセスできるようにするには、 `open` ファイルの先頭にそれぞれの名前空間のステートメントを追加し Q# ます。
```qsharp
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Arithmetic;
```

次に、新しい操作の名前 (例:) を呼び出すようにホストプログラムを調整 `PerformIntrinsicQFT` し、whirl を指定します。

ライブラリ操作を使用する実際の利点を確認するには Q# 、次のように qubits の数を変更し `3` ます。
```qsharp
        mutable resultArray = new Result[4]; 

        using (qs = Qubit[4]) {
            //...
        }
```
これにより、指定された数の qubits に対して適切な QFT を適用できます。これにより、新しい操作や各 qubits のローテーションについて心配する必要がなく `H` なります。

Qubits の数を増やすと、実際の量子ハードウェアに進むために、クォンタムシミュレーターの実行時間が大幅に長くなることに注意してください---













