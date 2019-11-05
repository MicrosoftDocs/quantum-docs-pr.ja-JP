---
title: 量子シミュレーターとホスト アプリケーション | Microsoft Docs
description: 従来型のコンピューティング .NET 言語 (通常 C# または Q#) を使用して量子シミュレーターを実行する方法について説明します。
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines
ms.openlocfilehash: 14aed75ed0ed192f88699b1c7dbacfae23f74642
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442229"
---
# <a name="quantum-simulators-and-host-applications"></a>量子シミュレーターとホスト アプリケーション

## <a name="what-youll-learn"></a>ここでは、次の内容について学習します

> [!div class="checklist"]
> * 量子アルゴリズムの実行方法
> * このリリースに含まれる量子シミュレーターについて
> * 量子アルゴリズムの C# ドライバーを記述する方法

## <a name="the-quantum-development-kit-execution-model"></a>Quantum Development Kit の実行モデル

[量子プログラムを記述する](xref:microsoft.quantum.write-program)方法に関する記事では、`QuantumSimulator` オブジェクトをアルゴリズム クラスの `Run` メソッドに渡すことによって、量子アルゴリズムを実行しました。
`QuantumSimulator` クラスは、`Teleport` の実行とテストに最適な量子状態ベクトルを完全にシミュレートすることで、量子アルゴリズムを実行します。
量子状態ベクトルの詳細については、[概念に関するガイド](xref:microsoft.quantum.concepts.intro)を参照してください。

他のターゲット コンピューターを使用して、量子アルゴリズムを実行することもできます。
このコンピューターは、アルゴリズムに対して量子プリミティブを実装する役割を担います。
これには、H、CNOT、Measure などのプリミティブ操作だけでなく、量子ビットの管理と追跡も含まれます。
異なるクラスの量子コンピューターは、同じ量子アルゴリズムの異なる実行モデルを表します。

量子コンピュータ－は、種類に応じてこのようなプリミティブの異なる実装を行うことができます。
たとえば、開発キットに含まれている量子コンピューターのトレース シミュレーターは、シミュレーション一切行いません。
代わりに、アルゴリズムのゲート、量子ビット、およびその他のリソースの使用状況を追跡します。

### <a name="quantum-machines"></a>量子コンピューター

今後、他の種類のシミュレーションや、トポロジカル量子コンピューターでの実行をサポートするために、追加の量子コンピューター クラスを定義する予定です。
基になるコンピューターの実装を変更してもアルゴリズムが一定に保たれるようにすることで、シミュレーションのアルゴリズムのテストとデバッグが簡単になり、アルゴリズムが変更されていないという確信を持って実際のハードウェアで実行できます。

### <a name="whats-included-in-this-release"></a>このリリースの新機能は次のとおりです

このリリースの量子開発者キットには、いくつかの量子コンピューター クラスが含まれています。
すべてのクラスは、`Microsoft.Quantum.Simulation.Simulators` 名前空間で定義されています。

* `QuantumSimulator` クラスの[完全状態ベクトル シミュレーター](xref:microsoft.quantum.machines.full-state-simulator)。
* `ResourcesEstimator` クラスの[簡易リソース推定機能](xref:microsoft.quantum.machines.resources-estimator)を使用すると、量子アルゴリズムを実行するために必要なリソースを最上位レベルで分析できます。
* `QCTraceSimulator` クラスの[トレース ベースのリソース推定機能](xref:microsoft.quantum.machines.qc-trace-simulator.intro)を使用すると、アルゴリズムの呼び出しグラフ全体におけるリソース消費の高度な分析を実行できます。
* `ToffoliSimulator` クラスの [Toffoli シミュレーター](xref:microsoft.quantum.machines.toffoli-simulator)。

## <a name="writing-a-host-application"></a>ホストアプリケーションを作成する

[量子プログラムを記述する方法](xref:microsoft.quantum.write-program)に関する記事では、テレポート アルゴリズムの単純な C# ドライバーを記述しました。 C# ドライバーには主に次の 4 つの目的があります。

* ターゲット コンピューターの構築
* 量子アルゴリズムに必要な引数の計算
* シミュレーターを使用した量子アルゴリズムの実行
* 操作の結果の処理

ここでは、各手順について詳しく説明します。

### <a name="constructing-the-target-machine"></a>ターゲット コンピューターを構築する

量子コンピュータ－は通常の .NET クラスのインスタンスであるため、.NET クラスと同様に、コンストラクターを呼び出すことによって作成します。
`QuantumSimulator` を含む一部のシミュレーターは .NET <xref:System.IDisposable?displayProperty=nameWithType> インターフェイスを実装するため、C# `using` ステートメントでラップする必要があります。

### <a name="computing-arguments-for-the-algorithm"></a>アルゴリズムの引数を計算する

`Teleport` の例では、量子アルゴリズムに渡す比較的人工的な引数をいくつか計算しています。
ただし、通常は、量子アルゴリズムで重要なデータが必要とされるため、従来型のドライバーから取得するのが最も簡単です。

たとえば、量子アルゴリズムで化学シミュレーションを実行する場合、分子軌道相互作用の数値を示す大きなテーブルが必要です。
通常、このようなテーブルはアルゴリズムの実行時に提供されるファイルから読み込まれます。
Q# にはファイル システムにアクセスするためのメカニズムがないため、この種のデータは従来型のドライバーによって収集され、量子アルゴリズムの `Run` メソッドに渡されます。

従来型のドライバーが主要な役割を果たすもう 1 つの場合があります。
このクラスのアルゴリズムでは、一部の従来型のパラメーターに基づいて量子状態が準備され、値の計算にはその状態が使用されます。
このパラメーターは、何らかの山登り法または機械学習アルゴリズムに基づいて調整され、その後、量子アルゴリズムは再度実行されます。
このようなアルゴリズムでは、山登り法アルゴリズム自体を、従来型のドライバーによって呼び出される純粋な関数として実装することをお勧めします。その後、山登り法による結果は、次に実行される量子アルゴリズムに渡されます。

### <a name="running-the-quantum-algorithm"></a>量子アルゴリズムを実行する

このパートの大部分は、きわめて単純です。
各 Q# 操作は、静的な `Run` メソッドを提供するクラスにコンパイルされます。
このメソッドへの引数は、操作自体のフラット化された引数のタプルと、実行に使用するシミュレーターである追加の最初の引数によって指定されます。 `(a: String, (b: Double, c: Double))` 型の名前付きタプルを想定している操作に対応するフラット化された型は `(String a, Double b, Double c)` です。


`Run` メソッドに引数を渡す際は、いくつかの細かい違いがあります。

* 配列は、`Microsoft.Quantum.Simulation.Core.QArray<T>` オブジェクトにラップする必要があります。
    `QArray` クラスには、適切なオブジェクトの順序が付けられたコレクション (`IEnumerable<T>`) を受け取ることができるコンストラクターがあります。
* Q# で `()` と示される空のタプルは、C# では `QVoid.Instance` で表されます。
* 空でないタプルは、.NET `ValueTuple` インスタンスとして表されます。
* Q# ユーザー定義型は、基本データ型として渡されます。
* `Run` メソッドに操作または関数を渡すには、シミュレーターの `Get<>` メソッドを使用して、操作または関数のクラスのインスタンスを取得する必要があります。

### <a name="processing-the-results"></a>結果を処理する

量子アルゴリズムの結果は、`Run` メソッドから返されます。
`Run` メソッドは非同期的に実行されるため、<xref:System.Threading.Tasks.Task`1> のインスタンスが返されます。
実際の操作の結果を取得するには、複数の方法があります。 最も簡単な方法は、`Task` の[`Result`プロパティ](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result)を使用することです。

```csharp
    var res = BellTest.Run(sim, 1000, initial).Result;
```
[`Wait` メソッド](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait)または C#[`await` キーワード](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await)などを使用する他の手法も機能します。

引数と同様に、Q# のタプルは `ValueTuple` インスタンスとして表され、Q# の配列は `QArray` インスタンスとして表されます。
ユーザー定義型は、基本データ型として返されます。
空のタプル (`()`) は、`QVoid` クラスのインスタンスとして返されます。

多くの量子アルゴリズムでは、有用な回答を得るためにかなりの後処理が必要です。
たとえば、Shor のアルゴリズムの量子部分は、数値の要因を検出する計算の始まりにすぎません。

ほとんどの場合、このような後処理は従来型のドライバーで実行するのが最も単純かつ簡単です。
ユーザーに結果を報告し、ディスクに書き込むことができるのは、従来型のドライバーだけです。
従来型のドライバーは、Q# で公開されていない分析ライブラリやその他の数学関数にアクセスできます。


## <a name="failures"></a>エラー

操作の実行中に Q# `fail` ステートメントに到達すると、`ExecutionFailException` がスローされます。

`Run` メソッドでは `System.Task` が使用されているため、`fail` ステートメントの結果としてスローされる例外は `System.AggregateException` にラップされます。
エラーを引き起こした実際の原因を調べるには、次のように `AggregateException` 
`InnerExceptions` に繰り返す必要があります。

```csharp

            try
            {
                using(var sim = new QuantumSimulator())
                {
                    /// call your operations here...
                }
            }
            catch (AggregateException e)
            {
                // Unwrap AggregateException to get the message from Q# fail statement.
                // Go through all inner exceptions.
                foreach (Exception inner in e.InnerExceptions)
                {
                    // If the exception of type ExecutionFailException
                    if (inner is ExecutionFailException failException)
                    {
                        // Print the message it contains
                        Console.WriteLine($" {failException.Message}");
                    }
                }
            }
```

## <a name="other-classical-languages"></a>その他の古典的な言語

提供されているサンプルは C#、F#、Python で書かれていますが、Quantum Development Kit では、他の言語による従来型のホスト プログラムの作成もサポートしています。
たとえば、Visual Basic でホスト プログラムを作成する場合も[問題なく行うことができます](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net)。
