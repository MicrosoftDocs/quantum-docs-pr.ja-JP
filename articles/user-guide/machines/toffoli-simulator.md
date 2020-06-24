---
title: Quantum Development Kit Toffoli シミュレーター
description: Microsoft QDK Toffoli シミュレーターについて説明します。これは、何百万もの qubits で使用できる特殊な用途のクォンタムシミュレーターです。
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 8a29caaa0fa058600a74e7d130e644374cbfa19c
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276033"
---
# <a name="quantum-development-kit-toffoli-simulator"></a><span data-ttu-id="2e353-103">Quantum Development Kit Toffoli シミュレーター</span><span class="sxs-lookup"><span data-stu-id="2e353-103">Quantum Development Kit Toffoli Simulator</span></span>

<span data-ttu-id="2e353-104">Quantum Development Kit には、Toffoli シミュレーターが用意されています。これは、X、CNOT、およびマルチ制御の X クォンタム操作に制限されているクォンタムアルゴリズムをシミュレートできる特殊な用途のシミュレーターです (すべての従来のロジックと計算を使用できます)。</span><span class="sxs-lookup"><span data-stu-id="2e353-104">The Quantum Development Kit provides a Toffoli simulator, which is a special-purpose simulator that can simulate quantum algorithms that are limited to X, CNOT, and multi-controlled X quantum operations (all classical logic and computations are available).</span></span>

<span data-ttu-id="2e353-105">Toffoli シミュレーターは、[完全な状態シミュレーター](xref:microsoft.quantum.machines.full-state-simulator)よりも操作の方がはるかに制限されていますが、はるかに多くの qubits をシミュレートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2e353-105">While the Toffoli simulator is much more restricted in operation than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it can simulate far more qubits.</span></span>
<span data-ttu-id="2e353-106">Toffoli シミュレーターは何百万もの qubits と共に使用できますが、通常、完全な状態シミュレーターは約30に制限されています。</span><span class="sxs-lookup"><span data-stu-id="2e353-106">The Toffoli simulator can be used with millions of qubits, while the full state simulator is generally limited to about 30.</span></span>
<span data-ttu-id="2e353-107">コンピューターで Q # で記述されたクォンタムアルゴリズムの限られたセットを実行し、デバッグすることができます。たとえば、ブール関数を評価する oracles は、これらのゲートを使用して実装できます。したがって、このシミュレーターを使用して、多数の qubits がテストされます。</span><span class="sxs-lookup"><span data-stu-id="2e353-107">It can execute and debug a limited set of quantum algorithms written in Q# on your computer; for instance, oracles that evaluate Boolean functions can be implemented using these gates and so tested on vary large numbers of qubits using this simulator.</span></span>

<span data-ttu-id="2e353-108">このクォンタムシミュレーターはクラスを介して公開されてい `ToffoliSimulator` ます。</span><span class="sxs-lookup"><span data-stu-id="2e353-108">This quantum simulator is exposed via the `ToffoliSimulator` class.</span></span>
<span data-ttu-id="2e353-109">シミュレーターを使用するには、このクラスのインスタンスを作成し、残りの `Run` パラメーターと共に実行するクォンタム操作のメソッドに渡すだけです。</span><span class="sxs-lookup"><span data-stu-id="2e353-109">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a><span data-ttu-id="2e353-110">その他の操作</span><span class="sxs-lookup"><span data-stu-id="2e353-110">Other Operations</span></span>

<span data-ttu-id="2e353-111">は、 `ToffoliSimulator` `R` 結果として `Exp` 得られる操作が id と等しい場合や、累乗 Paulis をサポートしています (やなど) `X` 。</span><span class="sxs-lookup"><span data-stu-id="2e353-111">The `ToffoliSimulator` supports rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation is equal to `X` or to the identity.</span></span>

<span data-ttu-id="2e353-112">測定とアサートはサポートされていますが、これは Ponly でのみサポートされてい `Z` ます。</span><span class="sxs-lookup"><span data-stu-id="2e353-112">Measurement and assert are supported, but only in the Pauli `Z` basis.</span></span>
<span data-ttu-id="2e353-113">測定値の確率は常に0または1になることに注意してください。Toffoli シミュレーターにはランダム性はありません。</span><span class="sxs-lookup"><span data-stu-id="2e353-113">Note that the probability of some measurement is always either 0 or 1; there is no randomness in the Toffoli simulator.</span></span>

<span data-ttu-id="2e353-114">`DumpMachine` と `DumpRegister` がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2e353-114">`DumpMachine` and `DumpRegister` are supported.</span></span>
<span data-ttu-id="2e353-115">どちらも、 `Z` 各 qubit の現在のベースの状態を出力します (1 行あたり1つの qubit)。</span><span class="sxs-lookup"><span data-stu-id="2e353-115">They both output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="qubitcount"></a><span data-ttu-id="2e353-116">QubitCount</span><span class="sxs-lookup"><span data-stu-id="2e353-116">QubitCount</span></span>

<span data-ttu-id="2e353-117">既定では、は `ToffoliSimulator` 65536 qubits の領域を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2e353-117">By default, the `ToffoliSimulator` allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="2e353-118">アルゴリズムにこの値以上が必要な場合は、パラメーターの値をコンストラクターに指定することで、qubit カウントを変更でき `qubitCount` ます。</span><span class="sxs-lookup"><span data-stu-id="2e353-118">If your algorithm requires more than this, you can change the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="2e353-119">追加の qubit には、追加のメモリが必要であるため、必要な qubit の数を過剰に見積もることには大きなコストはかかりません。</span><span class="sxs-lookup"><span data-stu-id="2e353-119">Each additional qubit requires an additional byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="2e353-120">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2e353-120">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
