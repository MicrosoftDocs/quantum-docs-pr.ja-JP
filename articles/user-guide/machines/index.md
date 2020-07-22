---
title: 量子シミュレーターと Q# プログラム
description: Q# プログラムのターゲット マシンとして使用できる量子シミュレーターについて説明します。
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 6/17/2020
ms.topic: article
uid: microsoft.quantum.machines
ms.openlocfilehash: c81226ba3e50b65cb1012e885866bd6fcc3764d7
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871163"
---
# <a name="quantum-simulators"></a><span data-ttu-id="49e43-103">量子シミュレーター</span><span class="sxs-lookup"><span data-stu-id="49e43-103">Quantum simulators</span></span>

<span data-ttu-id="49e43-104">量子シミュレーターは従来型コンピューターで実行され、"*ターゲット マシン*" として動作するソフトウェア プログラムであり、量子プログラムをある環境で実行して、さまざまな演算に量子ビットがどのように反応するかを予測するためのテストを行えるようにします。</span><span class="sxs-lookup"><span data-stu-id="49e43-104">Quantum simulators are software programs that run on classical computers and act as the *target machine* for a Q# program, making it possible to run and test quantum programs in an environment that predicts how qubits will react to different operations.</span></span> <span data-ttu-id="49e43-105">この記事では、Quantum Development Kit (QDK) に含まれている量子シミュレーターについて説明します。また、コマンド ラインまたは従来の言語で記述されたドライバー コードなどを使用して、量子シミュレーターに Q# プログラムを渡すさまざまな方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="49e43-105">This article describes which quantum simulators are included with the Quantum Development Kit (QDK), and different ways that you can pass a Q# program to the quantum simulators, for example, via the command line or by using driver code written in a classical language.</span></span>  



## <a name="the-quantum-development-kit-qdk-quantum-simulators"></a><span data-ttu-id="49e43-106">Quantum Development Kit (QDK) の量子シミュレーター</span><span class="sxs-lookup"><span data-stu-id="49e43-106">The Quantum Development Kit (QDK) quantum simulators</span></span>

<span data-ttu-id="49e43-107">量子シミュレーターは、アルゴリズムに対して量子プリミティブを実装する役割を担います。</span><span class="sxs-lookup"><span data-stu-id="49e43-107">The quantum simulator is responsible for providing implementations of quantum primitives for an algorithm.</span></span> <span data-ttu-id="49e43-108">これには、`H`、`CNOT`、`Measure` などのプリミティブ操作だけでなく、量子ビットの管理と追跡も含まれます。</span><span class="sxs-lookup"><span data-stu-id="49e43-108">This includes primitive operations such as `H`, `CNOT`, and `Measure`, as well as qubit management and tracking.</span></span> <span data-ttu-id="49e43-109">QDK には、同じ量子アルゴリズムの異なる実行モデルを表すさまざまなクラスの量子シミュレーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="49e43-109">The QDK includes different classes of quantum simulators representing different execution models for the same quantum algorithm.</span></span> 


<span data-ttu-id="49e43-110">それぞれの種類の量子シミュレーターは、これらのプリミティブに対して異なる実装を提供できます。</span><span class="sxs-lookup"><span data-stu-id="49e43-110">Each type of quantum simulator can provide different implementations of these primitives.</span></span> <span data-ttu-id="49e43-111">たとえば、[完全状態シミュレーター](xref:microsoft.quantum.machines.full-state-simulator)では、[量子状態ベクトル](xref:microsoft.quantum.glossary#quantum-state)を完全にシミュレートすることで、量子アルゴリズムが実行されます。一方、[量子コンピューターのトレース シミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)では、実際の量子状態はまったく考慮されません。</span><span class="sxs-lookup"><span data-stu-id="49e43-111">For example, the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator) runs the quantum algorithm by fully simulating the [quantum state vector](xref:microsoft.quantum.glossary#quantum-state), whereas the [quantum computer trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) doesn't consider the actual quantum state at all.</span></span> <span data-ttu-id="49e43-112">代わりに、アルゴリズムのゲート、量子ビット、およびその他のリソースの使用状況を追跡します。</span><span class="sxs-lookup"><span data-stu-id="49e43-112">Rather, it tracks gate, qubit, and other resource usage for the algorithm.</span></span>

### <a name="quantum-machine-classes"></a><span data-ttu-id="49e43-113">量子マシン クラス</span><span class="sxs-lookup"><span data-stu-id="49e43-113">Quantum machine classes</span></span>

<span data-ttu-id="49e43-114">今後、他の種類のシミュレーションや、量子ハードウェアでの実行をサポートするために、QDK に追加の量子マシン クラスが定義される予定です。</span><span class="sxs-lookup"><span data-stu-id="49e43-114">In the future, the QDK will define additional quantum machine classes to support other types of simulation and to support execution on quantum hardware.</span></span> <span data-ttu-id="49e43-115">基になるコンピューターの実装を変更してもアルゴリズムが一定に保たれるようにすることで、シミュレーションのアルゴリズムのテストとデバッグが簡単になり、アルゴリズムが変更されていないという確信を持って実際のハードウェアで実行できます。</span><span class="sxs-lookup"><span data-stu-id="49e43-115">Allowing the algorithm to stay constant while varying the underlying machine implementation makes it easy to test and debug an algorithm in simulation and then run it on real hardware with confidence that the algorithm hasn't changed.</span></span>

<span data-ttu-id="49e43-116">QDK には複数の量子マシン クラスが含まれており、すべて `Microsoft.Quantum.Simulation.Simulators` 名前空間に定義されています。</span><span class="sxs-lookup"><span data-stu-id="49e43-116">The QDK includes several quantum machine classes, all defined in the `Microsoft.Quantum.Simulation.Simulators` namespace.</span></span>

|<span data-ttu-id="49e43-117">シミュレーター</span><span class="sxs-lookup"><span data-stu-id="49e43-117">Simulator</span></span> |<span data-ttu-id="49e43-118">クラス</span><span class="sxs-lookup"><span data-stu-id="49e43-118">Class</span></span>|<span data-ttu-id="49e43-119">説明</span><span class="sxs-lookup"><span data-stu-id="49e43-119">Description</span></span>|
|-----|------|---|
|[<span data-ttu-id="49e43-120">完全状態シミュレーター</span><span class="sxs-lookup"><span data-stu-id="49e43-120">Full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator)| `QuantumSimulator` | <span data-ttu-id="49e43-121">量子アルゴリズムを実行およびデバッグします。これは約 30 量子ビットに制限されています。</span><span class="sxs-lookup"><span data-stu-id="49e43-121">Runs and debugs quantum algorithms, and is limited to about 30 qubits.</span></span> |
|[<span data-ttu-id="49e43-122">簡易リソース推定器</span><span class="sxs-lookup"><span data-stu-id="49e43-122">Simple resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)| `ResourcesEstimator` | <span data-ttu-id="49e43-123">量子アルゴリズムを実行するために必要なリソースの最上位レベル分析を実行、千単位の量子ビットをサポートします。</span><span class="sxs-lookup"><span data-stu-id="49e43-123">Performs a top level analysis of the resources needed to run a quantum algorithm, and supports thousands of qubits.</span></span>|
|[<span data-ttu-id="49e43-124">トレースベースのリソース推定器</span><span class="sxs-lookup"><span data-stu-id="49e43-124">Trace-based resource estimator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)|  `QCTraceSimulator` |<span data-ttu-id="49e43-125">アルゴリズムの呼び出しグラフ全体におけるリソース消費の高度な分析を実行し、千単位の量子ビットをサポートします。</span><span class="sxs-lookup"><span data-stu-id="49e43-125">Runs advanced analysis of resources consumptions for the algorithm's entire call-graph, and supports thousands of qubits.</span></span>|
|[<span data-ttu-id="49e43-126">Toffoli シミュレーター</span><span class="sxs-lookup"><span data-stu-id="49e43-126">Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)| `ToffoliSimulator` |<span data-ttu-id="49e43-127">`X`、`CNOT`、および複数制御された `X` 量子操作に制限される量子アルゴリズムをシミュレートし、100 万の量子ビットをサポートします。</span><span class="sxs-lookup"><span data-stu-id="49e43-127">Simulates quantum algorithms that are limited to `X`, `CNOT`, and multi-controlled `X` quantum operations, and supports million of qubits.</span></span> |

## <a name="invoking-the-quantum-simulator"></a><span data-ttu-id="49e43-128">量子シミュレーターの呼び出し</span><span class="sxs-lookup"><span data-stu-id="49e43-128">Invoking the quantum simulator</span></span>

<span data-ttu-id="49e43-129">「[Q# プログラムの実行方法](xref:microsoft.quantum.guide.host-programs)」では、Q# コードを量子シミュレーターに渡す次の 3 つの方法が紹介されています。</span><span class="sxs-lookup"><span data-stu-id="49e43-129">In [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs), three ways of passing the Q# code to the quantum simulator are demonstrated:</span></span> 

* <span data-ttu-id="49e43-130">コマンド ラインを使用する</span><span class="sxs-lookup"><span data-stu-id="49e43-130">Using the command line</span></span>
* <span data-ttu-id="49e43-131">Python ホスト プログラムを使用する</span><span class="sxs-lookup"><span data-stu-id="49e43-131">Using a Python host program</span></span>
* <span data-ttu-id="49e43-132">C# ホスト プログラムを使用する</span><span class="sxs-lookup"><span data-stu-id="49e43-132">Using a C# host program</span></span>

<span data-ttu-id="49e43-133">量子コンピュータ－は通常の .NET クラスのインスタンスであるため、.NET クラスと同様に、コンストラクターを呼び出すことによって作成します。</span><span class="sxs-lookup"><span data-stu-id="49e43-133">Quantum machines are instances of normal .NET classes, so they are created by invoking their constructor, just like any .NET class.</span></span> <span data-ttu-id="49e43-134">その方法は、Q# プログラムの実行方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="49e43-134">How you do this depends on how you run the Q# program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="49e43-135">次のステップ</span><span class="sxs-lookup"><span data-stu-id="49e43-135">Next steps</span></span>

* <span data-ttu-id="49e43-136">さまざまな環境で Q# プログラムのターゲット マシンを呼び出す方法の詳細について、「[Q# プロブラムの実行方法](xref:microsoft.quantum.guide.host-programs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49e43-136">For details about how to invoke target machines for Q# programs in different environments, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
