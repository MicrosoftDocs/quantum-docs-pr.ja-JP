---
title: クォンタムリソースの推定-Quantum 開発キット
description: 'クォンタムコンピューターで特定の操作のインスタンスを実行するために必要なリソースを推定する、Microsoft QDK リソースの推定機能について説明し :::no-loc(Q#)::: ます。'
author: anpaz-msft
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: e1ec01d85a141b9c8a7a5ba5589663a0773520e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691863"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="83e93-103">Quantum Development Kit (QDK) リソースの推定機能</span><span class="sxs-lookup"><span data-stu-id="83e93-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="83e93-104">名前が示すように、 `ResourcesEstimator` クラスは、クォンタムコンピューターで特定の操作のインスタンスを実行するために必要なリソースを見積もり :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="83e93-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a :::no-loc(Q#)::: operation on a quantum computer.</span></span> <span data-ttu-id="83e93-105">これを実現するには、実際にクォンタムコンピューターの状態をシミュレートせずに、クォンタム操作を実行します。このため、 :::no-loc(Q#)::: コードの古典的な部分が適切な時間内に実行されていれば、何千もの qubits を使用する操作のリソースを推定します。</span><span class="sxs-lookup"><span data-stu-id="83e93-105">It accomplishes this by running the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for :::no-loc(Q#)::: operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="83e93-106">リソースの推定機能は、プログラムのデバッグを支援するための豊富なメトリックとツールのセットを提供する、 [Quantum トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の上に構築されてい :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="83e93-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug :::no-loc(Q#)::: programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="83e93-107">リソースの推定機能の呼び出しと実行</span><span class="sxs-lookup"><span data-stu-id="83e93-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="83e93-108">リソースの推定機能を使用して、任意の操作を実行でき :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="83e93-108">You can use the resources estimator to run any :::no-loc(Q#)::: operation.</span></span> <span data-ttu-id="83e93-109">詳細については、「 [ :::no-loc(Q#)::: プログラムを実行する方法](xref:microsoft.quantum.guide.host-programs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83e93-109">For additional details, see [Ways to run a :::no-loc(Q#)::: program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="83e93-110">C からリソースの推定を呼び出す#</span><span class="sxs-lookup"><span data-stu-id="83e93-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="83e93-111">他のターゲット マシンと同様に、最初に `ResourceEstimator` クラスのインスタンスを作成し、それを操作の `Run` メソッドの最初のパラメーターとして渡します。</span><span class="sxs-lookup"><span data-stu-id="83e93-111">As with other target machines, you first create an instance of the `ResourceEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="83e93-112">`QuantumSimulator` クラスとは異なり、`ResourceEstimator` クラスでは <xref:System.IDisposable> インターフェイスが実装されていないため、これを `using` ステートメント内で囲む必要はありません。</span><span class="sxs-lookup"><span data-stu-id="83e93-112">Note that, unlike the `QuantumSimulator` class, the `ResourceEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

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

<span data-ttu-id="83e93-113">この例に示すように、には、 `ResourcesEstimator` `ToTSV()` タブ区切り値 (TSV) を含むテーブルを生成するメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="83e93-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="83e93-114">テーブルは、ファイルに保存することも、コンソールに表示して分析することもできます。</span><span class="sxs-lookup"><span data-stu-id="83e93-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="83e93-115">上記のプログラムからの出力例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="83e93-115">The following is a sample output from the preceding program:</span></span>

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
> <span data-ttu-id="83e93-116">インスタンスは、 `ResourcesEstimator` 実行のたびにその計算をリセットしません。</span><span class="sxs-lookup"><span data-stu-id="83e93-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="83e93-117">同じインスタンスを使用して別の操作を実行すると、新しい結果が既存の結果と共に集計されます。</span><span class="sxs-lookup"><span data-stu-id="83e93-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="83e93-118">実行間の計算をリセットする必要がある場合は、実行のたびに新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="83e93-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="83e93-119">Python からリソースの推定機能を呼び出す</span><span class="sxs-lookup"><span data-stu-id="83e93-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="83e93-120">インポートされた操作で、Python ライブラリの [estimate_resources ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) メソッドを使用し :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="83e93-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported :::no-loc(Q#)::: operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="83e93-121">コマンドラインからリソースの推定機能を呼び出す</span><span class="sxs-lookup"><span data-stu-id="83e93-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="83e93-122">コマンドラインからプログラムを実行する場合は、 :::no-loc(Q#)::: **--シミュレーター** (または **-s** ショートカット) パラメーターを使用して、対象のコンピューターを指定し `ResourcesEstimator` ます。</span><span class="sxs-lookup"><span data-stu-id="83e93-122">When running a :::no-loc(Q#)::: program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="83e93-123">次のコマンドは、リソースの推定機能を使用してプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="83e93-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="83e93-124">Juptyer Notebook からリソースの推定機能を呼び出す</span><span class="sxs-lookup"><span data-stu-id="83e93-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="83e93-125">この :::no-loc(Q#)::: 操作を実行するには、I マジック command [% 推定](xref:microsoft.quantum.iqsharp.magic-ref.simulate) を使用し :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="83e93-125">Use the I:::no-loc(Q#)::: magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the :::no-loc(Q#)::: operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="83e93-126">プログラムによる推定データの取得</span><span class="sxs-lookup"><span data-stu-id="83e93-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="83e93-127">TSV テーブルに加えて、リソースの推定機能のプロパティを使用して、実行中に推定されるリソースをプログラムで取得することができ `Data` ます。</span><span class="sxs-lookup"><span data-stu-id="83e93-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="83e93-128">プロパティは、 `Data` `System.DataTable` とという2つの列を持つインスタンスを提供します。これは `Metric` `Sum` 、メトリックの名前によってインデックス化されます。</span><span class="sxs-lookup"><span data-stu-id="83e93-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="83e93-129">次のコードは `QubitClifford` 、 `T` 操作に `CNOT` よって使用される、、および操作の合計数を取得して印刷する方法を示してい :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="83e93-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a :::no-loc(Q#)::: operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="83e93-130">報告されるメトリック</span><span class="sxs-lookup"><span data-stu-id="83e93-130">Metrics Reported</span></span>

<span data-ttu-id="83e93-131">リソースの推定機能では、次のメトリックが追跡されます。</span><span class="sxs-lookup"><span data-stu-id="83e93-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="83e93-132">メトリック</span><span class="sxs-lookup"><span data-stu-id="83e93-132">Metric</span></span>|<span data-ttu-id="83e93-133">説明</span><span class="sxs-lookup"><span data-stu-id="83e93-133">Description</span></span>|
|----|----|
|<span data-ttu-id="83e93-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="83e93-134">__CNOT__</span></span>    |<span data-ttu-id="83e93-135">操作の実行回数 `CNOT` (制御された Pa Li X 操作とも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="83e93-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="83e93-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="83e93-136">__QubitClifford__</span></span> |<span data-ttu-id="83e93-137">任意の1つの qubit Clifford および P# li 操作の実行回数。</span><span class="sxs-lookup"><span data-stu-id="83e93-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="83e93-138">__測定値__</span><span class="sxs-lookup"><span data-stu-id="83e93-138">__Measure__</span></span>    |<span data-ttu-id="83e93-139">測定の実行回数。</span><span class="sxs-lookup"><span data-stu-id="83e93-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="83e93-140">__R__</span><span class="sxs-lookup"><span data-stu-id="83e93-140">__R__</span></span>    |<span data-ttu-id="83e93-141">`T`、Clifford、および P# li の各操作を除く、任意の1つの qubit 回転の実行回数。</span><span class="sxs-lookup"><span data-stu-id="83e93-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="83e93-142">__T__</span><span class="sxs-lookup"><span data-stu-id="83e93-142">__T__</span></span>    |<span data-ttu-id="83e93-143">操作の実行回数 `T` とその活用 ( `T` 操作、T_x = h. t .h、T_y = Hy. t. hy など)。</span><span class="sxs-lookup"><span data-stu-id="83e93-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="83e93-144">__[奥行]__</span><span class="sxs-lookup"><span data-stu-id="83e93-144">__Depth__</span></span>|<span data-ttu-id="83e93-145">操作によって実行されるクォンタム回線の深さ :::no-loc(Q#)::: ( [下記](#depth-width-and-qubitcount)参照)。</span><span class="sxs-lookup"><span data-stu-id="83e93-145">Depth of the quantum circuit run by the :::no-loc(Q#)::: operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="83e93-146">既定では、深さメトリックはゲートだけをカウントし `T` ます。</span><span class="sxs-lookup"><span data-stu-id="83e93-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="83e93-147">詳細については、「 [深度カウンター](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83e93-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="83e93-148">__Width__</span><span class="sxs-lookup"><span data-stu-id="83e93-148">__Width__</span></span>|<span data-ttu-id="83e93-149">操作によって実行されるクォンタム回線の幅 :::no-loc(Q#)::: ( [下記](#depth-width-and-qubitcount)参照)。</span><span class="sxs-lookup"><span data-stu-id="83e93-149">Width of the quantum circuit run by the :::no-loc(Q#)::: operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="83e93-150">既定では、深さメトリックはゲートだけをカウントし `T` ます。</span><span class="sxs-lookup"><span data-stu-id="83e93-150">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="83e93-151">詳細については、「 [深度カウンター](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83e93-151">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="83e93-152">__QubitCount__</span><span class="sxs-lookup"><span data-stu-id="83e93-152">__QubitCount__</span></span>    |<span data-ttu-id="83e93-153">操作の実行中に割り当てられた qubits の最大数の下限 :::no-loc(Q#)::: 。</span><span class="sxs-lookup"><span data-stu-id="83e93-153">The lower bound for the maximum number of qubits allocated during the run of the :::no-loc(Q#)::: operation.</span></span> <span data-ttu-id="83e93-154">このメトリックは、 __深さ__ と互換性がない場合があります (下記参照)。</span><span class="sxs-lookup"><span data-stu-id="83e93-154">This metric might not be compatible with __Depth__ (see below).</span></span>  |
|<span data-ttu-id="83e93-155">__BorrowedWidth__</span><span class="sxs-lookup"><span data-stu-id="83e93-155">__BorrowedWidth__</span></span>    |<span data-ttu-id="83e93-156">操作内で借用される qubits の最大数 :::no-loc(Q#)::: 。</span><span class="sxs-lookup"><span data-stu-id="83e93-156">The maximum number of qubits borrowed inside the :::no-loc(Q#)::: operation.</span></span>  |


## <a name="depth-width-and-qubitcount"></a><span data-ttu-id="83e93-157">Depth、Width、および QubitCount</span><span class="sxs-lookup"><span data-stu-id="83e93-157">Depth, Width, and QubitCount</span></span>

<span data-ttu-id="83e93-158">レポートの深さと幅の推定は、相互に互換性があります。</span><span class="sxs-lookup"><span data-stu-id="83e93-158">Reported Depth and Width estimates are compatible with each other.</span></span>
<span data-ttu-id="83e93-159">(以前はどちらの数値も実現可能でしたが、深度と幅には異なる回路が必要です)。現在、このペアのメトリックは両方とも同じ回線で同時に実現できます。</span><span class="sxs-lookup"><span data-stu-id="83e93-159">(Previously both numbers were achievable, but different circuits would be required for Depth and for Width.) Currently both metrics in this pair can be achieved by the same circuit at the same time.</span></span>

<span data-ttu-id="83e93-160">次のメトリックがレポートされます。</span><span class="sxs-lookup"><span data-stu-id="83e93-160">The following metrics are reported:</span></span>

<span data-ttu-id="83e93-161">__深さ:__ ルート操作では、特定のゲート時間を想定して実行されます。</span><span class="sxs-lookup"><span data-stu-id="83e93-161">__Depth:__ For the root operation - time it takes to execute it assuming specific gate times.</span></span>
<span data-ttu-id="83e93-162">操作を実行した場合は、操作の開始時と終了時の最新の qubit 可用性時間との間で行われた操作時間の差。</span><span class="sxs-lookup"><span data-stu-id="83e93-162">For operations called or subsequent operations - time difference between latest qubit availability time at the beginning and the end of the operation.</span></span>

<span data-ttu-id="83e93-163">__幅:__ ルート操作の場合-実際に使用された qubits の数 (とその操作を呼び出します)。</span><span class="sxs-lookup"><span data-stu-id="83e93-163">__Width:__ For the root operation - number of qubits actually used to execute it (and operation it calls).</span></span>
<span data-ttu-id="83e93-164">操作が呼び出された操作または後続の操作の場合-操作の開始時に既に使用されている qubits に加えて、使用された qubits の数。</span><span class="sxs-lookup"><span data-stu-id="83e93-164">For operations called or subsequent operations - how many more qubits were used in addition to the qubits already used at the beginning of the operation.</span></span>

<span data-ttu-id="83e93-165">再利用された qubits はこの数に寄与しないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="83e93-165">Please note, that reused qubits do not contribute to this number.</span></span>
<span data-ttu-id="83e93-166">たとえば、操作が開始される前に数個の qubits が解放され、この操作によって要求された (およびから呼び出された操作) が以前のリリース qubits を再利用することによって満たされた場合、操作の幅は0として報告されます。</span><span class="sxs-lookup"><span data-stu-id="83e93-166">I.e. if a few qubits have been released before operation A starts, and all qubit demanded by this operation A (and operations called from A) were satisfied by reusing previously release qubits, the Width of operation A is reported as 0.</span></span> <span data-ttu-id="83e93-167">成功した qubits は、幅には影響しません。</span><span class="sxs-lookup"><span data-stu-id="83e93-167">Successfully borrowed qubits do not contribute to the Width either.</span></span>

<span data-ttu-id="83e93-168">__Qubitcount:__ ルート操作の場合-この操作を実行するのに十分な最小数の qubits (およびそこから呼び出された操作)。</span><span class="sxs-lookup"><span data-stu-id="83e93-168">__QubitCount:__ For the root operation - minimum number of qubits that would be sufficient to execute this operation (and operations called from it).</span></span>
<span data-ttu-id="83e93-169">または後続の操作と呼ばれる操作の場合-この操作を個別に実行するのに十分な数の qubits。</span><span class="sxs-lookup"><span data-stu-id="83e93-169">For operations called or subsequent operations - minimum number of qubits that would be sufficient to execute this operation separately.</span></span> <span data-ttu-id="83e93-170">この数値には入力 qubits は含まれません。</span><span class="sxs-lookup"><span data-stu-id="83e93-170">This number doesn't include input qubits.</span></span> <span data-ttu-id="83e93-171">これには、借用した qubits が含まれます。</span><span class="sxs-lookup"><span data-stu-id="83e93-171">It does include borrowed qubits.</span></span>

<span data-ttu-id="83e93-172">2つの操作モードがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="83e93-172">Two modes of operation are supported.</span></span> <span data-ttu-id="83e93-173">モードを選択するには、QCTraceSimulatorConfiguration. 最適化の深さを設定します。</span><span class="sxs-lookup"><span data-stu-id="83e93-173">Mode is selected by setting QCTraceSimulatorConfiguration.OptimizeDepth.</span></span>

<span data-ttu-id="83e93-174">最適化の __深さ = true:__ QubitManager は、qubit の使用を要求されるたびに、新しい qubit が割り当てられないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="83e93-174">__OptimizeDepth=true:__ QubitManager is discouraged from qubit reuse and allocates new qubit every time it is asked for a qubit.</span></span> <span data-ttu-id="83e93-175">ルート操作の __深さ__ は、最小の深さ (下限) になります。</span><span class="sxs-lookup"><span data-stu-id="83e93-175">For the root operation __Depth__ becomes the minimum depth (lower bound).</span></span> <span data-ttu-id="83e93-176">この深さでは、互換性のある __幅__ がレポートされます (両方とも同時に実現できます)。</span><span class="sxs-lookup"><span data-stu-id="83e93-176">Compatible __Width__ is reported for this depth (both can be achieved at the same time).</span></span> <span data-ttu-id="83e93-177">この深さでは、この幅が最適でない可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="83e93-177">Note, that this width will likely be not optimal given this depth.</span></span> <span data-ttu-id="83e93-178">再利用が想定されているため、ルート操作の場合、 __Qubitcount__ は Width よりも小さくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="83e93-178">__QubitCount__ may be lower than Width for the root operation because it assumes reuse.</span></span>

<span data-ttu-id="83e93-179">最適化の __深さ = false:__ QubitManager は、qubits を再利用することをお勧めします。新たにリリースされた qubits を再利用して、新しいものを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="83e93-179">__OptimizeDepth=false:__ QubitManager is encouraged to reuse qubits and will reuse released qubits before allocating new ones.</span></span> <span data-ttu-id="83e93-180">ルート操作の __幅__ は、最小幅 (下限) になります。</span><span class="sxs-lookup"><span data-stu-id="83e93-180">For the root operation __Width__ becomes the minimal width (lower bound).</span></span> <span data-ttu-id="83e93-181">互換性のある __深さ__ がレポートされます。</span><span class="sxs-lookup"><span data-stu-id="83e93-181">Compatible __Depth__ is reported on which it can be achieved.</span></span> <span data-ttu-id="83e93-182">__Qubitcount__ は、借りていないことを前提として、ルート操作の __幅__ と同じになります。</span><span class="sxs-lookup"><span data-stu-id="83e93-182">__QubitCount__ will be the same as __Width__ for the root operation assuming no borrowing.</span></span>

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="83e93-183">測定結果の確率を指定する</span><span class="sxs-lookup"><span data-stu-id="83e93-183">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="83e93-184"><xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability>名前空間のを使用し <xref:Microsoft.Quantum.Diagnostics> て、測定演算の予想される確率に関する情報を提供できます。</span><span class="sxs-lookup"><span data-stu-id="83e93-184">You can use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> from the <xref:Microsoft.Quantum.Diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="83e93-185">詳細については、「[クォンタムトレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83e93-185">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="83e93-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="83e93-186">See also</span></span>

- [<span data-ttu-id="83e93-187">クォンタムトレースシミュレーター</span><span class="sxs-lookup"><span data-stu-id="83e93-187">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="83e93-188">量子 Toffoli シミュレーター</span><span class="sxs-lookup"><span data-stu-id="83e93-188">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="83e93-189">量子完全状態シミュレーター</span><span class="sxs-lookup"><span data-stu-id="83e93-189">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 
