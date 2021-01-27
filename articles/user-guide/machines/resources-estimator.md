---
title: クォンタムリソースの推定-Quantum 開発キット
description: クォンタムコンピューターで特定の操作のインスタンスを実行するために必要なリソースを推定する、Microsoft QDK リソースの推定機能について説明し Q# ます。
author: anpaz
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: c3aa94c8b34ad7247fbdeab4bf4dcb96ce746014
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847460"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a>Quantum Development Kit (QDK) リソースの推定機能

名前が示すように、 `ResourcesEstimator` クラスは、クォンタムコンピューターで特定の操作のインスタンスを実行するために必要なリソースを見積もり Q# ます。 これを実現するには、実際にクォンタムコンピューターの状態をシミュレートせずに、クォンタム操作を実行します。このため、 Q# コードの古典的な部分が適切な時間内に実行されていれば、何千もの qubits を使用する操作のリソースを推定します。

リソースの推定機能は、プログラムのデバッグを支援するための豊富なメトリックとツールのセットを提供する、 [Quantum トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の上に構築されてい Q# ます。

## <a name="invoking-and-running-the-resources-estimator"></a>リソースの推定機能の呼び出しと実行

リソースの推定機能を使用して、任意の操作を実行でき Q# ます。 詳細については、「 [ Q# プログラムを実行する方法](xref:microsoft.quantum.guide.host-programs)」を参照してください。

### <a name="invoking-the-resources-estimator-from-c"></a>C からリソースの推定を呼び出す# 

他のターゲット マシンと同様に、最初に `ResourcesEstimator` クラスのインスタンスを作成し、それを操作の `Run` メソッドの最初のパラメーターとして渡します。

`QuantumSimulator` クラスとは異なり、`ResourcesEstimator` クラスでは <xref:System.IDisposable> インターフェイスが実装されていないため、これを `using` ステートメント内で囲む必要はありません。

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

インポートされた操作で、Python ライブラリの [estimate_resources ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) メソッドを使用し Q# ます。

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a>コマンドラインからリソースの推定機能を呼び出す

コマンドラインからプログラムを実行する場合は、 Q# **--シミュレーター** (または **-s** ショートカット) パラメーターを使用して、対象のコンピューターを指定し `ResourcesEstimator` ます。 次のコマンドは、リソースの推定機能を使用してプログラムを実行します。 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a>Juptyer Notebook からリソースの推定機能を呼び出す

この Q# 操作を実行するには、I マジック command [% 推定](xref:microsoft.quantum.iqsharp.magic-ref.simulate) を使用し Q# ます。

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a>プログラムによる推定データの取得

TSV テーブルに加えて、リソースの推定機能のプロパティを使用して、実行中に推定されるリソースをプログラムで取得することができ `Data` ます。 プロパティは、 `Data` `System.DataTable` とという2つの列を持つインスタンスを提供します。これは `Metric` `Sum` 、メトリックの名前によってインデックス化されます。

次のコードは `QubitClifford` 、 `T` 操作に `CNOT` よって使用される、、および操作の合計数を取得して印刷する方法を示してい Q# ます。

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

|指標|説明|
|----|----|
|__CNOT__    |操作の実行回数 `CNOT` (制御された Pa Li X 操作とも呼ばれます)。|
|__QubitClifford__ |任意の1つの qubit Clifford および P# li 操作の実行回数。|
|__測定値__    |測定の実行回数。  |
|__R__    |`T`、Clifford、および P# li の各操作を除く、任意の1つの qubit 回転の実行回数。  |
|__T__    |操作の実行回数 `T` とその活用 ( `T` 操作、T_x = h. t .h、T_y = Hy. t. hy など)。  |
|__Depth__|操作によって実行されるクォンタム回線の深さ Q# ( [下記](#depth-width-and-qubitcount)参照)。 既定では、深さメトリックはゲートだけをカウントし `T` ます。 詳細については、「 [深度カウンター](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)」を参照してください。   |
|__Width__|操作によって実行されるクォンタム回線の幅 Q# ( [下記](#depth-width-and-qubitcount)参照)。 既定では、深さメトリックはゲートだけをカウントし `T` ます。 詳細については、「 [Width カウンタ](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)」を参照してください。   |
|__QubitCount__    |操作の実行中に割り当てられた qubits の最大数の下限 Q# 。 このメトリックは、 __深さ__ と互換性がない場合があります (下記参照)。  |
|__BorrowedWidth__    |操作内で借用される qubits の最大数 Q# 。  |


## <a name="depth-width-and-qubitcount"></a>Depth、Width、および QubitCount

レポートの深さと幅の推定は、相互に互換性があります。
(以前はどちらの数値も実現可能でしたが、深度と幅には異なる回路が必要です)。現在、このペアのメトリックは両方とも同じ回線で同時に実現できます。

次のメトリックがレポートされます。

__深さ:__ ルート操作の実行に必要な場合は、構成されたゲート時間を前提とします。
操作が呼び出された場合、または操作の開始時と終了時の最新の qubit の時間差。

__幅:__ ルート操作の場合-実際に使用された qubits の数 (とその操作を呼び出します)。
操作が呼び出された操作または後続の操作の場合-操作の開始時に既に使用されている qubits に加えて、使用された qubits の数。

再利用された qubits はこの数に寄与しないことに注意してください。
たとえば、操作が開始される前に数個の qubits が解放され、この操作によって要求された (およびから呼び出された操作) が以前のリリース qubits を再利用することによって満たされた場合、操作の幅は0として報告されます。 成功した qubits は、幅には影響しません。

__Qubitcount:__ ルート操作の場合-この操作を実行するのに十分な最小数の qubits (およびそこから呼び出された操作)。
または後続の操作と呼ばれる操作の場合-この操作を個別に実行するのに十分な数の qubits。 この数値には入力 qubits は含まれません。 これには、借用した qubits が含まれます。

2つの操作モードがサポートされています。 モードを選択するには、QCTraceSimulatorConfiguration. 最適化の深さを設定します。

最適化の __深さ = false:__ これは既定のモードです。 QubitManager は、qubits を再利用することをお勧めします。新たにリリースされた qubits を再利用して、新しいものを割り当てます。 ルート操作の __幅__ は、最小幅 (下限) になります。 互換性のある __深さ__ がレポートされます。 __Qubitcount__ は、借りていないことを前提として、ルート操作の __幅__ と同じになります。

最適化の __深さ = true:__ QubitManager は、実行中および実行後に実行される qubit の再利用とヒューリスティックベースの最適化では推奨されません。 ルート操作の __深さ__ は、最小の深さ (下限) になります。 この深さでは、互換性のある __幅__ がレポートされます (両方とも同時に実現できます)。 幅を最適化するために、プログラムで後で検出されたゲートが、プログラムの前に発生したゲートの前にスケジュールされている可能性があります。ただし、qubits は、深さが最小限になるように再利用されるようにスケジュールされています。 時間の値に基づいて qubits を再利用する場合は、ゲート時間を整数値として構成することをお勧めします。 __幅__ が最適であることは保証されていません。 詳細については、「トレーサーのホワイトペーパーの [幅と詳細](https://github.com/microsoft/qsharp-runtime/tree/main/src/Simulation/Simulators/QCTraceSimulator/Docs)」を参照してください。

## <a name="providing-the-probability-of-measurement-outcomes"></a>測定結果の確率を指定する

<xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability>名前空間のを使用し <xref:Microsoft.Quantum.Diagnostics> て、測定演算の予想される確率に関する情報を提供できます。 詳細については、「[クォンタムトレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro) 」を参照してください。

## <a name="see-also"></a>関連項目

- [クォンタムトレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [量子 Toffoli シミュレーター](xref:microsoft.quantum.machines.toffoli-simulator)
- [量子完全状態シミュレーター](xref:microsoft.quantum.machines.full-state-simulator) 
