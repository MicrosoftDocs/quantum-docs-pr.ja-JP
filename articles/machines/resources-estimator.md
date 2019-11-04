---
title: Quantum 開発キットリソースの推定機能 |Microsoft Docs
description: Microsoft の Quantum 開発キットリソースの概要
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 591e306b3001934bd81342a533e3f6ca25129781
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184986"
---
# <a name="the-resourcesestimator-target-machine"></a><span data-ttu-id="15c93-103">ResourcesEstimator ターゲットコンピューター</span><span class="sxs-lookup"><span data-stu-id="15c93-103">The ResourcesEstimator Target Machine</span></span>

<span data-ttu-id="15c93-104">名前が示すように、`ResourcesEstimator` は、クォンタムコンピューターで Q # 操作の特定のインスタンスを実行するために必要なリソースを推定します。</span><span class="sxs-lookup"><span data-stu-id="15c93-104">As the name implies, the `ResourcesEstimator` estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>
<span data-ttu-id="15c93-105">これを実現するには、実際にクォンタムコンピューターの状態をシミュレートせずに、クォンタム操作を実行します。このため、数千個の qubits を使用する Q # 操作のリソースを見積もることができます。</span><span class="sxs-lookup"><span data-stu-id="15c93-105">It accomplishes this by executing the quantum operation without actually simulating the state of a quantum computer; for this reason, it can estimate resources for Q# operations that use thousands of qubits.</span></span>

## <a name="usage"></a><span data-ttu-id="15c93-106">使用量</span><span class="sxs-lookup"><span data-stu-id="15c93-106">Usage</span></span>

<span data-ttu-id="15c93-107">`ResourcesEstimator` は別の種類のターゲットマシンであるため、任意の Q # 操作を実行するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="15c93-107">The `ResourcesEstimator` is just another type of target machine, thus it can be used to run any Q# operation.</span></span> 

<span data-ttu-id="15c93-108">他のターゲットマシンと同様に、 C#ホストプログラムで使用するには、インスタンスを作成し、操作の `Run` メソッドの最初のパラメーターとして渡します。</span><span class="sxs-lookup"><span data-stu-id="15c93-108">As other target machines, to use it on a C# host program create an instance and pass it as the first parameter of the operation's `Run` method:</span></span>

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

<span data-ttu-id="15c93-109">この例に示すように、`ResourcesEstimator` には、タブ区切り値 (TSV) を含むテーブルを生成するための `ToTSV()` メソッドが用意されています。これは、ファイルに保存したり、分析のためにコンソールに書き込んだたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="15c93-109">As the example shows, the `ResourcesEstimator` provides a `ToTSV()` method to generate a table with tab-seperated-values (TSV) that can be saved into a file or written to the console for analysis.</span></span> <span data-ttu-id="15c93-110">上記のプログラムの出力は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="15c93-110">The output of the above program should look something like this:</span></span>

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
> <span data-ttu-id="15c93-111">`ResourcesEstimator` は、実行のたびに計算をリセットしません。同じインスタンスを使用して別の操作を実行すると、既存の結果に基づいて集計されたカウントを保持します。</span><span class="sxs-lookup"><span data-stu-id="15c93-111">The `ResourcesEstimator` does not reset its calculations on every run, if the same instance is used to execute another operation it will keep aggregating counts on top of existing results.</span></span>
> <span data-ttu-id="15c93-112">実行間の計算をリセットする必要がある場合は、実行のたびに新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="15c93-112">If you need to reset calculations between runs, create a new instance for every execution.</span></span>


## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="15c93-113">プログラムによる推定データの取得</span><span class="sxs-lookup"><span data-stu-id="15c93-113">Programmatically Retrieving the Estimated Data</span></span>

<span data-ttu-id="15c93-114">TSV テーブルに加えて、推定されるリソースは、`ResourcesEstimator`の `Data` プロパティを使用してプログラムで取得できます。</span><span class="sxs-lookup"><span data-stu-id="15c93-114">In addition to a TSV table, the resources estimated can be retrieved programmatically via the `ResourcesEstimator`'s `Data` property.</span></span> <span data-ttu-id="15c93-115">`Data` は、メトリック名でインデックス付けされた `Metric` と `Sum`の2つの列を持つ `System.DataTable` インスタンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="15c93-115">`Data` provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics names.</span></span>

<span data-ttu-id="15c93-116">次のコードは、Q # 操作によって使用される `QubitClifford`、`T`、および `CNOT` ゲートの合計数を取得して印刷する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="15c93-116">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` gates used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="15c93-117">報告されるメトリック</span><span class="sxs-lookup"><span data-stu-id="15c93-117">Metrics Reported</span></span>

<span data-ttu-id="15c93-118">`ResourcesEstimator`によって推定されるメトリックの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="15c93-118">The following is the list of metrics estimated by the `ResourcesEstimator`:</span></span>

* <span data-ttu-id="15c93-119">__Cnot__: 実行された cnot (被制御 P# li X ゲートとも呼ばれる) ゲートの数。</span><span class="sxs-lookup"><span data-stu-id="15c93-119">__CNOT__: The count of CNOT (also known as the Controlled Pauli X gate) gates executed.</span></span>
* <span data-ttu-id="15c93-120">__Qubitclifford__: 実行された1つの Qubit clifフォードおよび P# li ゲートの数。</span><span class="sxs-lookup"><span data-stu-id="15c93-120">__QubitClifford__: The count of any single qubit Clifford and Pauli gates executed.</span></span>
* <span data-ttu-id="15c93-121">__Measure__: 実行された測定値の数。</span><span class="sxs-lookup"><span data-stu-id="15c93-121">__Measure__:  The count of any measurements executed.</span></span>
* <span data-ttu-id="15c93-122">__R__: 実行された1つの qubit ローテーション (T、Clifford、および P# li を除く) の数。</span><span class="sxs-lookup"><span data-stu-id="15c93-122">__R__: The count of any single qubit rotations executed, excluding T, Clifford and Pauli gates.</span></span>
* <span data-ttu-id="15c93-123">__T__: t ゲート、T_x = .H、T_y = hy、実行された t ゲート、および = hy. t .h を含む、t ゲートとその数。</span><span class="sxs-lookup"><span data-stu-id="15c93-123">__T__: The count of T gates and their conjugates, including the T gate, T_x = H.T.H, and T_y = Hy.T.Hy, executed.</span></span>
* <span data-ttu-id="15c93-124">__Depth__: Q # 操作によって実行されるクォンタム回線の深さ。</span><span class="sxs-lookup"><span data-stu-id="15c93-124">__Depth__: Depth of the quantum circuit executed by the Q# operation.</span></span> <span data-ttu-id="15c93-125">既定では、T ゲートのみが深さでカウントされます。詳細については、「[深度カウンター](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15c93-125">By default, only T gates are counted in the depth, see [depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) for details.</span></span>
* <span data-ttu-id="15c93-126">__Width__: Q # 操作の実行中に割り当てられた qubits の最大数。</span><span class="sxs-lookup"><span data-stu-id="15c93-126">__Width__: Maximum number of qubits allocated during the execution of the Q# operation.</span></span>
* <span data-ttu-id="15c93-127">__BorrowedWidth__: Q # 操作内で借用される qubits の最大数。</span><span class="sxs-lookup"><span data-stu-id="15c93-127">__BorrowedWidth__: Maximum number of qubits borrowed inside the Q# operation.</span></span>


## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="15c93-128">測定結果の確率を提供する</span><span class="sxs-lookup"><span data-stu-id="15c93-128">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="15c93-129"><xref:microsoft.quantum.primitive> 名前空間の <xref:microsoft.quantum.primitive.assertprob> を使用すると、Q # プログラムの実行を促進するために、測定の予想される確率に関する情報を提供できます。</span><span class="sxs-lookup"><span data-stu-id="15c93-129"><xref:microsoft.quantum.primitive.assertprob> from the <xref:microsoft.quantum.primitive> namespace can be used to provide information about the expected probability of a measurement to help drive the execution of the Q# program.</span></span> <span data-ttu-id="15c93-130">次の例を使って説明します。</span><span class="sxs-lookup"><span data-stu-id="15c93-130">The following example illustrates this:</span></span>

```qsharp
operation Teleportation (source : Qubit, target : Qubit) : Unit {

    using (ancilla = Qubit()) {

        H(ancilla);
        CNOT(ancilla, target);

        CNOT(source, ancilla);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [ancilla], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(ancilla) == One) { X(target); X(ancilla); }
    }
}
```

<span data-ttu-id="15c93-131">`ResourcesEstimator` が検出されると `AssertProb` `source` の測定 `PauliZ` を記録し、`ancilla` 確率が0.5 の `Zero` の結果を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15c93-131">When the `ResourcesEstimator` encounters `AssertProb` it will record that measuring `PauliZ` on `source` and `ancilla` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="15c93-132">後で `M` を実行すると、結果の確率の記録された値が検出され、`M` は `Zero` または確率が0.5 の `One` を返します。</span><span class="sxs-lookup"><span data-stu-id="15c93-132">When it executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span>


## <a name="see-also"></a><span data-ttu-id="15c93-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="15c93-133">See also</span></span>

<span data-ttu-id="15c93-134">`ResourcesEstimator` は、quantum コンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の上に構築されています。これにより、豊富なメトリックセットが提供されます。また、完全な呼び出しグラフでメトリックをレポートする機能や、Q # プログラムでのバグの検出に役立つ[distinct 入力チェッカー](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)などの機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="15c93-134">The `ResourcesEstimator` is built on top of the quantum computer [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics, the ability to report metrics on the full call-graph, and features like [distinct inputs checker](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) to help find bugs on Q# programs.</span></span> <span data-ttu-id="15c93-135">詳細については、 [trace シミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="15c93-135">Please refer to the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) documentation for more information.</span></span>

