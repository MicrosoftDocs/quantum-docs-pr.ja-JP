---
title: 完全な状態の量子シミュレーター-Quantum 開発キット
description: Q#Microsoft Quantum Development Kit 完全な状態シミュレーターでプログラムを実行する方法について説明します。
author: anpaz-msft
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 632af681c5818ab7246c0f5849a8b8e716b570cb
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833382"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a><span data-ttu-id="44c0f-103">Quantum 開発キット (QDK) 完全な状態シミュレーター</span><span class="sxs-lookup"><span data-stu-id="44c0f-103">Quantum Development Kit (QDK) full state simulator</span></span>

<span data-ttu-id="44c0f-104">QDK には、ローカルコンピューター上のクォンタムコンピューターをシミュレートする完全な状態シミュレーターが用意されています。</span><span class="sxs-lookup"><span data-stu-id="44c0f-104">The QDK provides a full state simulator that simulates a quantum machine on your local computer.</span></span> <span data-ttu-id="44c0f-105">完全な状態シミュレーターを使用して、で記述されたクォンタムアルゴリズムを実行およびデバッグし Q# 、最大30個の qubits を利用できます。</span><span class="sxs-lookup"><span data-stu-id="44c0f-105">You can use the full state simulator to run and debug quantum algorithms written in Q#, utilizing up to 30 qubits.</span></span> <span data-ttu-id="44c0f-106">完全な状態シミュレーターは、Microsoft Research の  [Liq $ Ui | \rangle $](http://stationq.github.io/Liquid/) プラットフォームで使用されるクォンタムシミュレーターに似ています。</span><span class="sxs-lookup"><span data-stu-id="44c0f-106">The full state simulator is similar to the quantum simulator used in the  [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) platform from Microsoft Research.</span></span>

## <a name="invoking-and-running-the-full-state-simulator"></a><span data-ttu-id="44c0f-107">完全な状態シミュレーターを起動して実行する</span><span class="sxs-lookup"><span data-stu-id="44c0f-107">Invoking and running the full state simulator</span></span>

<span data-ttu-id="44c0f-108">完全な状態シミュレーターはクラスを使用して公開し `QuantumSimulator` ます。</span><span class="sxs-lookup"><span data-stu-id="44c0f-108">You expose the full state simulator via the `QuantumSimulator` class.</span></span> <span data-ttu-id="44c0f-109">詳細については、「 [ Q# プログラムを実行する方法](xref:microsoft.quantum.guide.host-programs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44c0f-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-simulator-from-c"></a><span data-ttu-id="44c0f-110">C からシミュレーターを呼び出す#</span><span class="sxs-lookup"><span data-stu-id="44c0f-110">Invoking the simulator from C#</span></span>

<span data-ttu-id="44c0f-111">クラスのインスタンスを作成し、そのインスタンスを、 `QuantumSimulator` `Run` 追加のパラメーターと共に、クォンタム操作のメソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="44c0f-111">Create an instance of the `QuantumSimulator` class and then pass it to the `Run` method of a quantum operation, along with any additional parameters.</span></span>
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

<span data-ttu-id="44c0f-112">クラスはインターフェイスを実装しているため `QuantumSimulator` <xref:System.IDisposable> 、 `Dispose` シミュレーターのインスタンスが不要になった場合は、メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="44c0f-112">Because the `QuantumSimulator` class implements the <xref:System.IDisposable> interface, you must call the `Dispose` method once you do not need the instance of the simulator anymore.</span></span> <span data-ttu-id="44c0f-113">これを行う最善の方法は、メソッド [を自動的に呼び出すステートメントで](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) 、シミュレーターの宣言と操作をラップすることです `Dispose` 。</span><span class="sxs-lookup"><span data-stu-id="44c0f-113">The best way to do this is to wrap the simulator declaration and operations within a [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) statement, which automatically calls the `Dispose` method.</span></span>

### <a name="invoking-the-simulator-from-python"></a><span data-ttu-id="44c0f-114">Python からシミュレーターを呼び出す</span><span class="sxs-lookup"><span data-stu-id="44c0f-114">Invoking the simulator from Python</span></span>

<span data-ttu-id="44c0f-115">インポートされた操作で、Python ライブラリの [シミュレート ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) メソッドを使用し Q# Q# ます。</span><span class="sxs-lookup"><span data-stu-id="44c0f-115">Use the [simulate()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Q# Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a><span data-ttu-id="44c0f-116">コマンドラインからシミュレーターを呼び出す</span><span class="sxs-lookup"><span data-stu-id="44c0f-116">Invoking the simulator from the command line</span></span>

<span data-ttu-id="44c0f-117">コマンドラインからプログラムを実行すると、 Q# 完全な状態シミュレーターが既定のターゲットコンピューターになります。</span><span class="sxs-lookup"><span data-stu-id="44c0f-117">When running a Q# program from the command line, the full state simulator is the default target machine.</span></span> <span data-ttu-id="44c0f-118">必要に応じて、 **--シミュレーター** (または **-s** ショートカット) パラメーターを使用して、目的のターゲットコンピューターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="44c0f-118">Optionally, you can use the **--simulator** (or **-s** shortcut) parameter to specify the desired target machine.</span></span> <span data-ttu-id="44c0f-119">次のコマンドはいずれも、完全な状態シミュレーターを使用してプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="44c0f-119">Both of the following commands run a program using the full state simulator.</span></span> 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a><span data-ttu-id="44c0f-120">Juptyer Notebook からシミュレーターを呼び出す</span><span class="sxs-lookup"><span data-stu-id="44c0f-120">Invoking the simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="44c0f-121">この Q# 操作を実行するには、I マジックコマンド [% シミュレート](xref:microsoft.quantum.iqsharp.magic-ref.simulate) を使用し Q# ます。</span><span class="sxs-lookup"><span data-stu-id="44c0f-121">Use the IQ# magic command [%simulate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a><span data-ttu-id="44c0f-122">シミュレーターのシード処理</span><span class="sxs-lookup"><span data-stu-id="44c0f-122">Seeding the simulator</span></span>

<span data-ttu-id="44c0f-123">既定では、完全な状態シミュレーターはランダムな数値ジェネレーターを使用して、クォンタムのランダム性をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="44c0f-123">By default, the full state simulator uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="44c0f-124">テスト目的では、決定的な結果が得られる場合があります。</span><span class="sxs-lookup"><span data-stu-id="44c0f-124">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="44c0f-125">C# プログラムでは、パラメーターを使用してコンストラクターに乱数ジェネレーターのシードを指定することで、これを実現でき `QuantumSimulator` `randomNumberGeneratorSeed` ます。</span><span class="sxs-lookup"><span data-stu-id="44c0f-125">In a C# program, you can accomplish this by providing a seed for the random number generator in the `QuantumSimulator` constructor via the `randomNumberGeneratorSeed` parameter.</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a><span data-ttu-id="44c0f-126">構成 (スレッドを)</span><span class="sxs-lookup"><span data-stu-id="44c0f-126">Configuring threads</span></span>

<span data-ttu-id="44c0f-127">完全な状態シミュレーターでは、 [OpenMP](http://www.openmp.org/) を使用して、必要な線形代数を並列化します。</span><span class="sxs-lookup"><span data-stu-id="44c0f-127">The full state simulator uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="44c0f-128">既定では、OpenMP は使用可能なすべてのハードウェアスレッドを使用します。これは、必要な調整によって実際の作業が dwarfs されるため、多くの場合、qubits の数が少ないプログラムは低速で動作することを意味します。</span><span class="sxs-lookup"><span data-stu-id="44c0f-128">By default, OpenMP uses all available hardware threads, which means that programs with small numbers of qubits often runs slowly because the coordination that is required dwarfs the actual work.</span></span> <span data-ttu-id="44c0f-129">この問題を解決するには、環境変数 `OMP_NUM_THREADS` を小さい数値に設定します。</span><span class="sxs-lookup"><span data-stu-id="44c0f-129">You can fix this by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="44c0f-130">経験則として、1つのスレッドを最大4つの qubits に構成してから、qubits ごとに1つのスレッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="44c0f-130">As a rule of thumb, configure one thread for up to four qubits, and then one additional thread per qubit.</span></span> <span data-ttu-id="44c0f-131">アルゴリズムによっては、変数の調整が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="44c0f-131">You might need to adjust the variable depending on your algorithm.</span></span>

## <a name="see-also"></a><span data-ttu-id="44c0f-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="44c0f-132">See also</span></span>

- [<span data-ttu-id="44c0f-133">量子リソース推定器</span><span class="sxs-lookup"><span data-stu-id="44c0f-133">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="44c0f-134">量子 Toffoli シミュレーター</span><span class="sxs-lookup"><span data-stu-id="44c0f-134">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="44c0f-135">クォンタムトレースシミュレーター</span><span class="sxs-lookup"><span data-stu-id="44c0f-135">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)