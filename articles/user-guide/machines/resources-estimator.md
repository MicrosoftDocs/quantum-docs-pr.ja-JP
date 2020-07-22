---
title: クォンタムリソースの推定-Quantum 開発キット
description: 'Microsoft QDK リソースの推定機能について説明します。この推定値は、クォンタムコンピューターで Q # 操作の特定のインスタンスを実行するために必要なリソースを見積もります。'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 0909a050e89d6295664e54ab63cfda5d407a8f12
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870544"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a>Quantum Development Kit (QDK) リソースの推定機能

名前が示すように、 `ResourcesEstimator` クラスは、クォンタムコンピューターで Q # 操作の特定のインスタンスを実行するために必要なリソースを見積もります。 これを実現するには、実際にクォンタムコンピューターの状態をシミュレートせずに、クォンタム操作を実行します。このため、コードの古典的な部分が適切な時間内に実行されていれば、数千個の qubits を使用する Q # 操作のリソースを推定します。

リソースの推定機能は、[シミュレータートレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の上に構築されています。これは、Q # プログラムのデバッグを支援するための豊富なメトリックとツールのセットを提供します。

## <a name="invoking-and-running-the-resources-estimator"></a>リソースの推定機能の呼び出しと実行

リソースの推定機能を使用して、任意の Q # 操作を実行できます。 詳細については、「 [Q # プログラムを実行する方法](xref:microsoft.quantum.guide.host-programs)」を参照してください。

### <a name="invoking-the-resources-estimator-from-c"></a>C からリソースの推定を呼び出す# 

他のターゲット マシンと同様に、最初に `ResourceEstimator` クラスのインスタンスを作成し、それを操作の `Run` メソッドの最初のパラメーターとして渡します。

`QuantumSimulator` クラスとは異なり、`ResourceEstimator` クラスでは <xref:System.IDisposable> インターフェイスが実装されていないため、これを `using` ステートメント内で囲む必要はありません。

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

この例に示すように、には、 `ResourcesEstimator` `ToTSV()` タブ区切り値 (TSV) を含むテーブルを生成するメソッドが用意されています。 テーブルは、ファイルに保存することも、コンソールに表示して分析することもできます。 上記のプログラムからの出力例を次に示します。

```output
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
> インスタンスは、 `ResourcesEstimator` 実行のたびにその計算をリセットしません。 同じインスタンスを使用して別の操作を実行すると、新しい結果が既存の結果と共に集計されます。 実行間の計算をリセットする必要がある場合は、実行のたびに新しいインスタンスを作成します。

### <a name="invoking-the-resources-estimator-from-python"></a>Python からリソースの推定機能を呼び出す

インポートされた Q # 操作で、Python ライブラリの[estimate_resources ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable)メソッドを使用します。

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a>コマンドラインからリソースの推定機能を呼び出す

コマンドラインから Q # プログラムを実行する場合は、 **--シミュレーター** (または **-s**ショートカット) パラメーターを使用して、対象のコンピューターを指定し `ResourcesEstimator` ます。 次のコマンドは、リソースの推定機能を使用してプログラムを実行します。 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a>Juptyer Notebook からリソースの推定機能を呼び出す

"IQ # マジック command [% 推定](xref:microsoft.quantum.iqsharp.magic-ref.simulate)" を使用して、Q # 操作を実行します。

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a>プログラムによる推定データの取得

TSV テーブルに加えて、リソースの推定機能のプロパティを使用して、実行中に推定されるリソースをプログラムで取得することができ `Data` ます。 プロパティは、 `Data` `System.DataTable` とという2つの列を持つインスタンスを提供します。これは `Metric` `Sum` 、メトリックの名前によってインデックス化されます。

次のコードは `QubitClifford` 、 `T` `CNOT` Q # 操作によって使用される、、および操作の合計数を取得して印刷する方法を示しています。

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

リソースの推定機能では、次のメトリックが追跡されます。

|メトリック|説明|
|----|----|
|__CNOT__    |操作の実行回数 `CNOT` (制御された Pa Li X 操作とも呼ばれます)。|
|__QubitClifford__ |任意の1つの qubit Clifford および P# li 操作の実行回数。|
|__測定値__    |測定の実行回数。  |
|__R__    |`T`、Clifford、および P# li の各操作を除く、任意の1つの qubit 回転の実行回数。  |
|__T__    |操作の実行回数 `T` とその活用 ( `T` 操作、T_x = h. t .h、T_y = Hy. t. hy など)。  |
|__[奥行]__|Q # 操作によって実行されるクォンタム回線の深さの下限。 既定では、深さメトリックはゲートだけをカウントし `T` ます。 詳細については、「[深度カウンター](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)」を参照してください。   |
|__Width__    |Q # 操作の実行中に割り当てられた qubits の最大数の下限。 __深さ__と__幅__の両方の下限を同時に達成できない可能性があります。  |
|__BorrowedWidth__    |Q # 操作内で借用された qubits の最大数。  |

## <a name="providing-the-probability-of-measurement-outcomes"></a>測定結果の確率を指定する

<xref:microsoft.quantum.diagnostics.assertmeasurementprobability>名前空間のを使用し <xref:microsoft.quantum.diagnostics> て、測定演算の予想される確率に関する情報を提供できます。 詳細については、「[クォンタムトレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro) 」を参照してください。

## <a name="see-also"></a>関連項目

- [クォンタムトレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [量子 Toffoli シミュレーター](xref:microsoft.quantum.machines.toffoli-simulator)
- [量子完全状態シミュレーター](xref:microsoft.quantum.machines.full-state-simulator) 