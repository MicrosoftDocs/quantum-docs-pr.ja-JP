---
title: Quantum Toffoli シミュレーター-Quantum 開発キット
description: Microsoft QDK Toffoli シミュレーターについて説明します。これは、何百万もの qubits で使用できる特殊な用途のクォンタムシミュレーターです。
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 6/25/2020
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6a0885035c12a99ae43533f04cdc95c5c529380a
ms.sourcegitcommit: 11bd357baeb6ab53a402882979e75964d0869b57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2020
ms.locfileid: "88992211"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a><span data-ttu-id="0f7c9-103">Quantum 開発キット (QDK) Toffoli シミュレーター</span><span class="sxs-lookup"><span data-stu-id="0f7c9-103">Quantum Development Kit (QDK) Toffoli simulator</span></span>

<span data-ttu-id="0f7c9-104">QDK Toffoli シミュレーターは、限られたスコープの特別な用途のシミュレーターで、 `X` 、、およびの複数制御されたクォンタム操作のみをサポートしてい `CNOT` `X` ます。</span><span class="sxs-lookup"><span data-stu-id="0f7c9-104">The QDK Toffoli simulator is a special-purpose simulator with a limited scope and only supports `X`, `CNOT`, and multi-controlled `X` quantum operations.</span></span> <span data-ttu-id="0f7c9-105">すべての従来のロジックと計算を利用できます。</span><span class="sxs-lookup"><span data-stu-id="0f7c9-105">All classical logic and computations are available.</span></span>

<span data-ttu-id="0f7c9-106">Toffoli シミュレーターは、 [完全な状態シミュレーター](xref:microsoft.quantum.machines.full-state-simulator)よりも機能が制限されていますが、はるかに多くの qubits をシミュレートできるという利点があります。</span><span class="sxs-lookup"><span data-stu-id="0f7c9-106">While the Toffoli simulator is more restricted in functionality than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it has the advantage of being able to simulate far more qubits.</span></span> <span data-ttu-id="0f7c9-107">Toffoli シミュレーターは何百万もの qubits と共に使用できますが、完全な状態シミュレーターは約 30 qubits に制限されています。</span><span class="sxs-lookup"><span data-stu-id="0f7c9-107">The Toffoli simulator can be used with millions of qubits, while the full state simulator is limited to about 30 qubits.</span></span> <span data-ttu-id="0f7c9-108">これは、たとえば、ブール関数を評価する oracles を使用した場合に便利です。サポートされているアルゴリズムの限られたセットを使用して実装し、多数の qubits でテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="0f7c9-108">This is useful, for example, with oracles that evaluate Boolean functions - they can be implemented using the limited set of supported algorithms and tested on a large number of qubits.</span></span>

## <a name="invoking-the-toffoli-simulator"></a><span data-ttu-id="0f7c9-109">Toffoli シミュレーターの呼び出し</span><span class="sxs-lookup"><span data-stu-id="0f7c9-109">Invoking the Toffoli simulator</span></span>

<span data-ttu-id="0f7c9-110">クラスを使用して Toffoli シミュレーターを公開し `ToffoliSimulator` ます。</span><span class="sxs-lookup"><span data-stu-id="0f7c9-110">You expose the Toffoli simulator via the `ToffoliSimulator` class.</span></span> <span data-ttu-id="0f7c9-111">詳細については、「 [ Q# プログラムを実行する方法](xref:microsoft.quantum.guide.host-programs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f7c9-111">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-toffoli-simulator-from-c"></a><span data-ttu-id="0f7c9-112">C から Toffoli シミュレーターを呼び出す#</span><span class="sxs-lookup"><span data-stu-id="0f7c9-112">Invoking the Toffoli simulator from C#</span></span>

<span data-ttu-id="0f7c9-113">他のターゲット マシンと同様に、最初に `ToffoliSimulator` クラスのインスタンスを作成し、それを操作の `Run` メソッドの最初のパラメーターとして渡します。</span><span class="sxs-lookup"><span data-stu-id="0f7c9-113">As with other target machines, you first create an instance of the `ToffoliSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="0f7c9-114">`QuantumSimulator` クラスとは異なり、`ToffoliSimulator` クラスでは <xref:System.IDisposable> インターフェイスが実装されていないため、これを `using` ステートメント内で囲む必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0f7c9-114">Note that, unlike the `QuantumSimulator` class, the `ToffoliSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a><span data-ttu-id="0f7c9-115">Python から Toffoli シミュレーターを呼び出す</span><span class="sxs-lookup"><span data-stu-id="0f7c9-115">Invoking the Toffoli simulator from Python</span></span>

<span data-ttu-id="0f7c9-116">インポートされた操作で、Python ライブラリの [toffoli_simulate ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) メソッドを使用し Q# ます。</span><span class="sxs-lookup"><span data-stu-id="0f7c9-116">Use the [toffoli_simulate()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a><span data-ttu-id="0f7c9-117">コマンドラインからの Toffoli シミュレーターの呼び出し</span><span class="sxs-lookup"><span data-stu-id="0f7c9-117">Invoking the Toffoli simulator from the command line</span></span>

<span data-ttu-id="0f7c9-118">コマンドラインからプログラムを実行する場合は、 Q# **--シミュレーター** (または **-s** ショートカット) パラメーターを使用して、Toffoli シミュレーターターゲットコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="0f7c9-118">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the Toffoli simulator target machine.</span></span> <span data-ttu-id="0f7c9-119">次のコマンドは、リソースの推定機能を使用してプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="0f7c9-119">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a><span data-ttu-id="0f7c9-120">Juptyer Notebook から Toffoli シミュレーターを呼び出す</span><span class="sxs-lookup"><span data-stu-id="0f7c9-120">Invoking the Toffoli simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="0f7c9-121">この Q# 操作を実行するには、I マジックコマンド [% toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) を使用し Q# ます。</span><span class="sxs-lookup"><span data-stu-id="0f7c9-121">Use the IQ# magic command [%toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) to run the Q# operation.</span></span>

```
%toffoli myOperation
```

## <a name="supported-operations"></a><span data-ttu-id="0f7c9-122">サポート対象の操作</span><span class="sxs-lookup"><span data-stu-id="0f7c9-122">Supported operations</span></span>

<span data-ttu-id="0f7c9-123">Toffoli シミュレーターは次をサポートします。</span><span class="sxs-lookup"><span data-stu-id="0f7c9-123">The Toffoli simulator supports:</span></span>

* <span data-ttu-id="0f7c9-124">回転と累乗 Paulis (やなど `R` ) `Exp` は、結果の操作が `X` または id 行列と等しい場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="0f7c9-124">Rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation equals `X` or the identity matrix.</span></span>
* <span data-ttu-id="0f7c9-125">測定および [アサート](xref:microsoft.quantum.diagnostics.assertmeasurement) 操作。ただし、ponly の場合にのみ実行さ `Z` れます。</span><span class="sxs-lookup"><span data-stu-id="0f7c9-125">Measurement and [assert](xref:microsoft.quantum.diagnostics.assertmeasurement) operations, but only in the Pauli `Z` basis.</span></span> <span data-ttu-id="0f7c9-126">測定演算の確率は常に **0** または **1**であることに注意してください。Toffoli シミュレーターにはランダム性はありません。</span><span class="sxs-lookup"><span data-stu-id="0f7c9-126">Note that a measurement operation's probability is always either **0** or **1**; there is no randomness in the Toffoli simulator.</span></span>
* <span data-ttu-id="0f7c9-127">`DumpMachine``DumpRegister`関数と関数。</span><span class="sxs-lookup"><span data-stu-id="0f7c9-127">`DumpMachine` and `DumpRegister` functions.</span></span>
<span data-ttu-id="0f7c9-128">どちらの関数も `Z` 、各 qubit の現在の状態を出力し、1行に1つの qubit を出力します。</span><span class="sxs-lookup"><span data-stu-id="0f7c9-128">Both functions output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="specifying-the-number-of-qubits"></a><span data-ttu-id="0f7c9-129">Qubits の数の指定</span><span class="sxs-lookup"><span data-stu-id="0f7c9-129">Specifying the number of qubits</span></span>

<span data-ttu-id="0f7c9-130">既定では、 `ToffoliSimulator` インスタンスは 65536 qubits の領域を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0f7c9-130">By default, a `ToffoliSimulator` instance allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="0f7c9-131">アルゴリズムにより多くの qubits が必要な場合は、コンストラクターにパラメーターの値を指定して、qubits カウントを指定でき `qubitCount` ます。</span><span class="sxs-lookup"><span data-stu-id="0f7c9-131">If your algorithm requires more qubits than this, you can specify the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="0f7c9-132">追加の qubit は1バイトのメモリしか必要としないので、必要な qubit の数を過剰に見積もることには大きなコストはかかりません。</span><span class="sxs-lookup"><span data-stu-id="0f7c9-132">Each additional qubit requires only one byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="0f7c9-133">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f7c9-133">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a><span data-ttu-id="0f7c9-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f7c9-134">See also</span></span>

- [<span data-ttu-id="0f7c9-135">クォンタムリソースの推定</span><span class="sxs-lookup"><span data-stu-id="0f7c9-135">Quantum Resources Estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="0f7c9-136">クォンタムトレースシミュレーター</span><span class="sxs-lookup"><span data-stu-id="0f7c9-136">Quantum Trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="0f7c9-137">クォンタムの完全な状態シミュレーター</span><span class="sxs-lookup"><span data-stu-id="0f7c9-137">Quantum Full State simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 