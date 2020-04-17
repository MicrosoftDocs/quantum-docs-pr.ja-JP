---
title: Q# を使った量子の基本
description: Q# で量子プログラムを作成する方法について説明します。 Quantum Development Kit (QDK) を使用してベル状態アプリケーションを開発する
author: natke
ms.author: nakersha
ms.date: 10/07/2019
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 8d3b2d7c8da39a961f4eedcc5989ad3a1e134ade
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "77906731"
---
# <a name="quantum-basics-with-q"></a>Q# を使った量子の基本

このクイックスタートでは、量子ビットの操作および測定を行い、重ね合わせともつれの効果を示す、Q# プログラムの作成方法を説明します。  このガイドでは、QDK をインストールし、プログラムをビルドして、そのプログラムを量子シミュレーターで実行する方法を示します。  

量子のもつれを示すため、Bell というアプリケーションを記述します。  Bell という名前は、ベル状態を表しています。これは、量子の重ね合わせともつれの最も簡単な例を表すために使用される、2 つの量子ビットの特定の量子の状態です。 

## <a name="pre-requisites"></a>前提条件

コーディングを開始する準備ができたら、続行する前に次の手順を実行してください。 

* 任意の言語および開発環境を使用して、Quantum Development Kit を[インストール](xref:microsoft.quantum.install)する
* 既に QDK をインストールしている場合は、バージョンが[最新](xref:microsoft.quantum.update)であることを確認する

QDK をインストールしなくても、説明を読み進めることで Q# プログラミング言語の概要と量子コンピューティングの最初の概念を理解することができます。

## <a name="demonstrating-qubit-behavior-with-q"></a>Q# を使った量子ビットの動作のデモ

簡単な[量子ビットの定義](xref:microsoft.quantum.overview.what#the-qubit)を思い出してください。  従来のビットでは単一のバイナリ値 (0、1 など) が保持されるのに対し、量子ビットの状態は同時に 0 と 1 の**重ね合わせ**になることができます。  概念的には、量子ビットは空間内の方向 (ベクトルとも呼ばれます) と考えられます。  量子ビットは、任意の方向にすることができます。 2 つの**従来の状態**とは、0 を測定する確率が 100% になる方向と、1 を測定する確率が 100% になる方向のことです。  この表現は、[ブロッホ球](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere)によってより正式に視覚化されます。


測定の動作により、2 進法の結果が生成され、量子ビットの状態が変わります。 測定では、0 または 1 のバイナリ値が生成されます。  量子ビットは重ね合わせ (あらゆる方向にある) の状態から古典的状態のいずれかになります。  その後、介在する操作なしで同じ測定を繰り返すと、同じ 2 進数の結果が生成されます。  

複数の量子ビットは**もつれさせる**ことができます。 もつれのある 1 つの量子ビットを測定すると、もう一方の量子ビットの状態に関する知識も更新されます。

これで、Q# がこの動作を表現する方法を説明できるようになりました。  考えられる最も単純なプログラムから始め、量子の重ね合わせと量子のもつれを表すように構築します。

## <a name="setup"></a>セットアップ

Microsoft の Quantum Development Kit を使用して開発されたアプリケーションは、次の 2 つの部分で構成されます。

1. 1 つ以上の量子アルゴリズム。Q# 量子プログラミング言語を使用して実装します。
1. ホストプログラム。Python や C# などのプログラミング言語で実装します。メイン エントリ ポイントとして機能し、Q# 操作を呼び出して量子アルゴリズムを実行します。

#### <a name="python"></a>[Python](#tab/tabid-python)

1. アプリケーションを格納する場所を選択します。

1. `Bell.qs`という名前でファイルを作成します。 このファイルには、Q# コードが含まれます。

1. `host.py`という名前でファイルを作成します。 このファイルには、Python ホスト コードが含まれます。

#### <a name="c-command-line"></a>[C# コマンド ライン](#tab/tabid-csharp)

1. 新しい Q# プロジェクトを作成する

    ```bash
    dotnet new console -lang Q# --output Bell
    cd Bell
    ```

    `.csproj` ファイル、`Operations.qs` という名前の Q# ファイル、および `Driver.cs` という名前のホスト プログラム ファイルが表示されます。

1. Q# ファイルの名前を変更する

    ```bash
    mv Operation.qs Bell.qs
    ```

#### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs2019)

1. 新しいプロジェクトを作成する

   * Visual Studio を開きます
   * **[ファイル]** メニューで、 **[新規作成]**  ->  **[プロジェクト...]** の順に選択します
   * プロジェクト テンプレート エクスプローラーの検索フィールドに「`Q#`」と入力し、`Q# Application` のテンプレートを選択します
   * プロジェクトに `Bell` という名前を付けます

1. Q# ファイルの名前を変更する

   * **ソリューション エクスプローラー**に移動します
   * `Operations.qs` ファイルを右クリックします
   * 名前を `Bell.qs` に変更します

* * *

## <a name="write-a-q-operation"></a>Q# 操作を記述する

私たちの目標は、Q# を使って量子ビットを操作してその状態を変更するための、特定の量子の状態にある 2 つの量子ビットを準備し、重ね合わせともつれの効果を示すことです。 ここでは、量子ビットの状態や操作、測定について示しつつ、少しずつ構築していきます。

**概要:** 以下に示す最初のコードは、Q# で量子ビットを操作する方法を示しています。  ここでは、量子ビットの状態を変換する 2 つの操作、`M` と `X` を紹介します。 

このコード スニペットでは、量子ビットをパラメーターと見なす操作 `Set` が定義されています。もう 1 つのパラメーター `desired` は量子ビットが目的とする状態を表しています。  操作 `Set` は、操作 `M` を使用して、量子ビットに対する測定を実行します。  Q# では量子ビットの測定では常に `Zero` または `One` のどちらかが返されます。  測定値が目的の値と等しくない値を返す場合は、量子ビットを "反転" させます。つまり、`X` 操作を実行します。これにより、量子ビットの状態は、測定で `Zero` と `One` を返す確率が逆になる新しい状態に変更されます。  `Set` 操作の効果を示すため、`TestBellState` 操作を追加します。  この操作では、`Zero` または `One` を入力として受け取り、その入力で `Set` 操作を何回か呼び出して、`Zero` が量子ビットの測定から返された回数と `One` が返された回数をカウントします。 当然ながら、`TestBellState` 操作のこの最初のシミュレーションでは、`Zero` がパラメーターとして設定された量子ビットのすべての測定で `Zero` を返し、`One` がパラメーターとして設定された量子ビットのすべての測定で `One` を返すことが想定されます。  さらに、重ね合わせともつれを示すコードを `TestBellState` に追加します。


### <a name="q-operation-code"></a>Q# 操作コード

1. Bell.qs ファイルの内容を次のコードに置き換えます。

    ```qsharp
    namespace Quantum.Bell {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation Set(desired : Result, q1 : Qubit) : Unit {
            if (desired != M(q1)) {
                X(q1);
            }
        }
    }
    ```

    この操作により、量子ビットが従来の状態に設定されます。つまり、`Zero` が 100% 返されるか、`One` が 100% 返されるかのどちらかです。  `Zero` および `One` は、量子ビットの測定結果として考えられる 2 とおりの結果を表す定数です。

    `Set` 操作で量子ビットが測定されます。
    量子ビットが目的の状態にある場合は、`Set` をそのままにしておきます。それ以外の場合は、`X` 操作を実行することで量子ビットの状態が目的の状態に変更されます。

### <a name="about-q-operations"></a>Q# 操作について

Q# 操作は、量子のサブルーチンです。 つまり、量子操作を含む呼び出し可能なルーチンです。

操作の引数は、かっこ内にタプルとして指定します。

操作の戻り値の型は、コロンの後に指定します。 この場合、`Set` 操作には戻り値がないため、`Unit` を返すように設定されています。 これは、F# における `unit` の Q# 版にあたります。C# では `void`、Python では空のタプル (`Tuple[()]`) とほぼ同じです。

最初の Q# 操作では、次の 2 つの量子操作を使用しました。

* 量子ビットの状態を測定する [M](xref:microsoft.quantum.intrinsic.m) 操作
* 量子ビットの状態を反転させる [X](xref:microsoft.quantum.intrinsic.x) 操作

量子操作により、量子ビットの状態が変換されます。 従来の論理ゲートの類義語として、量子操作の代わりに、量子ゲートが話題になることがあります。 これは初期の量子コンピューティングでは、アルゴリズムが単なる理論上の構成要素であり、古典コンピューティングの回路図に似た図で視覚化されていたことに端を発します。

### <a name="add-q-test-code"></a>Q# テスト コードの追加

1. `Bell.qs` ファイルの名前空間内、`Set` 操作の終了後に次の操作を追加します。

    ```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                Set(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            Set(Zero, qubit);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
    ```

    この操作 (`TestBellState`) では、`count` 回ループし、指定された `initial` 値を量子ビットに設定して、結果を測定 (`M`) します。 これにより、測定した 0 と 1 の数がいくつあるかの統計情報が収集され、呼び出し元に返されます。 ここでは、もう 1 つの必要な操作を実行しています。 他のユーザーがこの量子ビットに既知の状態を割り当てることができるよう、終了する前にこの量子ビットを既知の状態 (`Zero`) にリセットします。 この操作は、`using` ステートメントに必須です。

### <a name="about-variables-in-q"></a>Q# の変数について

既定では、Q# の変数は不変です。バインド後に変数の値を変更することはできません。 `let` キーワードは、不変変数のバインドを示すために使用します。 操作の引数は常に不変です。

先ほどの例の `numOnes` のように、値を変更できる変数が必要な場合は、`mutable` キーワードを使用して変数を宣言できます。 可変変数の値は、`set` ステートメントを使用して変更できます。

どちらの場合も、変数の型はコンパイラによって推論されます。 Q# では、変数に型の注釈は必要ありません。

### <a name="about-using-statements-in-q"></a>Q# の `using` ステートメントについて

`using` ステートメントも Q# に特有です。 これは、コードのブロックで使用するために量子ビットを割り当てる場合に使用されます。 Q# では、複雑なアルゴリズムの有効期間全体にわたってリソースが固定されるのではなく、すべての量子ビットが動的に割り当てられ、解放されます。 `using` ステートメントは、ブロックの最初で一連の量子ビットを割り当て、ブロックの最後でその量子ビットを解放します。

## <a name="create-the-host-application-code"></a>ホスト アプリケーション コードの作成

#### <a name="python"></a>[Python](#tab/tabid-python)

1. `host.py` ファイルを開き、次のコードを追加します。

    ```python
    import qsharp

    from qsharp import Result
    from Quantum.Bell import TestBellState

    initials = (Result.Zero, Result.One)

    for i in initials:
      res = TestBellState.simulate(count=1000, initial=i)
      (num_zeros, num_ones) = res
      print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4}')
    ```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

1. `Driver.cs` ファイルの内容を次のコードに置き換えます。

    ```csharp
    using System;

    using Microsoft.Quantum.Simulation.Core;
    using Microsoft.Quantum.Simulation.Simulators;

    namespace Quantum.Bell
    {
        class Driver
        {
            static void Main(string[] args)
            {
                using (var qsim = new QuantumSimulator())
                {
                    // Try initial values
                    Result[] initials = new Result[] { Result.Zero, Result.One };
                    foreach (Result initial in initials)
                    {
                        var res = TestBellState.Run(qsim, 1000, initial).Result;
                        var (numZeros, numOnes) = res;
                        System.Console.WriteLine(
                            $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4}");
                    }
                }

                System.Console.WriteLine("Press any key to continue...");
                Console.ReadKey();
            }
        }
    }
    ```

#### [](#tab/tabid-vs2019)

* * *

### <a name="about-the-host-application-code"></a>ホスト アプリケーション コードについて

#### <a name="python"></a>[Python](#tab/tabid-python)

Python ホスト アプリケーションには、次の 3 つの部分があります。

* 量子アルゴリズムに必要な引数を計算します。 この例では、`count` は 1000 に固定され、`initial` が量子ビットの初期値になっています。
* インポートした Q# 操作の `simulate()` メソッドを呼び出し、量子アルゴリズムを実行します。
* 操作の結果を処理します。 この例では、`res` が操作の結果を受け取ります。 ここでの結果は、シミュレーターが測定した 0 の数 (`num_zeros`) と 1 の数 (`num_ones`) のタプルになります。 2 つのフィールドを取得するためにタプルを分解し、結果を出力します。

#### <a name="c"></a>[C#](#tab/tabid-csharp)

C# ホスト アプリケーションには、次の 4 つの部分があります。

* 量子シミュレーターを構築します。 この例では、`qsim` がシミュレーターです。
* 量子アルゴリズムに必要な引数を計算します。 この例では、`count` は 1000 に固定され、`initial` が量子ビットの初期値になっています。
* 量子アルゴリズムを実行します。 各 Q# 操作によって、同じ名前の C# クラスが生成されます。 このクラスには、操作を**非同期に**実行する `Run` メソッドがあります。 実行が非同期とは、実際のハードウェアでの実行が非同期になるということです。 `Run` メソッドは非同期であるため、`Result` プロパティを取得しています。これにより、タスクが完了して結果を同期的に返すまで実行がブロックされます。
* 操作の結果を処理します。 この例では、`res` が操作の結果を受け取ります。 ここでの結果は、シミュレーターが測定した 0 の数 (`numZeros`) と 1 の数 (`numOnes`) のタプルになります。 これが C# の ValueTuple として返されます。 2 つのフィールドを取得するためにタプルを分解し、結果を出力し、キーが押されるまで待機します。

#### [](#tab/tabid-vs2019)

* * *

## <a name="build-and-run"></a>ビルドおよび実行

#### <a name="python"></a>[Python](#tab/tabid-python)

1. ターミナルで次のコマンドを実行します。

    ```
    python host.py
    ```

    このコマンドは、Q# 操作をシミュレートするホスト アプリケーションを実行します。

結果は次のようになります。

```Output
Init:0    0s=1000 1s=0   
Init:1    0s=0    1s=1000
```

#### <a name="command-line--visual-studio-code"></a>[コマンドライン/Visual Studio Code](#tab/tabid-csharp)

1. ターミナルで次のように実行します。

    ```bash
    dotnet run
    ```

    このコマンドは、必要なすべてのパッケージを自動的にダウンロードし、アプリケーションをビルドしてから、それをコマンド ラインで実行します。

1. または、**F1** キーを押してコマンド パレットを開き、 **[デバッグ]、[デバッグなしで開始]** の順に選択します。
プログラムを起動する方法を記述した新しい ``launch.json`` ファイルを作成するように求められる場合があります。
既定の ``launch.json`` は、ほとんどのアプリケーションで適切に動作します。

結果は次のようになります。

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

#### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs2019)

1. `F5` を押すだけで、プログラムがビルドされて実行されます。

結果は次のようになります。

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

プログラムは、キーを押した後に終了します。

* * *

## <a name="prepare-superposition"></a>重ね合わせ状態を作成する

**概要** では、Q# が重ね合わせで量子ビットをどのように配置するかを見てみましょう。  量子ビットの状態は、0 と 1 の重ね合わせにできることを思い出してください。  これを行うには、`Hadamard` 操作を使用します。 量子ビットが従来の状態のいずれか (測定で常に `One` または `Zero` を返す) である場合、`Hadamard` (`H`) 操作によって、量子ビットの測定で 50% の `Zero` および 50% の `One` を返す状態に量子ビットが配置されます。  概念上、量子ビットは `Zero` と `One` の中間にあると考えることができます。  ここで、`TestBellState` 操作をシミュレートすると、測定後の結果は、ほぼ同数の `Zero` と `One` を返します。  

まず、量子ビットを反転してみます (量子ビットが `Zero` の状態にある場合は `One` になり、その逆も同様になります)。 これは、`TestBellState` で測定する前に `X` 操作を実行することで実現されます。

```qsharp
X(qubit);
let res = M(qubit);
```

これで結果 (`F5`を押した後) は逆転します。

```Output
Init:Zero 0s=0    1s=1000
Init:One  0s=1000 1s=0
```

ただし、これまでに説明したものはすべて従来型の操作です。 量子的な結果を取得してみましょう。 必要なのは、先ほどの実行の `X` 操作を `H` すなわち Hadamard 操作に置き換えることだけです。 これは、量子ビットを 0 から 1 まで完全に反転させるのではなく、半分だけ反転します。 `TestBellState` の行を置き換えると、次のようになります。

```qsharp
H(qubit);
let res = M(qubit);
```

結果はさらに興味深いものになります。

```Output
Init:Zero 0s=484  1s=516
Init:One  0s=522  1s=478
```

測定するたびに、従来型の値が要求されますが、量子ビットは 0 と 1 の中間にあるため、(統計的に) 半分が 0、半分が 1 になります。 これは__重ね合わせ__と呼ばれる現象で、これによって初めて量子状態を実際に観測できます。

## <a name="prepare-entanglement"></a>もつれ状態を作成する

**概要:** では、Q# がどのように量子ビットのもつれを表現するかを見てみましょう。  まず、最初の量子ビットを初期状態に設定してから、`H` 操作を使用してそれを重ね合わせに配置します。  次に、最初の量子ビットを測定する前に、Controlled-Not を表す新しい操作 (`CNOT`) を使用します。  2 つの量子ビットに対してこの操作を実行した結果、最初の量子ビットが `One` である場合には 2 番目の量子ビットが反転されます。  これで、2 つの量子ビットがもつれ状態になります。  最初の量子ビットの統計情報は変わっていませんが (測定後、50-50 の確率で `Zero` または `One`)、2 番目の量子ビットを測定すると、最初の量子ビットを測定した結果と__常に__同じになります。 この `CNOT` が 2 つの量子ビットをもつれさせ、片方に何かが起きると、もう片方にも同じことが起こるようになっています。 測定を反対にしても (最初の量子ビットの前に 2 番目の量子ビットを測定する)、同じことが起こります。 最初の測定値はランダムであり、2 回目の測定値は最初に検出されたものと完全に一致します。

まず、`TestBellState` で 1 つではなく 2 つの量子ビットを割り当てる必要があります。

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

これにより、`TestBellState` で測定 (`M`) する前に、新しい操作 (`CNOT`) を追加できます。

```qsharp
Set(initial, q0);
Set(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

最初の量子ビットを初期化するために別の `Set` 操作を追加し、開始時に常に `Zero` 状態になるようにしました。

また、2 番目の量子ビットを解放する前にリセットする必要があります。

```qsharp
Set(Zero, q0);
Set(Zero, q1);
```

完全なルーチンは、次のようになります。

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set (initial, q0);
                Set (Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

これを実行すると、以前とまったく同じ 50-50 の結果が得られます。 しかし、ここで興味深いのは、2 番目の量子ビットが測定される最初の量子ビットに対してどのように反応するかです。 この統計情報は、新しいバージョンの `TestBellState` の操作で追加します。

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set(initial, q0);
                Set(Zero, q1);

                H(q0);
                CNOT(q0, q1);
                let res = M(q0);

                if (M(q1) == res) {
                    set agree += 1;
                }

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes, agree);
    }
```

新しい戻り値 (`agree`) は、最初の量子ビットの測定値が 2 番目の量子ビットの測定値と一致した回数を追跡します。 また、ホスト アプリケーションを適切に更新する必要があります。

#### <a name="python"></a>[Python](#tab/tabid-python)

```python
import qsharp

from qsharp import Result
from Quantum.Bell import TestBellState

initials = {Result.Zero, Result.One} 

for i in initials:
    res = TestBellState.simulate(count=1000, initial=i)
    (num_zeros, num_ones, agree) = res
    print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4} agree={agree: <4}')
```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

```csharp
            using (var qsim = new QuantumSimulator())
            {
                // Try initial values
                Result[] initials = new Result[] { Result.Zero, Result.One };
                foreach (Result initial in initials)
                {
                    var res = TestBellState.Run(qsim, 1000, initial).Result;
                    var (numZeros, numOnes, agree) = res;
                    System.Console.WriteLine(
                        $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4} agree={agree,-4}");
                }
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
```

#### [](#tab/tabid-vs2019)

* * *

これを実行すると、驚くような結果が得られます。

```Output
Init:Zero 0s=499  1s=501  agree=1000
Init:One  0s=490  1s=510  agree=1000
```

概要で述べたように、最初の量子ビットの統計情報は変わっていませんが (50-50 の確率で 0 または 1)、2 番目の量子ビットを測定すると、最初の量子ビットを測定した結果と__常に__同じになります。これは、もつれ状態にあるからです。

これで、最初の量子プログラムが作成できました。

## <a name="whats-next"></a>次の操作

[グローバーの検索](xref:microsoft.quantum.quickstarts.search)のクイックスタートでは、最も人気のある量子コンピューティング アルゴリズムの 1 つである、グローバーの検索をビルドして実行する方法を示しています。また、量子コンピューティングに関する実際の問題を解決するために使用できる Q# プログラムの優れた例を提示しています。  

「[Get Started with the Quantum Development Kit](xref:microsoft.quantum.welcome)」(Quantum Development Kit の概要) では、Q# と量子コンピューティングのその他の学習方法も紹介しています。

