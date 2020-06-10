---
title: Quantum 開発キットリソースの推定機能
description: 'リソースの推定について説明します。この推定値は、クォンタムコンピューターで Q # 操作の特定のインスタンスを実行するために必要なリソースを見積もります。'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: b0c800c3946d2e4ba4457127fb9495dc9dcf2934
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630131"
---
# <a name="the-resources-estimator-target-machine"></a>リソース推定対象コンピューター

この名前が示すように、は、 `ResourcesEstimator` クォンタムコンピューターで Q # 操作の特定のインスタンスを実行するために必要なリソースを見積もります。
これを実現するには、実際にクォンタムコンピューターの状態をシミュレートせずに、クォンタム操作を実行します。このため、コードの古典的な部分を妥当な時間内に実行できる場合は、数千の qubits を使用する Q # 操作のリソースを見積もることができます。

## <a name="usage"></a>使用法

`ResourcesEstimator`は別の種類のターゲットコンピューターであるため、任意の Q # 操作を実行するために使用できます。 

他のターゲットマシンと同様に、C# ホストプログラムで使用するには、インスタンスを作成し、操作のメソッドの最初のパラメーターとして渡し `Run` ます。

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

この例に示すように、には、 `ResourcesEstimator` `ToTSV()` タブ区切り値 (TSV) を含むテーブルを生成するメソッドが用意されています。このテーブルは、ファイルに保存したり、分析のためにコンソールに書き込んだたりすることができます。 上記のプログラムの出力は、次のようになります。

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
> では、 `ResourcesEstimator` 実行ごとに計算がリセットされません。同じインスタンスを使用して別の操作を実行すると、既存の結果に対して集計されたカウントが保持されます。
> 実行間の計算をリセットする必要がある場合は、実行のたびに新しいインスタンスを作成します。


## <a name="programmatically-retrieving-the-estimated-data"></a>プログラムによる推定データの取得

TSV テーブルに加えて、推定されるリソースは、のプロパティを使用してプログラムで取得でき `ResourcesEstimator` `Data` ます。 `Data`には、 `System.DataTable` とという2つの列を持つインスタンスがあります。 `Metric` `Sum` メトリック名によってインデックスが作成されます。

次のコードは `QubitClifford` 、 `T` `CNOT` Q # 操作によって使用される、およびゲートの合計数を取得して印刷する方法を示しています。

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

によって推定されるメトリックの一覧を次に示し `ResourcesEstimator` ます。

* __Cnot__: 実行された cnot (被制御 P# li X ゲートとも呼ばれる) ゲートの数。
* __Qubitclifford__: 実行された1つの Qubit clifフォードおよび P# li ゲートの数。
* __Measure__: 実行された測定値の数。
* __R__: 実行された1つの qubit ローテーション (T、Clifford、および P# li を除く) の数。
* __T__: t ゲート、T_x = .h、T_y = hy. t .h を含む t ゲートとその活用の数が実行されました。
* __Depth__: Q # 操作によって実行されるクォンタム回線の深さ。 既定では、T ゲートのみが深さでカウントされます。詳細については、「[深度カウンター](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) 」を参照してください。
* __Width__: Q # 操作の実行中に割り当てられた qubits の最大数。
* __BorrowedWidth__: Q # 操作内で借用される qubits の最大数。


## <a name="providing-the-probability-of-measurement-outcomes"></a>測定結果の確率を指定する

<xref:microsoft.quantum.intrinsic.assertprob>名前空間からは、 <xref:microsoft.quantum.intrinsic> Q # プログラムの実行を促進するために、測定の予想される確率に関する情報を提供するために使用できます。 次の例を使って説明します。

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

が検出されると、の `ResourcesEstimator` `AssertProb` 測定を記録 `PauliZ` `source` し、 `q` 確率0.5 を使用しての結果を指定する必要があり `Zero` ます。 後で実行すると `M` 、結果の確率の記録された値が検出され、 `M` が返される `Zero` か、または `One` 確率0.5 が返されます。


## <a name="see-also"></a>関連項目

`ResourcesEstimator`は、quantum コンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の上に構築されています。これにより、豊富なメトリックセットが提供されます。また、完全な呼び出しグラフでメトリックをレポートする機能や、Q # プログラムでのバグの発見に役立つ[distinct 入力チェッカー](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)などの機能が提供されます。 詳細については、 [trace シミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)のドキュメントを参照してください。

