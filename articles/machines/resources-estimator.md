---
title: Quantum 開発キットリソースの推定機能
description: 'リソースの推定について説明します。この推定値は、クォンタムコンピューターで Q # 操作の特定のインスタンスを実行するために必要なリソースを見積もります。'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 37c901e5a861f0e8a10cdc911ad1d84ddd3e6e00
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907054"
---
# <a name="the-resourcesestimator-target-machine"></a>ResourcesEstimator ターゲットコンピューター

名前が示すように、`ResourcesEstimator` は、クォンタムコンピューターで Q # 操作の特定のインスタンスを実行するために必要なリソースを推定します。
これを実現するには、実際にクォンタムコンピューターの状態をシミュレートせずに、クォンタム操作を実行します。このため、数千個の qubits を使用する Q # 操作のリソースを見積もることができます。

## <a name="usage"></a>使用法

`ResourcesEstimator` は別の種類のターゲットマシンであるため、任意の Q # 操作を実行するために使用できます。 

他のターゲットマシンと同様に、 C#ホストプログラムで使用するには、インスタンスを作成し、操作の `Run` メソッドの最初のパラメーターとして渡します。

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();
            Console.WriteLine(estimator.ToTSV());
        }
    }
}
```

この例に示すように、`ResourcesEstimator` には、タブ区切り値 (TSV) を含むテーブルを生成するための `ToTSV()` メソッドが用意されています。これは、ファイルに保存したり、分析のためにコンソールに書き込んだたりすることができます。 上記のプログラムの出力は、次のようになります。

```Output
Metric          Sum
CNOT            1000
QubitClifford   1000
R               0
Measure         4002
T               0
Depth           0
Width           2
BorrowedWidth   0
```

> [!NOTE]
> `ResourcesEstimator` は、実行のたびに計算をリセットしません。同じインスタンスを使用して別の操作を実行すると、既存の結果に基づいて集計されたカウントを保持します。
> 実行間の計算をリセットする必要がある場合は、実行のたびに新しいインスタンスを作成します。


## <a name="programmatically-retrieving-the-estimated-data"></a>プログラムによる推定データの取得

TSV テーブルに加えて、推定されるリソースは、`ResourcesEstimator`の `Data` プロパティを使用してプログラムで取得できます。 `Data` は、メトリック名でインデックス付けされた `Metric` と `Sum`の2つの列を持つ `System.DataTable` インスタンスを提供します。

次のコードは、Q # 操作によって使用される `QubitClifford`、`T`、および `CNOT` ゲートの合計数を取得して印刷する方法を示しています。

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();

            var data = estimator.Data;
            Console.WriteLine($"QubitCliffords: {data.Rows.Find("QubitClifford")["Sum"]}");
            Console.WriteLine($"Ts: {data.Rows.Find("T")["Sum"]}");
            Console.WriteLine($"CNOTs: {data.Rows.Find("CNOT")["Sum"]}");
        }
    }
}
```

## <a name="metrics-reported"></a>報告されるメトリック

`ResourcesEstimator`によって推定されるメトリックの一覧を次に示します。

* __Cnot__: 実行された cnot (被制御 P# li X ゲートとも呼ばれる) ゲートの数。
* __Qubitclifford__: 実行された1つの Qubit clifフォードおよび P# li ゲートの数。
* __Measure__: 実行された測定値の数。
* __R__: 実行された1つの qubit ローテーション (T、Clifford、および P# li を除く) の数。
* __T__: t ゲート、T_x = .h、T_y = hy. t .h を含む t ゲートとその活用の数が実行されました。
* __Depth__: Q # 操作によって実行されるクォンタム回線の深さ。 既定では、T ゲートのみが深さでカウントされます。詳細については、「[深度カウンター](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) 」を参照してください。
* __Width__: Q # 操作の実行中に割り当てられた qubits の最大数。
* __BorrowedWidth__: Q # 操作内で借用される qubits の最大数。


## <a name="providing-the-probability-of-measurement-outcomes"></a>測定結果の確率を指定する

<xref:microsoft.quantum.intrinsic> 名前空間の <xref:microsoft.quantum.intrinsic.assertprob> を使用すると、Q # プログラムの実行を促進するために、測定の予想される確率に関する情報を提供できます。 次の例を使って説明します。

```qsharp
operation Teleport(source : Qubit, target : Qubit) : Unit {

    using (qubit = Qubit()) {

        H(q);
        CNOT(qubit, target);

        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [qubit], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(qubit) == One) { X(target); X(qubit); }
    }
}
```

`ResourcesEstimator` が検出されると `AssertProb` `source` の測定 `PauliZ` を記録し、`q` 確率が0.5 の `Zero` の結果を指定する必要があります。 後で `M` を実行すると、結果の確率の記録された値が検出され、`M` は `Zero` または確率が0.5 の `One` を返します。


## <a name="see-also"></a>参照

`ResourcesEstimator` は、quantum コンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の上に構築されています。これにより、豊富なメトリックセットが提供されます。また、完全な呼び出しグラフでメトリックをレポートする機能や、Q # プログラムでのバグの検出に役立つ[distinct 入力チェッカー](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)などの機能が提供されます。 詳細については、 [trace シミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)のドキュメントを参照してください。

