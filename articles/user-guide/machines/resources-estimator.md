---
title: クォンタムリソースの推定-Quantum 開発キット
description: クォンタムコンピューターで特定の操作のインスタンスを実行するために必要なリソースを推定する、Microsoft QDK リソースの推定機能について説明し Q# ます。
author: anpaz-msft
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6138c098a4efe2797c7d7360573ddcb9cb70a6c1
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835929"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="43990-103">Quantum Development Kit (QDK) リソースの推定機能</span><span class="sxs-lookup"><span data-stu-id="43990-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="43990-104">名前が示すように、 `ResourcesEstimator` クラスは、クォンタムコンピューターで特定の操作のインスタンスを実行するために必要なリソースを見積もり Q# ます。</span><span class="sxs-lookup"><span data-stu-id="43990-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="43990-105">これを実現するには、実際にクォンタムコンピューターの状態をシミュレートせずに、クォンタム操作を実行します。このため、 Q# コードの古典的な部分が適切な時間内に実行されていれば、何千もの qubits を使用する操作のリソースを推定します。</span><span class="sxs-lookup"><span data-stu-id="43990-105">It accomplishes this by running the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="43990-106">リソースの推定機能は、プログラムのデバッグを支援するための豊富なメトリックとツールのセットを提供する、 [Quantum トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の上に構築されてい Q# ます。</span><span class="sxs-lookup"><span data-stu-id="43990-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="43990-107">リソースの推定機能の呼び出しと実行</span><span class="sxs-lookup"><span data-stu-id="43990-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="43990-108">リソースの推定機能を使用して、任意の操作を実行でき Q# ます。</span><span class="sxs-lookup"><span data-stu-id="43990-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="43990-109">詳細については、「 [ Q# プログラムを実行する方法](xref:microsoft.quantum.guide.host-programs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43990-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="43990-110">C からリソースの推定を呼び出す#</span><span class="sxs-lookup"><span data-stu-id="43990-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="43990-111">他のターゲット マシンと同様に、最初に `ResourceEstimator` クラスのインスタンスを作成し、それを操作の `Run` メソッドの最初のパラメーターとして渡します。</span><span class="sxs-lookup"><span data-stu-id="43990-111">As with other target machines, you first create an instance of the `ResourceEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="43990-112">`QuantumSimulator` クラスとは異なり、`ResourceEstimator` クラスでは <xref:System.IDisposable> インターフェイスが実装されていないため、これを `using` ステートメント内で囲む必要はありません。</span><span class="sxs-lookup"><span data-stu-id="43990-112">Note that, unlike the `QuantumSimulator` class, the `ResourceEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

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

<span data-ttu-id="43990-113">この例に示すように、には、 `ResourcesEstimator` `ToTSV()` タブ区切り値 (TSV) を含むテーブルを生成するメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="43990-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="43990-114">テーブルは、ファイルに保存することも、コンソールに表示して分析することもできます。</span><span class="sxs-lookup"><span data-stu-id="43990-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="43990-115">上記のプログラムからの出力例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="43990-115">The following is a sample output from the preceding program:</span></span>

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
> <span data-ttu-id="43990-116">インスタンスは、 `ResourcesEstimator` 実行のたびにその計算をリセットしません。</span><span class="sxs-lookup"><span data-stu-id="43990-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="43990-117">同じインスタンスを使用して別の操作を実行すると、新しい結果が既存の結果と共に集計されます。</span><span class="sxs-lookup"><span data-stu-id="43990-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="43990-118">実行間の計算をリセットする必要がある場合は、実行のたびに新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="43990-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="43990-119">Python からリソースの推定機能を呼び出す</span><span class="sxs-lookup"><span data-stu-id="43990-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="43990-120">インポートされた操作で、Python ライブラリの [estimate_resources ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) メソッドを使用し Q# ます。</span><span class="sxs-lookup"><span data-stu-id="43990-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="43990-121">コマンドラインからリソースの推定機能を呼び出す</span><span class="sxs-lookup"><span data-stu-id="43990-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="43990-122">コマンドラインからプログラムを実行する場合は、 Q# **--シミュレーター** (または **-s** ショートカット) パラメーターを使用して、対象のコンピューターを指定し `ResourcesEstimator` ます。</span><span class="sxs-lookup"><span data-stu-id="43990-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="43990-123">次のコマンドは、リソースの推定機能を使用してプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="43990-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="43990-124">Juptyer Notebook からリソースの推定機能を呼び出す</span><span class="sxs-lookup"><span data-stu-id="43990-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="43990-125">この Q# 操作を実行するには、I マジック command [% 推定](xref:microsoft.quantum.iqsharp.magic-ref.simulate) を使用し Q# ます。</span><span class="sxs-lookup"><span data-stu-id="43990-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="43990-126">プログラムによる推定データの取得</span><span class="sxs-lookup"><span data-stu-id="43990-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="43990-127">TSV テーブルに加えて、リソースの推定機能のプロパティを使用して、実行中に推定されるリソースをプログラムで取得することができ `Data` ます。</span><span class="sxs-lookup"><span data-stu-id="43990-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="43990-128">プロパティは、 `Data` `System.DataTable` とという2つの列を持つインスタンスを提供します。これは `Metric` `Sum` 、メトリックの名前によってインデックス化されます。</span><span class="sxs-lookup"><span data-stu-id="43990-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="43990-129">次のコードは `QubitClifford` 、 `T` 操作に `CNOT` よって使用される、、および操作の合計数を取得して印刷する方法を示してい Q# ます。</span><span class="sxs-lookup"><span data-stu-id="43990-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="43990-130">報告されるメトリック</span><span class="sxs-lookup"><span data-stu-id="43990-130">Metrics Reported</span></span>

<span data-ttu-id="43990-131">リソースの推定機能では、次のメトリックが追跡されます。</span><span class="sxs-lookup"><span data-stu-id="43990-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="43990-132">メトリック</span><span class="sxs-lookup"><span data-stu-id="43990-132">Metric</span></span>|<span data-ttu-id="43990-133">説明</span><span class="sxs-lookup"><span data-stu-id="43990-133">Description</span></span>|
|----|----|
|<span data-ttu-id="43990-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="43990-134">__CNOT__</span></span>    |<span data-ttu-id="43990-135">操作の実行回数 `CNOT` (制御された Pa Li X 操作とも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="43990-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="43990-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="43990-136">__QubitClifford__</span></span> |<span data-ttu-id="43990-137">任意の1つの qubit Clifford および P# li 操作の実行回数。</span><span class="sxs-lookup"><span data-stu-id="43990-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="43990-138">__測定値__</span><span class="sxs-lookup"><span data-stu-id="43990-138">__Measure__</span></span>    |<span data-ttu-id="43990-139">測定の実行回数。</span><span class="sxs-lookup"><span data-stu-id="43990-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="43990-140">__R__</span><span class="sxs-lookup"><span data-stu-id="43990-140">__R__</span></span>    |<span data-ttu-id="43990-141">`T`、Clifford、および P# li の各操作を除く、任意の1つの qubit 回転の実行回数。</span><span class="sxs-lookup"><span data-stu-id="43990-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="43990-142">__T__</span><span class="sxs-lookup"><span data-stu-id="43990-142">__T__</span></span>    |<span data-ttu-id="43990-143">操作の実行回数 `T` とその活用 ( `T` 操作、T_x = h. t .h、T_y = Hy. t. hy など)。</span><span class="sxs-lookup"><span data-stu-id="43990-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="43990-144">__[奥行]__</span><span class="sxs-lookup"><span data-stu-id="43990-144">__Depth__</span></span>|<span data-ttu-id="43990-145">操作によって実行されるクォンタム回線の深さの下限。 Q#</span><span class="sxs-lookup"><span data-stu-id="43990-145">The lower bound for the depth of the quantum circuit run by the Q# operation.</span></span> <span data-ttu-id="43990-146">既定では、深さメトリックはゲートだけをカウントし `T` ます。</span><span class="sxs-lookup"><span data-stu-id="43990-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="43990-147">詳細については、「 [深度カウンター](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43990-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="43990-148">__Width__</span><span class="sxs-lookup"><span data-stu-id="43990-148">__Width__</span></span>    |<span data-ttu-id="43990-149">操作の実行中に割り当てられた qubits の最大数の下限 Q# 。</span><span class="sxs-lookup"><span data-stu-id="43990-149">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="43990-150">__深さ__と__幅__の両方の下限を同時に達成できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="43990-150">It might not be possible to achieve both __Depth__ and __Width__ lower bounds simultaneously.</span></span>  |
|<span data-ttu-id="43990-151">__BorrowedWidth__</span><span class="sxs-lookup"><span data-stu-id="43990-151">__BorrowedWidth__</span></span>    |<span data-ttu-id="43990-152">操作内で借用される qubits の最大数 Q# 。</span><span class="sxs-lookup"><span data-stu-id="43990-152">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="43990-153">測定結果の確率を指定する</span><span class="sxs-lookup"><span data-stu-id="43990-153">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="43990-154"><xref:microsoft.quantum.diagnostics.assertmeasurementprobability>名前空間のを使用し <xref:microsoft.quantum.diagnostics> て、測定演算の予想される確率に関する情報を提供できます。</span><span class="sxs-lookup"><span data-stu-id="43990-154">You can use <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> from the <xref:microsoft.quantum.diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="43990-155">詳細については、「[クォンタムトレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43990-155">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="43990-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="43990-156">See also</span></span>

- [<span data-ttu-id="43990-157">クォンタムトレースシミュレーター</span><span class="sxs-lookup"><span data-stu-id="43990-157">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="43990-158">量子 Toffoli シミュレーター</span><span class="sxs-lookup"><span data-stu-id="43990-158">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="43990-159">量子完全状態シミュレーター</span><span class="sxs-lookup"><span data-stu-id="43990-159">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 