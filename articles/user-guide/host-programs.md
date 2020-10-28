---
title: 'プログラムを実行する方法 :::no-loc(Q#):::'
description: 'プログラムを実行するさまざまな方法の概要を説明し :::no-loc(Q#)::: ます。 :::no-loc(Q#):::Python または .net 言語のコマンドプロンプト、jupyter notebook、およびクラシックホストプログラム。'
author: gillenhaalb
ms.author: a-gibec
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: f1a4ef0616a8a3f1548b7a7207cf8cbb9dcc7260
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691693"
---
# <a name="ways-to-run-a-no-locq-program"></a><span data-ttu-id="9dfd5-104">プログラムを実行する方法 :::no-loc(Q#):::</span><span class="sxs-lookup"><span data-stu-id="9dfd5-104">Ways to run a :::no-loc(Q#)::: program</span></span>

<span data-ttu-id="9dfd5-105">Quantum Development Kit の最大の強みの1つは、プラットフォームと開発環境全体での柔軟性です。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-105">One of the Quantum Development Kit's greatest strengths is its flexibility across platforms and development environments.</span></span>
<span data-ttu-id="9dfd5-106">ただし、これは、新しい :::no-loc(Q#)::: ユーザーが、 [インストールガイド](xref:microsoft.quantum.install)に記載されている多くのオプションによって混乱を招き、圧倒される可能性があることも意味します。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-106">However, this also means that new :::no-loc(Q#)::: users may find themselves confused or overwhelmed by the numerous options found in the [install guide](xref:microsoft.quantum.install).</span></span>
<span data-ttu-id="9dfd5-107">このページでは、プログラムの実行時の動作につい :::no-loc(Q#)::: て説明し、ユーザーが実行できるさまざまな方法を比較します。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-107">On this page, we explain what happens when a :::no-loc(Q#)::: program is run, and compare the different ways in which users can do so.</span></span>

<span data-ttu-id="9dfd5-108">主な違いは、を :::no-loc(Q#)::: 実行できることです。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-108">A primary distinction is that :::no-loc(Q#)::: can be run:</span></span>
- <span data-ttu-id="9dfd5-109">スタンドアロンアプリケーションとして、 :::no-loc(Q#)::: は関連する唯一の言語であり、プログラムは直接呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-109">as a standalone application, where :::no-loc(Q#)::: is the only language involved and the program is invoked directly.</span></span> <span data-ttu-id="9dfd5-110">このカテゴリには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-110">Two methods actually fall in this category:</span></span>
  - <span data-ttu-id="9dfd5-111">コマンドラインインターフェイス</span><span class="sxs-lookup"><span data-stu-id="9dfd5-111">the command-line interface</span></span>
  - <span data-ttu-id="9dfd5-112">:::no-loc(Q#)::: Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="9dfd5-112">:::no-loc(Q#)::: Jupyter Notebooks</span></span>
- <span data-ttu-id="9dfd5-113">Python または .NET 言語 (C#、F # など) で記述された追加の *ホストプログラム* を使用して、プログラムを呼び出し、返された結果をさらに処理できます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-113">with an additional *host program* , written in Python or a .NET language (for example, C# or F#), which then invokes the program and can further process returned results.</span></span>

<span data-ttu-id="9dfd5-114">これらのプロセスとその違いについて理解を深めるために、単純なプログラムを考えて、 :::no-loc(Q#)::: 実行する方法を比較します。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-114">To best understand these processes and their differences, we consider a simple :::no-loc(Q#)::: program and compare the ways it can be run.</span></span>

## <a name="basic-no-locq-program"></a><span data-ttu-id="9dfd5-115">基本 :::no-loc(Q#)::: プログラム</span><span class="sxs-lookup"><span data-stu-id="9dfd5-115">Basic :::no-loc(Q#)::: program</span></span>

<span data-ttu-id="9dfd5-116">基本的な量子プログラムは、法則の状態が $ \ket $ および $ \ket $ の qubit を準備し、それを測定し、結果を返すことで構成される場合があり {0} {1} ます。これは、これら2つの状態のうち、確率が等しい場合に、ランダムに発生します。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-116">A basic quantum program might consist of preparing a qubit in an equal superposition of states $\ket{0}$ and $\ket{1}$, measuring it, and returning the result, which will be randomly either one of these two states with equal probability.</span></span>
<span data-ttu-id="9dfd5-117">実際には、このプロセスは、クォンタムの [乱数ジェネレーター](xref:microsoft.quantum.quickstarts.qrng) のクイックスタートの中核になっています。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-117">Indeed, this process is at the core of the [quantum random number generator](xref:microsoft.quantum.quickstarts.qrng) quickstart.</span></span>

<span data-ttu-id="9dfd5-118">では :::no-loc(Q#)::: 、これは次のコードによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-118">In :::no-loc(Q#):::, this would be performed by the following code:</span></span>

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

<span data-ttu-id="9dfd5-119">ただし、このコードだけをで実行することはできません :::no-loc(Q#)::: 。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-119">However, this code alone can't be run by :::no-loc(Q#):::.</span></span>
<span data-ttu-id="9dfd5-120">そのためには、操作の本体を構成する必要があります。この [操作](xref:microsoft.quantum.guide.basics#q-operations-and-functions)は、直接または別の操作によって---呼び出されたときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-120">For that, it needs to make up the body of an [operation](xref:microsoft.quantum.guide.basics#q-operations-and-functions), which is then run when called---either directly or by another operation.</span></span> <span data-ttu-id="9dfd5-121">そのため、次の形式の操作を記述できます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-121">Hence, you can write an operation of the following form:</span></span>
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
<span data-ttu-id="9dfd5-122">`MeasureSuperposition`入力を受け取らず、 [Result](xref:microsoft.quantum.guide.types)型の値を返す操作を定義しました。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-122">You have defined an operation, `MeasureSuperposition`, which takes no inputs and returns a value of type [Result](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="9dfd5-123">このページの例は操作のみで構成 :::no-loc(Q#)::: *operations* されていますが、ここで説明するすべての概念は、関数にも同様に関係 :::no-loc(Q#)::: *functions* します。そのため、これらのすべての概念を *呼び出し* が許容できるものとして参照します。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-123">While the examples on this page only consist of :::no-loc(Q#)::: *operations* , all of the concepts we will discuss pertain equally to :::no-loc(Q#)::: *functions* , and therefore we refer to them collectively as *callables* .</span></span> <span data-ttu-id="9dfd5-124">これらの違いについては、 [ :::no-loc(Q#)::: 「基本: 操作と関数](xref:microsoft.quantum.guide.basics#q-operations-and-functions)」で説明されています。これらの定義の詳細については、「[操作と関数](xref:microsoft.quantum.guide.operationsfunctions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-124">Their differences are discussed at [:::no-loc(Q#)::: basics: operations and functions](xref:microsoft.quantum.guide.basics#q-operations-and-functions), and more details on defining them can be found at [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

### <a name="callable-defined-in-a-no-locq-file"></a><span data-ttu-id="9dfd5-125">ファイルで定義された呼び出し可能 :::no-loc(Q#):::</span><span class="sxs-lookup"><span data-stu-id="9dfd5-125">Callable defined in a :::no-loc(Q#)::: file</span></span>

<span data-ttu-id="9dfd5-126">呼び出し可能なは、によって呼び出され、実行され :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-126">The callable is precisely what's called and run by :::no-loc(Q#):::.</span></span>
<span data-ttu-id="9dfd5-127">ただし、完全なファイルを構成するには、さらにいくつかの追加機能が必要です `*.qs` :::no-loc(Q#)::: 。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-127">However, it requires a few more additions to comprise a full `*.qs` :::no-loc(Q#)::: file.</span></span>

<span data-ttu-id="9dfd5-128">すべての :::no-loc(Q#)::: 型と呼び出し可能 (定義したものと言語に固有の型の両方) は、 *名前空間* 内で定義されます。これらの名前は、参照可能な完全な名前を提供します。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-128">All :::no-loc(Q#)::: types and callables (both those you define and those intrinsic to the language) are defined within *namespaces* , which provide each a full name that can then be referenced.</span></span>

<span data-ttu-id="9dfd5-129">たとえば、およびの [`H`](xref:Microsoft.Quantum.Intrinsic.H) 各 [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) 操作は、 [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) 名前空間と名前空間 ( [ :::no-loc(Q#)::: 標準ライブラリ](xref:microsoft.quantum.qsharplibintro)の一部) にあります。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-129">For example, the [`H`](xref:Microsoft.Quantum.Intrinsic.H) and [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) operations are found in the [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) and [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) namespaces (part of the [:::no-loc(Q#)::: Standard Libraries](xref:microsoft.quantum.qsharplibintro)).</span></span>
<span data-ttu-id="9dfd5-130">そのため、常に *完全な* 名前を使用してを呼び出すことができます `Microsoft.Quantum.Intrinsic.H(<qubit>)` が、 `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` 常にこの操作を実行すると、コードが乱雑になることがあります。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-130">As such, they can always be called via their *full* names, `Microsoft.Quantum.Intrinsic.H(<qubit>)` and `Microsoft.Quantum.Measurement.MResetZ(<qubit>)`, but always doing this would lead to very cluttered code.</span></span>

<span data-ttu-id="9dfd5-131">ステートメントを `open` 使用すると、上記の操作本体で行ったように、より簡潔な短縮形で呼び出し可能なを参照できます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-131">Instead, `open` statements allow callables to be referenced with more concise shorthand, as we've done in the operation body above.</span></span>
<span data-ttu-id="9dfd5-132">:::no-loc(Q#):::このため、操作を含む完全なファイルは、独自の名前空間を定義し、操作が使用する呼び出しの名前空間を開いて、次の操作を行うことで構成されます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-132">The full :::no-loc(Q#)::: file containing our operation would therefore consist of defining our own namespace, opening the namespaces for those callables our operation uses, and then our operation:</span></span>

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="9dfd5-133">名前空間は、開いたときに *別名* を付けることもできます。これは、2つの名前空間の呼び出し可能な名前または型名が競合する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-133">Namespaces can also be *aliased* when opened, which can be helpful if callable/type names in two namespaces conflict.</span></span>
> <span data-ttu-id="9dfd5-134">たとえば、代わりにを使用してから、を使用してを呼び出すこともでき `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` `H` `NamespaceWithH.H(<qubit>)` ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-134">For example, we could instead use `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` above, and then call `H` via `NamespaceWithH.H(<qubit>)`.</span></span>

> [!NOTE]
> <span data-ttu-id="9dfd5-135">すべての例外の1つとして、 [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) 常に自動的に開かれる名前空間があります。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-135">One exception to all of this is the [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) namespace, which is always automatically opened.</span></span>
> <span data-ttu-id="9dfd5-136">そのため、のような呼び出し可能なは、 [`Length`](xref:Microsoft.Quantum.Core.Length) 常に直接使用できます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-136">Therefore, callables like [`Length`](xref:Microsoft.Quantum.Core.Length) can always be used directly.</span></span>

### <a name="running-on-target-machines"></a><span data-ttu-id="9dfd5-137">ターゲットコンピューターでの実行</span><span class="sxs-lookup"><span data-stu-id="9dfd5-137">Running on target machines</span></span>

<span data-ttu-id="9dfd5-138">これで、プログラムの一般的な実行モデルが明確になりました :::no-loc(Q#)::: 。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-138">Now the general run model of a :::no-loc(Q#)::: program becomes clear.</span></span>

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt=":::no-loc(Q#)::: program execution diagram" width="400">

<span data-ttu-id="9dfd5-139">最初に、実行される特定の呼び出し可能なが、同じ名前空間で定義されている他の呼び出し可能な型と型にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-139">Firstly, the specific callable to be run has access to any other callables and types defined in the same namespace.</span></span>
<span data-ttu-id="9dfd5-140">また、 [ :::no-loc(Q#)::: ライブラリ](xref:microsoft.quantum.libraries)からアクセスすることもできますが、フルネームを使用するか、上記のステートメントを使用して参照する必要があり `open` ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-140">It also access those from any of the [:::no-loc(Q#)::: libraries](xref:microsoft.quantum.libraries), but those must be referenced either via their full name, or through the use of `open` statements described above.</span></span>

<span data-ttu-id="9dfd5-141">その後、呼び出し可能なものが *[ターゲットコンピューター](xref:microsoft.quantum.machines)* 上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-141">The callable itself is then run on a *[target machine](xref:microsoft.quantum.machines)* .</span></span>
<span data-ttu-id="9dfd5-142">このようなターゲットマシンは、実際の quantum ハードウェア、または QDK の一部として提供されている複数のシミュレーターにすることができます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-142">Such target machines can be actual quantum hardware or the multiple simulators available as part of the QDK.</span></span>
<span data-ttu-id="9dfd5-143">ここでの目的のために、最も役に立つターゲットコンピューターは、 [フルステートシミュレーター](xref:microsoft.quantum.machines.full-state-simulator)のインスタンスです。これは `QuantumSimulator` 、ノイズフリーのクォンタムコンピューターで実行されているかのようにプログラムの動作を計算します。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-143">For our purposes here, the most useful target machine is an instance of the [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator`, which calculates the program's behavior as if it were being run on a noise-free quantum computer.</span></span>

<span data-ttu-id="9dfd5-144">ここまでは、特定の :::no-loc(Q#)::: 呼び出し可能が実行されたときの動作について説明しました。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-144">So far, we've described what happens when a specific :::no-loc(Q#)::: callable is being run.</span></span>
<span data-ttu-id="9dfd5-145">がスタンドアロンアプリケーションとホストプログラムのどちらで使用されているかにかかわらず :::no-loc(Q#)::: 、この一般的なプロセスは同じ---であるため、QDK の柔軟性があります。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-145">Regardless of whether :::no-loc(Q#)::: is used in a standalone application or with a host program, this general process is more or less the same---hence the QDK's flexibility.</span></span>
<span data-ttu-id="9dfd5-146">クォンタム開発キットを呼び出す方法の違いにより、呼び出し可能な呼び出しの *how* 実行方法 :::no-loc(Q#)::: と結果が返される方法が異なります。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-146">The differences between the ways of calling into the Quantum Development Kit therefore reveal themselves in *how* that :::no-loc(Q#)::: callable is called to be run, and in what manner any results are returned.</span></span>
<span data-ttu-id="9dfd5-147">具体的には、次のような違いがあります。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-147">More specifically, the differences revolve around:</span></span>

- <span data-ttu-id="9dfd5-148">:::no-loc(Q#):::実行する呼び出し元を示す</span><span class="sxs-lookup"><span data-stu-id="9dfd5-148">Indicating which :::no-loc(Q#)::: callable is to be run</span></span>
- <span data-ttu-id="9dfd5-149">可能性のある呼び出し可能な引数の提供方法</span><span class="sxs-lookup"><span data-stu-id="9dfd5-149">How potential callable arguments are provided</span></span>
- <span data-ttu-id="9dfd5-150">実行するターゲットコンピューターの指定</span><span class="sxs-lookup"><span data-stu-id="9dfd5-150">Specifying the target machine on which to run it</span></span>
- <span data-ttu-id="9dfd5-151">結果が返される方法</span><span class="sxs-lookup"><span data-stu-id="9dfd5-151">How any results are returned</span></span>

<span data-ttu-id="9dfd5-152">まず、コマンドプロンプトからスタンドアロンアプリケーションを使用してこれがどのように行われるかについて説明 :::no-loc(Q#)::: し、次に Python および C# ホストプログラムの使用に進みます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-152">First, we discuss how this is done with the :::no-loc(Q#)::: standalone application from the command prompt, and then proceed to using Python and C# host programs.</span></span>
<span data-ttu-id="9dfd5-153">Jupyter Notebook のスタンドアロンアプリケーションは、 :::no-loc(Q#)::: 最初の3つとは異なり、プライマリ機能はローカルファイルを中心にしていません :::no-loc(Q#)::: 。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-153">We reserve the standalone application of :::no-loc(Q#)::: Jupyter Notebooks for last, because unlike the first three, it's primary functionality does not center around a local :::no-loc(Q#)::: file.</span></span>

> [!NOTE]
> <span data-ttu-id="9dfd5-154">これらの例では説明しませんが、run メソッド間の1つの共通点として、プログラム内から :::no-loc(Q#)::: (またはなどによって) 出力されるすべてのメッセージは、 [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) 通常、それぞれのコンソールに出力されます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-154">Although we don't illustrate it in these examples, one commonality between the run methods is that any messages printed from inside the :::no-loc(Q#)::: program (by way of [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) or [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine), for example) will typically always be printed to the respective console.</span></span>

## <a name="no-locq-from-the-command-prompt"></a><span data-ttu-id="9dfd5-155">:::no-loc(Q#)::: コマンドプロンプトから</span><span class="sxs-lookup"><span data-stu-id="9dfd5-155">:::no-loc(Q#)::: from the command prompt</span></span>
<span data-ttu-id="9dfd5-156">プログラムの記述を開始する最も簡単な方法の1つ :::no-loc(Q#)::: は、個別のファイルと2番目の言語をまったく気にすることがないようにすることです。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-156">One of the easiest ways to get started writing :::no-loc(Q#)::: programs is to avoid worrying about separate files and a second language altogether.</span></span>
<span data-ttu-id="9dfd5-157">QDK 拡張機能を使用して Visual Studio Code または Visual Studio を使用すると、 :::no-loc(Q#)::: 1 つのファイルから呼び出し可能なものだけを実行するシームレスな作業フローを実現でき :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-157">Using Visual Studio Code or Visual Studio with the QDK extension allows for a seamless work flow in which we run :::no-loc(Q#)::: callables from only a single :::no-loc(Q#)::: file.</span></span>

<span data-ttu-id="9dfd5-158">この場合、最終的には、次のように入力してプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-158">For this, we will ultimately run the program by entering</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="9dfd5-159">」と入力します。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-159">at the command prompt.</span></span>
<span data-ttu-id="9dfd5-160">最も単純なワークフローは、ターミナルのディレクトリの場所がファイルと同じ場合です :::no-loc(Q#)::: :::no-loc(Q#)::: 。たとえば、VS Code の統合ターミナルを使用して、ファイルの編集と共に簡単に処理できます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-160">The simplest workflow is when the terminal's directory location is the same as the :::no-loc(Q#)::: file, which can be easily handled alongside :::no-loc(Q#)::: file editing by using the integrated terminal in VS Code, for example.</span></span>
<span data-ttu-id="9dfd5-161">ただし、 [ `dotnet run` コマンド](https://docs.microsoft.com/dotnet/core/tools/dotnet-run)は多くのオプションを受け入れます。プログラムは、 `--project <PATH>` ファイルの場所を指定するだけで別の場所から実行することもできます :::no-loc(Q#)::: 。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-161">However, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepts numerous options, and the program can also be run from a different location by simply providing `--project <PATH>` with the location of the :::no-loc(Q#)::: file.</span></span>


### <a name="add-entry-point-to-no-locq-file"></a><span data-ttu-id="9dfd5-162">ファイルへのエントリポイントの追加 :::no-loc(Q#):::</span><span class="sxs-lookup"><span data-stu-id="9dfd5-162">Add entry point to :::no-loc(Q#)::: file</span></span>

<span data-ttu-id="9dfd5-163">ほとんど :::no-loc(Q#)::: のファイルには複数の呼び出し可能が含まれているため、当然ながら、コマンドを指定したときに実行さ *れる呼び出し元* をコンパイラに知らせる必要があり `dotnet run` ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-163">Most :::no-loc(Q#)::: files will contain more than one callable, so naturally we need to let the compiler know *which* callable to run when we provide the `dotnet run` command.</span></span>
<span data-ttu-id="9dfd5-164">これは、ファイル自体を単純に変更することで行われ :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-164">This is done with a simple change to the :::no-loc(Q#)::: file itself:</span></span> 
    - <span data-ttu-id="9dfd5-165">呼び出し可能なの直前に行を追加 `@EntryPoint()` します。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-165">add a line with `@EntryPoint()` directly preceding the callable.</span></span>

<span data-ttu-id="9dfd5-166">そのため、上記のファイルは</span><span class="sxs-lookup"><span data-stu-id="9dfd5-166">Our file from above would therefore become</span></span>
```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    @EntryPoint()
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

<span data-ttu-id="9dfd5-167">これで、コマンドプロンプトからを呼び出すと、が `dotnet run` `MeasureSuperposition` 実行され、返された値がターミナルに直接出力されます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-167">Now, a call of `dotnet run` from the command prompt leads to `MeasureSuperposition` being run, and the returned value is then printed directly to the terminal.</span></span>
<span data-ttu-id="9dfd5-168">そのため、またはのどちらかが表示され `One` `Zero` ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-168">So, you will see either `One` or `Zero` printed.</span></span> 

<span data-ttu-id="9dfd5-169">より多くの呼び出し可能を定義しているかどうかは関係ありません `MeasureSuperposition` 。実行されるのはのみです。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-169">Note that it doesn't matter if you have more callables defined below it, only `MeasureSuperposition` will be run.</span></span>
<span data-ttu-id="9dfd5-170">また、呼び出し元が宣言の前に [ドキュメントコメント](xref:microsoft.quantum.guide.filestructure#documentation-comments) を含んでいる場合は問題ありません `@EntryPoint()` 。属性は、単純にその上に配置できます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-170">Additionally, it's no problem if your callable includes [documentation comments](xref:microsoft.quantum.guide.filestructure#documentation-comments) before its declaration, the `@EntryPoint()` attribute can be simply placed above them.</span></span>

### <a name="callable-arguments"></a><span data-ttu-id="9dfd5-171">呼び出し可能引数</span><span class="sxs-lookup"><span data-stu-id="9dfd5-171">Callable arguments</span></span>

<span data-ttu-id="9dfd5-172">ここまでは、入力を必要としない操作についてのみ検討しました。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-172">So far, we've only considered an operation that takes no inputs.</span></span>
<span data-ttu-id="9dfd5-173">同様の操作を実行するとしますが、複数の qubits---、引数として指定されている数を示しています。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-173">Suppose we wanted to perform a similar operation, but on multiple qubits---the number of which is provided as an argument.</span></span>
<span data-ttu-id="9dfd5-174">このような操作は、</span><span class="sxs-lookup"><span data-stu-id="9dfd5-174">Such an operation could be written as</span></span>
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
<span data-ttu-id="9dfd5-175">返される値は、測定結果の配列です。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-175">where the returned value is an array of the measurement results.</span></span>
<span data-ttu-id="9dfd5-176">[`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach)と [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) は名前空間にあり [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) 、 `open` それぞれに対して追加のステートメントが必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-176">Note that [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) and [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) are in the [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) and [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) namespaces, requiring additional `open` statements for each.</span></span>

<span data-ttu-id="9dfd5-177">`@EntryPoint()`この新しい操作の前に属性を移動した場合 (ファイル内にはそのような行が1つだけ存在する場合があることに注意してください)、を使用して実行しようとすると、 `dotnet run` 必要な追加のコマンドラインオプションを示すエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-177">If we move the `@EntryPoint()` attribute to precede this new operation (note there can only be one such line in a file), attempting to run it with simply `dotnet run` results in an error message which indicates what additional command-line options are required, and how to express them.</span></span>

<span data-ttu-id="9dfd5-178">コマンドラインの一般的な形式は実際にはであり、呼び出し可能な引数がそこに用意されてい `dotnet run [options]` ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-178">The general format for the command line is actually `dotnet run [options]`, and callable arguments are provided there.</span></span>
<span data-ttu-id="9dfd5-179">この場合、引数 `n` が不足しているため、オプションを指定する必要があることが示されて `-n <n>` います。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-179">In this case, the argument `n` is missing, and it shows that we need to provide the option `-n <n>`.</span></span> <span data-ttu-id="9dfd5-180">Qubits でを実行するには、次のように `MeasureSuperpositionArray` `n=4` します。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-180">To run `MeasureSuperpositionArray` for `n=4` qubits, we therefore use</span></span>

```dotnetcli
dotnet run -n 4
```

<span data-ttu-id="9dfd5-181">のような出力を生成する</span><span class="sxs-lookup"><span data-stu-id="9dfd5-181">yielding an output similar to</span></span>

```output
[Zero,One,One,One]
```

<span data-ttu-id="9dfd5-182">これは、複数の引数にまで拡張されています。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-182">This of course extends to multiple arguments.</span></span>

> [!NOTE]
> <span data-ttu-id="9dfd5-183">で定義されている引数名 `camelCase` は、入力として受け入れられるように、コンパイラによって若干変更されてい :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-183">Argument names defined in `camelCase` are slightly altered by the compiler to be accepted as :::no-loc(Q#)::: inputs.</span></span> <span data-ttu-id="9dfd5-184">たとえば、の代わりに上記の名前を使用した場合、この入力はでは `n` `numQubits` なく、コマンドラインで指定され `--num-qubits 4` `-n 4` ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-184">For example, if instead of `n`, we used the name `numQubits` above, then this input would be provided in the command line via `--num-qubits 4` instead of `-n 4`.</span></span>

<span data-ttu-id="9dfd5-185">このエラーメッセージには、ターゲットコンピューターの変更方法など、使用できるその他のオプションも表示されます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-185">The error message also provides other options which can be used, including how to change the target machine.</span></span>

### <a name="different-target-machines"></a><span data-ttu-id="9dfd5-186">異なるターゲットコンピューター</span><span class="sxs-lookup"><span data-stu-id="9dfd5-186">Different target machines</span></span>

<span data-ttu-id="9dfd5-187">これまでの操作からの出力が実際の qubits でのアクションの予想される結果であるため、コマンドラインからの既定のターゲットコンピューターが完全な状態のクォンタムシミュレーターであることは明らかです `QuantumSimulator` 。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-187">As the outputs from our operations thus far have been the expected results of their action on real qubits, it's clear that the default target machine from the command line is the full-state quantum simulator, `QuantumSimulator`.</span></span>
<span data-ttu-id="9dfd5-188">ただし、オプション `--simulator` (または短縮形) を使用して、特定のターゲットコンピューターで実行するように指定することもでき `-s` ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-188">However, we can instruct callables to be run on a specific target machine with the option `--simulator` (or the shorthand `-s`).</span></span>

<span data-ttu-id="9dfd5-189">たとえば、次のように実行でき [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-189">For example, we could run it on [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator):</span></span>

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

<span data-ttu-id="9dfd5-190">印刷出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-190">The printed output is then</span></span>

```output
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

<span data-ttu-id="9dfd5-191">これらのメトリックが示す内容の詳細については、「 [リソースの推定機能: 報告](xref:microsoft.quantum.machines.resources-estimator#metrics-reported)されるメトリック」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-191">For details on what these metrics indicate, see [Resource estimator: metrics reported](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span></span>

### <a name="command-line-run-summary"></a><span data-ttu-id="9dfd5-192">コマンドラインの実行の概要</span><span class="sxs-lookup"><span data-stu-id="9dfd5-192">Command line run summary</span></span>
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt=":::no-loc(Q#)::: program from command line" width="700">

### <a name="non-no-locq-dotnet-run-options"></a><span data-ttu-id="9dfd5-193">オプション以外 :::no-loc(Q#)::: `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="9dfd5-193">Non-:::no-loc(Q#)::: `dotnet run` options</span></span>

<span data-ttu-id="9dfd5-194">前述のようにオプションを使用 `--project` すると、 [ `dotnet run` コマンド](https://docs.microsoft.com/dotnet/core/tools/dotnet-run)は呼び出し可能な引数とは無関係のオプションも受け入れ :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-194">As we briefly mentioned above with the `--project` option, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) also accepts options unrelated to the :::no-loc(Q#)::: callable arguments.</span></span>
<span data-ttu-id="9dfd5-195">両方の種類のオプションを指定する場合は、固有のオプションを指定し、その後に区切り記号を指定してから、固有のオプションを `dotnet` 指定する必要があり `--` :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-195">If providing both kinds of options, the `dotnet`-specific options must be provided first, followed by a delimeter `--`, and then the :::no-loc(Q#):::-specific options.</span></span>
<span data-ttu-id="9dfd5-196">たとえば、上記の操作に対して、数値 qubits と共にパスを指定すると、を使用して実行さ `dotnet run --project <PATH> -- -n <n>` れます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-196">For example, specifying a path along with a number qubits for the operation above would be run via `dotnet run --project <PATH> -- -n <n>`.</span></span>

## <a name="no-locq-with-host-programs"></a><span data-ttu-id="9dfd5-197">:::no-loc(Q#)::: ホストプログラムを使用する</span><span class="sxs-lookup"><span data-stu-id="9dfd5-197">:::no-loc(Q#)::: with host programs</span></span>

<span data-ttu-id="9dfd5-198">ファイルを :::no-loc(Q#)::: 手に置いて、コマンドプロンプトから直接操作または関数を呼び出す代わりに、別のクラシック言語で *ホストプログラム* を使用する方法があります。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-198">With our :::no-loc(Q#)::: file in hand, an alternative to calling an operation or function directly from the command prompt is to use a *host program* in another classical language.</span></span> <span data-ttu-id="9dfd5-199">具体的には、Python または C# や F # などの .NET 言語で行うことができます (簡潔にするために、ここでは C# についてのみ説明します)。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-199">Specifically, this can be done with either Python or a .NET language such as C# or F# (for the sake of brevity we will only detail C# here).</span></span>
<span data-ttu-id="9dfd5-200">相互運用性を実現するにはもう少しセットアップが必要ですが、これらの詳細については、 [インストールガイド](xref:microsoft.quantum.install)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-200">A little more setup is required to enable the interoperability, but those details can be found in the [install guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="9dfd5-201">簡単に言うと、この状況で `*.py` は、 `*.cs` ファイルと同じ場所にホストプログラムファイル (やなど) が含まれるようになりました :::no-loc(Q#)::: 。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-201">In a nutshell, the situation now includes a host program file (for example, `*.py` or `*.cs`) in the same location as our :::no-loc(Q#)::: file.</span></span>
<span data-ttu-id="9dfd5-202">これで実行される *ホスト* プログラムになり、実行中に、ファイルから特定の操作と関数を呼び出すことができ :::no-loc(Q#)::: :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-202">It's now the *host* program that gets run, and while it is running, it can call specific :::no-loc(Q#)::: operations and functions from the :::no-loc(Q#)::: file.</span></span>
<span data-ttu-id="9dfd5-203">相互運用性の中核となるのは、コンパイラを使用して、 :::no-loc(Q#)::: ファイルの内容を :::no-loc(Q#)::: ホストプログラムからアクセスできるようにし、それらを呼び出すことができるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-203">The core of the interoperability is based on the :::no-loc(Q#)::: compiler making the contents of the :::no-loc(Q#)::: file accessible to the host program so that they can be called.</span></span>

<span data-ttu-id="9dfd5-204">ホストプログラムを使用する主な利点の1つは、プログラムによって返される古典的なデータを :::no-loc(Q#)::: ホスト言語でさらに処理できることです。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-204">One of the main benefits of using a host program is that the classical data returned by the :::no-loc(Q#)::: program can then be further processed in the host language.</span></span>
<span data-ttu-id="9dfd5-205">これは、いくつかの高度なデータ処理 (で内部で実行できないものなど :::no-loc(Q#)::: ) と、その結果に基づいて他のアクションを呼び出すことができ :::no-loc(Q#)::: ます。また、結果をプロットするのと同じように簡単です :::no-loc(Q#)::: 。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-205">This could consist of some advanced data processing (for example, something that can't be performed internally in :::no-loc(Q#):::), and then calling further :::no-loc(Q#)::: actions based on those results, or something as simple as plotting the :::no-loc(Q#)::: results.</span></span>

<span data-ttu-id="9dfd5-206">一般的なスキームを次に示します。以下では、Python と C# の特定の実装について説明します。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-206">The general scheme is shown here, and we discuss the specific implementations for Python and C# below.</span></span> <span data-ttu-id="9dfd5-207">F # ホストプログラムを使用するサンプルについては、 [.net 相互運用性のサンプル](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-207">A sample using an F# host program can be found at the [.NET interoperability samples](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt=":::no-loc(Q#)::: program from a host program" width="700">

> [!NOTE]
> <span data-ttu-id="9dfd5-208">`@EntryPoint()`アプリケーションに使用される属性は、 :::no-loc(Q#)::: ホストプログラムでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-208">The `@EntryPoint()` attribute used for :::no-loc(Q#)::: applications cannot be used with host programs.</span></span>
> <span data-ttu-id="9dfd5-209">:::no-loc(Q#):::ホストによって呼び出されているファイルにエラーがある場合は、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-209">An error will be raised if it is present in the :::no-loc(Q#)::: file being called by a host.</span></span> 

<span data-ttu-id="9dfd5-210">別のホストプログラムを使用する場合は、ファイルに対する変更は必要ありません `*.qs` :::no-loc(Q#)::: 。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-210">To work with different host programs, there are no changes required to a `*.qs` :::no-loc(Q#)::: file.</span></span>
<span data-ttu-id="9dfd5-211">次のホストプログラムの実装はすべて、同じファイルで動作し :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-211">The following host program implementations all work with the same :::no-loc(Q#)::: file:</span></span>

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // contains H
    open Microsoft.Quantum.Measurement;   // MResetZ
    open Microsoft.Quantum.Canon;         // ApplyToEach
    open Microsoft.Quantum.Arrays;        // ForEach

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }

    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {  
            ApplyToEach(H, qubits); 
            return ForEach(MResetZ, qubits);    
        }
    }
}
```

<span data-ttu-id="9dfd5-212">目的のホスト言語に対応するタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-212">Select the tab corresponding to your host language of interest.</span></span>

### <a name="python"></a>[<span data-ttu-id="9dfd5-213">Python</span><span class="sxs-lookup"><span data-stu-id="9dfd5-213">Python</span></span>](#tab/tabid-python)
<span data-ttu-id="9dfd5-214">Python ホストプログラムは次のように構成されます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-214">A Python host program is constructed as follows:</span></span>
1. <span data-ttu-id="9dfd5-215">モジュールをインポートし `qsharp` ます。これにより、モジュールローダーが相互運用性のために登録され :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-215">Import the `qsharp` module, which registers the module loader for :::no-loc(Q#)::: interoperability.</span></span> 
    <span data-ttu-id="9dfd5-216">これ :::no-loc(Q#)::: により、名前空間を Python モジュールとして表示できるようになります。そこから、"インポート" 呼び出しを実行でき :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-216">This allows :::no-loc(Q#)::: namespaces to appear as Python modules, from which we can "import" :::no-loc(Q#)::: callables.</span></span>
    <span data-ttu-id="9dfd5-217">これは技術的には呼び出し可能なものではなく :::no-loc(Q#)::: 、インポートされる Python スタブであり、それを呼び出すことができることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-217">Note that it is technically not the :::no-loc(Q#)::: callables themselves which are imported, but rather Python stubs which allow calling into them.</span></span>
    <span data-ttu-id="9dfd5-218">これらは Python クラスのオブジェクトとして動作します。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-218">These behave as objects of Python classes.</span></span> <span data-ttu-id="9dfd5-219">これらのオブジェクトに対してメソッドを使用して、プログラムの実行時に操作を送信するターゲットコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-219">We use methods on these objects to specify the target machines that we send the operation to when running the program.</span></span>

2. <span data-ttu-id="9dfd5-220">そのような呼び出しをインポート :::no-loc(Q#)::: します。ここでは、を直接呼び出します。この場合、 `MeasureSuperposition` と--- `MeasureSuperpositionArray` ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-220">Import those :::no-loc(Q#)::: callables which we will directly invoke---in this case, `MeasureSuperposition` and `MeasureSuperpositionArray`.</span></span>
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    <span data-ttu-id="9dfd5-221">モジュールをインポートした場合は、 `qsharp` ライブラリの名前空間から直接 callables 実行可能ファイルをインポートすることもでき :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-221">With the `qsharp` module imported, you can also import callables directly from the :::no-loc(Q#)::: library namespaces.</span></span>

3. <span data-ttu-id="9dfd5-222">その他の Python コードでは、特定のターゲットコンピューターでそれらの呼び出しを呼び出すことができるようになりました。さらに使用するために、その戻り値を変数に代入します (値を返す場合)。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-222">Among any other Python code, you can now call those callables on specific target machines, and assign their returns to variables (if they return a value) for further use.</span></span>

#### <a name="specifying-target-machines"></a><span data-ttu-id="9dfd5-223">ターゲットコンピューターの指定</span><span class="sxs-lookup"><span data-stu-id="9dfd5-223">Specifying target machines</span></span>
<span data-ttu-id="9dfd5-224">特定のターゲットコンピューターで実行される操作の呼び出しは、インポートされたオブジェクトのさまざまな Python メソッドを使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-224">Calling an operation to be run on a specific target machine is done via different Python methods on the imported object.</span></span>
<span data-ttu-id="9dfd5-225">たとえば、は、を使用して `.simulate(<args>)` 操作を実行しますが、ではを使用 `QuantumSimulator` `.estimate_resources(<args>)` `ResourcesEstimator` します。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-225">For example, `.simulate(<args>)`, uses the `QuantumSimulator` to run the operation, whereas `.estimate_resources(<args>)` does so on the `ResourcesEstimator`.</span></span>

#### <a name="passing-inputs-to-q"></a><span data-ttu-id="9dfd5-226">入力を Q に渡す\#</span><span class="sxs-lookup"><span data-stu-id="9dfd5-226">Passing inputs to Q\#</span></span>
<span data-ttu-id="9dfd5-227">呼び出し可能な引数は、キーワード :::no-loc(Q#)::: 引数の形式で指定する必要があります。キーワードは呼び出し可能な定義の引数名です :::no-loc(Q#)::: 。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-227">Arguments for the :::no-loc(Q#)::: callable should be provided in the form of a keyword argument, where the keyword is the argument name in the :::no-loc(Q#)::: callable definition.</span></span>
<span data-ttu-id="9dfd5-228">つまり、は有効ですが、では `MeasureSuperpositionArray.simulate(n=4)` エラーがスローされ `MeasureSuperpositionArray.simulate(4)` ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-228">That is, `MeasureSuperpositionArray.simulate(n=4)` is valid, whereas `MeasureSuperpositionArray.simulate(4)` would throw an error.</span></span>

<span data-ttu-id="9dfd5-229">そのため、Python ホストプログラム</span><span class="sxs-lookup"><span data-stu-id="9dfd5-229">Therefore, the Python host program</span></span> 

```python
import qsharp
from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray

single_qubit_result = MeasureSuperposition.simulate()
single_qubit_resources = MeasureSuperposition.estimate_resources()

multi_qubit_result = MeasureSuperpositionArray.simulate(n=4)
multi_qubit_resources = MeasureSuperpositionArray.estimate_resources(n=4)

print('Single qubit:\n' + str(single_qubit_result))
print(single_qubit_resources)

print('\nMultiple qubits:\n' + str(multi_qubit_result))
print(multi_qubit_resources)
```

<span data-ttu-id="9dfd5-230">次のような結果が出力されます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-230">results in an output like the following:</span></span>

```output
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

#### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="9dfd5-231">:::no-loc(Q#):::他のプロジェクトまたはパッケージからのコードの使用</span><span class="sxs-lookup"><span data-stu-id="9dfd5-231">Using :::no-loc(Q#)::: code from other projects or packages</span></span>

<span data-ttu-id="9dfd5-232">既定では、 `import qsharp` コマンドは、現在のフォルダー内のすべてのファイルを読み込み、 `.qs` その :::no-loc(Q#)::: 操作と関数を Python スクリプト内から使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-232">By default, the `import qsharp` command loads all of the `.qs` files in the current folder and makes their :::no-loc(Q#)::: operations and functions available for use from inside the Python script.</span></span>

<span data-ttu-id="9dfd5-233">別のフォルダーからコードを読み込むには、 :::no-loc(Q#)::: [ `qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects)を使用して、 `.csproj` プロジェクトのファイル (つまり :::no-loc(Q#)::: 、を参照するプロジェクト) への参照を追加し `Microsoft.Quantum.Sdk` ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-233">To load :::no-loc(Q#)::: code from another folder, the [`qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) can be used to add a reference to a `.csproj` file for a :::no-loc(Q#)::: project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span>
<span data-ttu-id="9dfd5-234">このコマンドは `.qs` 、とそのサブフォルダーを含むフォルダー内のすべてのファイルをコンパイル `.csproj` します。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-234">This command will compile any `.qs` files in the folder containing the `.csproj` and its subfolders.</span></span> <span data-ttu-id="9dfd5-235">また、またはから参照されるプロジェクトを通じて参照されるパッケージも、そのファイルで再帰的に読み込まれ `PackageReference` :::no-loc(Q#)::: `ProjectReference` `.csproj` ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-235">It will also recursively load any packages referenced via `PackageReference` or :::no-loc(Q#)::: projects referenced via `ProjectReference` in that `.csproj` file.</span></span>

<span data-ttu-id="9dfd5-236">たとえば、次の Python コードは、現在のフォルダーに対する相対パスを参照して外部プロジェクトをインポートし、その操作の1つを呼び出し :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-236">As an example, the following Python code imports an external project, referencing its path relative to the current folder, and invokes one of its :::no-loc(Q#)::: operations:</span></span>

```python
import qsharp
qsharp.projects.add("../qrng/Qrng.csproj")
from Qrng import SampleQuantumRandomNumberGenerator
print(f"Qrng result: {SampleQuantumRandomNumberGenerator.simulate()}")
```

<span data-ttu-id="9dfd5-237">この結果、次のような出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-237">This results in output like the following:</span></span>

```output
Adding reference to project: ../qrng/Qrng.csproj
Qrng result: 0
```

<span data-ttu-id="9dfd5-238">コードを含む外部パッケージを読み込むに :::no-loc(Q#)::: は、 [ `qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages)を使用します。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-238">To load external packages containing :::no-loc(Q#)::: code, use the [`qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages).</span></span>

<span data-ttu-id="9dfd5-239">現在の :::no-loc(Q#)::: フォルダー内のコードが外部のプロジェクトまたはパッケージに依存している場合は、 `import qsharp` 依存関係がまだ読み込まれていないため、の実行時にエラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-239">If the :::no-loc(Q#)::: code in the current folder depends on external projects or packages, you may see errors when running `import qsharp`, since the dependencies have not yet been loaded.</span></span>
<span data-ttu-id="9dfd5-240">コマンドの実行中に必要な外部パッケージまたはプロジェクトを読み込むには、Python スクリプトが格納されているフォルダーに、を :::no-loc(Q#)::: `import qsharp` 参照するファイルが含まれていることを確認し `.csproj` `Microsoft.Quantum.Sdk` ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-240">To load required external packages or :::no-loc(Q#)::: projects during the `import qsharp` command, ensure that the folder with the Python script contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="9dfd5-241">その中で、 `.csproj` プロパティを `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` に追加し `<PropertyGroup>` ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-241">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="9dfd5-242">これにより :::no-loc(Q#)::: `ProjectReference` `PackageReference` `.csproj` 、コマンドの実行中に、で見つかった項目または項目を再帰的に読み込むように指示され `import qsharp` ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-242">This will instruct I:::no-loc(Q#)::: to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` during the `import qsharp` command.</span></span>

<span data-ttu-id="9dfd5-243">たとえば、 `.csproj` パッケージを自動的に読み込む単純なファイルを次に示し :::no-loc(Q#)::: `Microsoft.Quantum.Chemistry` ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-243">For example, here is a simple `.csproj` file that causes I:::no-loc(Q#)::: to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="9dfd5-244">現在、このカスタム `<IQSharpLoadAutomatically>` プロパティは python ホストで要求されていますが、将来は `.csproj` python スクリプトと同じフォルダーにあるファイルの既定の動作になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-244">Currently this custom `<IQSharpLoadAutomatically>` property is required by Python hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the Python script.</span></span>

> [!NOTE]
> <span data-ttu-id="9dfd5-245">現在 `<QsharpCompile>` 、の設定は `.csproj` Python ホストによって無視され、 `.qs` のフォルダー (サブフォルダーを含む) 内のすべてのファイルが `.csproj` 読み込まれ、コンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-245">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by Python hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="9dfd5-246">設定のサポートは `.csproj` 今後改善される予定です (詳細については、「 [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) 」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-246">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>


### <a name="c"></a>[<span data-ttu-id="9dfd5-247">C#</span><span class="sxs-lookup"><span data-stu-id="9dfd5-247">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="9dfd5-248">C# ホストプログラムには複数のコンポーネントがあり、QDK の一部のコンポーネントと密接に連携しています。たとえば、シミュレーターは、それ自体が C# 上に構築されています。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-248">A C# host program has multiple components, and works very closely with some components of the QDK, such as the simulators, which are themselves built on C#.</span></span>

<span data-ttu-id="9dfd5-249">ここでは、 :::no-loc(Q#)::: ファイルの名前空間から同等の名前付き C# 名前空間を生成することによって、コンパイラが動作し :::no-loc(Q#)::: :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-249">The :::no-loc(Q#)::: compiler works here by generating an equivalently named C# namespace from the :::no-loc(Q#)::: namespace in our :::no-loc(Q#)::: file.</span></span>
<span data-ttu-id="9dfd5-250">さらに、呼び出しが許容される型またはその中に定義された型ごとに、同等の名前付き C# クラスを生成 :::no-loc(Q#)::: します。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-250">It further generates an equivalently named C# class for each of the :::no-loc(Q#)::: callables or types defined therein.</span></span>

<span data-ttu-id="9dfd5-251">まず、ホストプログラムで使用されるすべてのクラスをステートメントで使用できるようにし `using` ます。これは、 `open` ファイル内のステートメントに対しておおよその順序で実行され :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-251">First, we make any classes used in our host program available with `using` statements, which are roughly analagous to the `open` statements in our :::no-loc(Q#)::: file:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (for example, QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the :::no-loc(Q#)::: namespace available
```

<span data-ttu-id="9dfd5-252">次に、C# の名前空間、他のいくつかのビットと部分 (以下の完全なコードブロックを参照) と、必要なすべての古典的なプログラミング (呼び出しを行うための引数の計算など) を宣言し :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-252">Next, we declare our C# namespace, a few other bits and pieces (see the full code block below), and then any classical programming we would like (for example, computing arguments for the :::no-loc(Q#)::: callables).</span></span>
<span data-ttu-id="9dfd5-253">この場合、後者は必要ありませんが、このような使用例については、  [.net 相互運用性のサンプル](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-253">The latter isn't necessary in our case, but an example of such usage can be found at the  [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).</span></span>

#### <a name="target-machines"></a><span data-ttu-id="9dfd5-254">ターゲット コンピューター</span><span class="sxs-lookup"><span data-stu-id="9dfd5-254">Target machines</span></span>

<span data-ttu-id="9dfd5-255">に戻るには :::no-loc(Q#)::: 、操作を実行する対象コンピューターのインスタンスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-255">Getting back to :::no-loc(Q#):::, we must create an instance of whatever target machine we will run our operations on.</span></span>

```csharp
            using var sim = new QuantumSimulator();
```

<span data-ttu-id="9dfd5-256">他のターゲットマシンの使用は、別のターゲットコンピューターをインスタンス化するのと同じように簡単ですが、それを行う方法と戻り値を処理する方法は若干異なります。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-256">Using other target machines is as simple as instantiating a different one, although the manner of doing so and processing the returns can be slightly different.</span></span>
<span data-ttu-id="9dfd5-257">簡潔にするために、ここではについて説明 [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) し、次のものを含め [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator)ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-257">For brevity, we stick to the [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) for now, and include the [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).</span></span>

<span data-ttu-id="9dfd5-258">操作から生成された各 C# クラスには :::no-loc(Q#)::: メソッドがあり `Run` 、その最初の引数はターゲットコンピューターインスタンスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-258">Each C# class generated from the :::no-loc(Q#)::: operations have a `Run` method, the first argument of which must be the target machine instance.</span></span>
<span data-ttu-id="9dfd5-259">そのため、でを実行するには、を `MeasureSuperposition` `QuantumSimulator` 使用 `MeasureSuperposition.Run(sim)` します。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-259">So, to run `MeasureSuperposition` on the `QuantumSimulator`, we use `MeasureSuperposition.Run(sim)`.</span></span>
<span data-ttu-id="9dfd5-260">返された結果は、C# の変数に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-260">The returned results can then be assigned to variables in C#:</span></span>

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> <span data-ttu-id="9dfd5-261">`Run`このメソッドは、実際のクォンタムハードウェアの場合に使用されるため、非同期的に実行されます。したがって、キーワードは、 `await` タスクが完了するまでさらに処理をブロックします。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-261">The `Run` method is run asynchronously because this will be the case for real quantum hardware, and therefore the `await` keyword blocks further processing until the task completes.</span></span>

<span data-ttu-id="9dfd5-262">:::no-loc(Q#):::呼び出し可能なが返されない場合 (戻り値の型がある場合など `Unit` )、変数に代入せずに、実行を同じ方法で実行できます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-262">If the :::no-loc(Q#)::: callable does not have any returns (for example, it has return type `Unit`), then the run can still be done in the same manner without assigning it to a variable.</span></span>
<span data-ttu-id="9dfd5-263">その場合、行全体は単に</span><span class="sxs-lookup"><span data-stu-id="9dfd5-263">In that case, the entire line would simply consist of</span></span> 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a><span data-ttu-id="9dfd5-264">引数</span><span class="sxs-lookup"><span data-stu-id="9dfd5-264">Arguments</span></span>

<span data-ttu-id="9dfd5-265">呼び出し可能な引数 :::no-loc(Q#)::: は、ターゲットコンピューターの後に追加の引数として渡されるだけです。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-265">Any arguments to the :::no-loc(Q#)::: callable are simply passed as additional arguments after the target machine.</span></span>
<span data-ttu-id="9dfd5-266">したがって、qubits での結果は、を使用してフェッチされます。 `MeasureSuperpositionArray` `n=4`</span><span class="sxs-lookup"><span data-stu-id="9dfd5-266">Hence the results of `MeasureSuperpositionArray` on `n=4` qubits would fetched via</span></span> 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

<span data-ttu-id="9dfd5-267">完全な C# ホストプログラムは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-267">A full C# host program could thus look like</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine($"Multiple qubit result: {multiQubitResult}");
        }
    }
}
```

<span data-ttu-id="9dfd5-268">C# ファイルの場所では、「」と入力して、コマンドプロンプトからホストプログラムを実行できます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-268">At the location of the C# file, the host program can be run from the command prompt by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="9dfd5-269">この場合、次のような出力がコンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-269">and in this case you will see output written to the console similar to</span></span> 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> <span data-ttu-id="9dfd5-270">コンパイラの名前空間との相互運用性により、 :::no-loc(Q#)::: ステートメントを使用せずに呼び出し可能にすることができ `using NamespaceName;` ます。また、C# の名前空間のタイトルと単純に一致させることもできます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-270">Due to the compiler's interoperability with namespaces, we could alternatively make our :::no-loc(Q#)::: callables available without the `using NamespaceName;` statement, and simply matching the C# namespace title to it.</span></span>
> <span data-ttu-id="9dfd5-271">つまり、をに置き換え `namespace host` `namespace NamespaceName` ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-271">That is, by replacing `namespace host` with `namespace NamespaceName`.</span></span>

#### <a name="including-the-resources-estimator"></a><span data-ttu-id="9dfd5-272">リソースの推定機能を含む</span><span class="sxs-lookup"><span data-stu-id="9dfd5-272">Including the resources estimator</span></span>

<span data-ttu-id="9dfd5-273">では、 [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) 出力を取得するために若干異なる実装が必要です。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-273">The [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) requires a slightly different implementation to retrieve the output.</span></span>

<span data-ttu-id="9dfd5-274">まず、ステートメントを使用して変数としてインスタンス化する代わりに、を使用して `using` `QuantumSimulator` クラスのオブジェクトを直接インスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-274">Firstly, instead of instantiating them as a variable with a `using` statement (as we do with the `QuantumSimulator`), we more directly instantiate objects of the class via</span></span>

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

<span data-ttu-id="9dfd5-275">複数の操作で1つのターゲットシミュレーターが使用されるのではなく :::no-loc(Q#)::: 、それぞれに対して1つのターゲットシミュレーターがインスタンス化されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-275">Notice that instead of a single target simulator to be used by multiple :::no-loc(Q#)::: operations, we have instantiated one for each.</span></span> <span data-ttu-id="9dfd5-276">これは、ターゲットコンピューターとして使用されたときにオブジェクト自体が変更され、その結果をクラスメソッドで後から取得できるためです `.ToTSV()` 。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-276">This is because the objects themselves are modified when used as target machines, and their results can then be retrieved afterwards with the class method `.ToTSV()`.</span></span>

<span data-ttu-id="9dfd5-277">リソース estimators に対して操作を実行するには、次を使用します。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-277">To run the operations on the resource estimators, we use</span></span>

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
<span data-ttu-id="9dfd5-278">次に、とを使用して、結果をタブ区切り値 (TSV) としてフェッチし `estimatorSingleQ.ToTSV()` `estimatorMultiQ.ToTSV()` ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-278">and then fetch the results as tab-separated-values (TSV) with `estimatorSingleQ.ToTSV()` and `estimatorMultiQ.ToTSV()`.</span></span>

<span data-ttu-id="9dfd5-279">したがって、との両方を使用する完全な C# ホストプログラムは、次のような `QuantumSimulator` `ResourcesEstimator` 形式になります。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-279">So, a full C# host program making use of both the `QuantumSimulator` and `ResourcesEstimator` could take the form:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine("Single qubit resources:");
            Console.WriteLine(estimatorSingleQ.ToTSV());

            Console.WriteLine($"\nMultiple qubit result: {multiQubitResult}");
            Console.WriteLine("Multiple qubit resources:");
            Console.WriteLine(estimatorMultiQ.ToTSV());
        }
    }
}
```


<span data-ttu-id="9dfd5-280">これにより、のような出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-280">which would yield output similar to</span></span>

```output
Single qubit result: One
Single qubit resources:
Metric          Sum
CNOT            0
QubitClifford   1
R               0
Measure         1
T               0
Depth           0
Width           1
BorrowedWidth   0

Multiple qubit result: [One,One,One,Zero]
Multiple qubit resources:
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

***

## <a name="no-locq-jupyter-notebooks"></a><span data-ttu-id="9dfd5-281">:::no-loc(Q#)::: Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="9dfd5-281">:::no-loc(Q#)::: Jupyter Notebooks</span></span>
<span data-ttu-id="9dfd5-282">:::no-loc(Q#)::: Jupyter Notebook では、I カーネルを使用します :::no-loc(Q#)::: 。これにより、 :::no-loc(Q#)::: すべての命令、メモ、およびその他のコンテンツと共に、呼び出し可能なを1つのノートブックで定義、コンパイル、および実行することが---ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-282">:::no-loc(Q#)::: Jupyter Notebooks make use of the I:::no-loc(Q#)::: kernel, which allows you to define, compile, and run :::no-loc(Q#)::: callables in a single notebook---all alongside instructions, notes, and other content.</span></span>
<span data-ttu-id="9dfd5-283">つまり、ファイルの内容をインポートして使用することはできますが、 `*.qs` :::no-loc(Q#)::: 実行モデルでは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-283">This means that while it is possible to import and use the contents of `*.qs` :::no-loc(Q#)::: files, they are not necessary in the run model.</span></span>

<span data-ttu-id="9dfd5-284">ここでは、上で定義した操作を実行する方法について詳しく説明します :::no-loc(Q#)::: が、jupyter notebook の使用方法の概要については、「 :::no-loc(Q#)::: 概要」と「 [ :::no-loc(Q#)::: jupyter notebook](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-284">Here, we will detail how to run the :::no-loc(Q#)::: operations defined above, but a more broad introduction to using :::no-loc(Q#)::: Jupyter Notebooks is provided at [Intro to :::no-loc(Q#)::: and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span></span>

### <a name="defining-operations"></a><span data-ttu-id="9dfd5-285">定義 (操作を)</span><span class="sxs-lookup"><span data-stu-id="9dfd5-285">Defining operations</span></span>

<span data-ttu-id="9dfd5-286">Jupyter Notebook では :::no-loc(Q#)::: 、 :::no-loc(Q#)::: ファイルの名前空間内と同様にコードを入力し :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-286">In a :::no-loc(Q#)::: Jupyter Notebook, you enter :::no-loc(Q#)::: code just as we would from inside the namespace of a :::no-loc(Q#)::: file.</span></span>

<span data-ttu-id="9dfd5-287">そのため、 [ :::no-loc(Q#)::: 標準ライブラリ](xref:microsoft.quantum.qsharplibintro)から、 `open` それぞれの名前空間のステートメントを使用して、呼び出し可能なアクセスを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-287">So, we can enable access to callables from the [:::no-loc(Q#)::: standard libraries](xref:microsoft.quantum.qsharplibintro) with `open` statements for their respective namespaces.</span></span>
<span data-ttu-id="9dfd5-288">このようなステートメントでセルを実行すると、その名前空間の定義がワークスペース全体で使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-288">Upon running a cell with such a statement, the definitions from those namespaces are available throughout the workspace.</span></span>

> [!NOTE]
> <span data-ttu-id="9dfd5-289">[Microsoft の quantum](xref:Microsoft.Quantum.Intrinsic)および[microsoft の quantum](xref:Microsoft.Quantum.Canon) (たとえば、や) からの呼び出し [`H`](xref:Microsoft.Quantum.Intrinsic.H) [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) 可能範囲は、jupyter notebook のセル内に定義されている操作で自動的に使用できるようになります。 :::no-loc(Q#):::</span><span class="sxs-lookup"><span data-stu-id="9dfd5-289">Callables from [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic) and [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon) (for example, [`H`](xref:Microsoft.Quantum.Intrinsic.H) and [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach)) are automatically available to operations defined within cells in :::no-loc(Q#)::: Jupyter Notebooks.</span></span>
> <span data-ttu-id="9dfd5-290">ただし、外部ソースファイルからのコードには当てはまりません :::no-loc(Q#)::: ( [概要 :::no-loc(Q#)::: と Jupyter notebook](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)に示されているプロセス)。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-290">However, this is not true for code brought in from external :::no-loc(Q#)::: source files (a process shown at [Intro to :::no-loc(Q#)::: and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span></span> 
> 

<span data-ttu-id="9dfd5-291">同様に、操作を定義するには、コードの記述 :::no-loc(Q#)::: とセルの実行のみが必要です。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-291">Similarly, defining operations requires only writing the :::no-loc(Q#)::: code and running the cell.</span></span>

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining :::no-loc(Q#)::: operations" width="773">

<span data-ttu-id="9dfd5-292">出力には、これらの操作が一覧表示されます。これらの操作は、今後のセルから呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-292">The output then lists those operations, which can then be called from future cells.</span></span>

### <a name="target-machines"></a><span data-ttu-id="9dfd5-293">ターゲット コンピューター</span><span class="sxs-lookup"><span data-stu-id="9dfd5-293">Target machines</span></span>

<span data-ttu-id="9dfd5-294">特定の対象コンピューターで操作を実行する機能は、 [I :::no-loc(Q#)::: マジックコマンド](xref:microsoft.quantum.guide.quickref.iqsharp)を使用して提供されます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-294">The functionality to run operations on specific target machines is provided via [I:::no-loc(Q#)::: Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp).</span></span>
<span data-ttu-id="9dfd5-295">たとえば、はを使用し、を使用し `%simulate` `QuantumSimulator` `%estimate` `ResourcesEstimator` ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-295">For example, `%simulate` makes use of the `QuantumSimulator`, and `%estimate` uses the `ResourcesEstimator`:</span></span>

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Jupyter cell simulating a :::no-loc(Q#)::: operation and running resource estimation" width="773">

### <a name="passing-inputs-to-functions-and-operations"></a><span data-ttu-id="9dfd5-296">関数および操作への入力の引き渡し</span><span class="sxs-lookup"><span data-stu-id="9dfd5-296">Passing inputs to functions and operations</span></span>

<span data-ttu-id="9dfd5-297">操作に入力を渡すために、 :::no-loc(Q#)::: 引数をペアとして `key=value` 実行マジックコマンドに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-297">To pass inputs to the :::no-loc(Q#)::: operations, the arguments can be passed as `key=value` pairs to the run magic command.</span></span>
<span data-ttu-id="9dfd5-298">そのため、 `MeasureSuperpositionArray` 4 つの qubits を使用してを実行するには、次のように実行し `%simulate MeasureSuperpositionArray n=4` ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-298">So, to run `MeasureSuperpositionArray` with four qubits, we can run `%simulate MeasureSuperpositionArray n=4`:</span></span>

<img src="../media/hostprograms_jupyter_args_sim_crop.png" alt="Jupyter cell simulating a :::no-loc(Q#)::: operation with arguments" width="773">

<span data-ttu-id="9dfd5-299">このパターンは `%estimate` 、およびその他の実行コマンドと同様に使用できます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-299">This pattern can be used similarly with `%estimate` and other run commands.</span></span>

### <a name="using-no-locq-code-from-other-projects-or-packages"></a><span data-ttu-id="9dfd5-300">:::no-loc(Q#):::他のプロジェクトまたはパッケージからのコードの使用</span><span class="sxs-lookup"><span data-stu-id="9dfd5-300">Using :::no-loc(Q#)::: code from other projects or packages</span></span>

<span data-ttu-id="9dfd5-301">既定では、 :::no-loc(Q#)::: Jupyter Notebook は現在のフォルダーにあるすべてのファイルを読み込み、その `.qs` :::no-loc(Q#)::: 操作と機能を Notebook 内から使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-301">By default, a :::no-loc(Q#)::: Jupyter Notebook loads all of the `.qs` files in the current folder and makes their :::no-loc(Q#)::: operations and functions available for use from inside the notebook.</span></span> <span data-ttu-id="9dfd5-302">[ `%who` マジックコマンド](xref:microsoft.quantum.iqsharp.magic-ref.who)では、現在使用可能なすべての操作と関数が一覧表示され :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-302">The [`%who` magic command](xref:microsoft.quantum.iqsharp.magic-ref.who) lists all currently-available :::no-loc(Q#)::: operations and functions.</span></span>

<span data-ttu-id="9dfd5-303">別のフォルダーからコードを読み込むには、 :::no-loc(Q#)::: [ `%project` マジックコマンド](xref:microsoft.quantum.iqsharp.magic-ref.project)を使用して、 `.csproj` プロジェクトのファイル (つまり :::no-loc(Q#)::: 、を参照するプロジェクト) への参照を追加し `Microsoft.Quantum.Sdk` ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-303">To load :::no-loc(Q#)::: code from another folder, the [`%project` magic command](xref:microsoft.quantum.iqsharp.magic-ref.project) can be used to add a reference to a `.csproj` file for a :::no-loc(Q#)::: project (that is, a project that references `Microsoft.Quantum.Sdk`).</span></span> <span data-ttu-id="9dfd5-304">このコマンドを実行する `.qs` `.csproj` と、(およびサブフォルダー) を含むフォルダー内のすべてのファイルがコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-304">This command will compile any `.qs` files in the folder containing the `.csproj` (and subfolders).</span></span> <span data-ttu-id="9dfd5-305">また、またはから参照されるプロジェクトを通じて参照されるパッケージも、そのファイルで再帰的に読み込まれ `PackageReference` :::no-loc(Q#)::: `ProjectReference` `.csproj` ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-305">It will also recursively load any packages referenced via `PackageReference` or :::no-loc(Q#)::: projects referenced via `ProjectReference` in that `.csproj` file.</span></span> 

<span data-ttu-id="9dfd5-306">たとえば、次のセルは、現在の :::no-loc(Q#)::: フォルダーを基準としてプロジェクトパスが参照される外部プロジェクトからの操作をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-306">As an example, the following cells simulate a :::no-loc(Q#)::: operation from an external project, where the project path is referenced relative to the current folder:</span></span>

<img src="../media/hostprograms_jupyter_project_crop.png" alt="Jupyter cell simulating a :::no-loc(Q#)::: operation from an external project" width="773">

<span data-ttu-id="9dfd5-307">コードを含む外部パッケージを読み込むには :::no-loc(Q#)::: 、 [ `%package` マジックコマンド](xref:microsoft.quantum.iqsharp.magic-ref.package)を使用します。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-307">To load external packages containing :::no-loc(Q#)::: code, use the [`%package` magic command](xref:microsoft.quantum.iqsharp.magic-ref.package).</span></span>
<span data-ttu-id="9dfd5-308">パッケージを読み込むと、パッケージの一部であるすべてのアセンブリに含まれている任意のカスタムマジックコマンドまたは表示エンコーダーも使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-308">Loading a package will also make available any custom magic commands or display encoders that are contained in any assemblies that are part of the package.</span></span>

<span data-ttu-id="9dfd5-309">ノートブックの初期化時に外部パッケージまたはプロジェクトを読み込むには :::no-loc(Q#)::: 、notebook フォルダーにを参照するファイルが含まれていることを確認し `.csproj` `Microsoft.Quantum.Sdk` ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-309">To load external packages or :::no-loc(Q#)::: projects at notebook intialization time, ensure that the notebook folder contains a `.csproj` file which references `Microsoft.Quantum.Sdk`.</span></span> <span data-ttu-id="9dfd5-310">その中で、 `.csproj` プロパティを `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` に追加し `<PropertyGroup>` ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-310">In that `.csproj`, add the property `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` to the `<PropertyGroup>`.</span></span> <span data-ttu-id="9dfd5-311">これにより、 :::no-loc(Q#)::: `ProjectReference` notebook の読み込み時に、 `PackageReference` で見つかった項目または項目を再帰的に読み込むように指示され `.csproj` ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-311">This will instruct I:::no-loc(Q#)::: to recursively load any `ProjectReference` or `PackageReference` items found in that `.csproj` at notebook load time.</span></span>

<span data-ttu-id="9dfd5-312">たとえば、 `.csproj` パッケージを自動的に読み込む単純なファイルを次に示し :::no-loc(Q#)::: `Microsoft.Quantum.Chemistry` ます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-312">For example, here is a simple `.csproj` file that causes I:::no-loc(Q#)::: to automatically load the `Microsoft.Quantum.Chemistry` package:</span></span>

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="9dfd5-313">現在、このカスタム `<IQSharpLoadAutomatically>` プロパティは Jupyter Notebook ホストで要求されてい :::no-loc(Q#)::: ますが、今後、 `.csproj` Notebook ファイルと同じフォルダーにあるファイルの既定の動作になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-313">Currently this custom `<IQSharpLoadAutomatically>` property is required by :::no-loc(Q#)::: Jupyter Notebook hosts, but in the future, this may become the default behavior for a `.csproj` file located in the same folder as the notebook file.</span></span>

> [!NOTE]
> <span data-ttu-id="9dfd5-314">現在 `<QsharpCompile>` 、の設定は `.csproj` Jupyter Notebook ホストによって無視され、 :::no-loc(Q#)::: `.qs` のフォルダー (サブフォルダーを含む) 内のすべてのファイルが `.csproj` 読み込まれ、コンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-314">Currently the `<QsharpCompile>` setting in the `.csproj` is ignored by :::no-loc(Q#)::: Jupyter Notebook hosts, and all `.qs` files in the folder of the `.csproj` (including subfolders) are loaded and compiled.</span></span> <span data-ttu-id="9dfd5-315">設定のサポートは `.csproj` 今後改善される予定です (詳細については、「 [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) 」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="9dfd5-315">Support for `.csproj` settings will be improved in the future (see [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for more details).</span></span>
