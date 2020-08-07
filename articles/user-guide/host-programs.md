---
title: プログラムを実行する方法 Q#
description: プログラムを実行するさまざまな方法の概要を説明し Q# ます。 Python または .NET 言語のコマンドライン、 Q# jupyter notebook、およびクラシックホストプログラム。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8e3fa83700417a4ffaf9e3be91796c9e9513b253
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869734"
---
# <a name="ways-to-run-a-no-locq-program"></a><span data-ttu-id="2808b-104">プログラムを実行する方法 Q#</span><span class="sxs-lookup"><span data-stu-id="2808b-104">Ways to run a Q# program</span></span>

<span data-ttu-id="2808b-105">Quantum Development Kit の最大の強みの1つは、プラットフォームと開発環境全体での柔軟性です。</span><span class="sxs-lookup"><span data-stu-id="2808b-105">One of the Quantum Development Kit's greatest strengths is its flexibility across platforms and development environments.</span></span>
<span data-ttu-id="2808b-106">ただし、これは、新しい Q# ユーザーが、[インストールガイド](xref:microsoft.quantum.install)に記載されている多くのオプションによって混乱を招き、圧倒される可能性があることも意味します。</span><span class="sxs-lookup"><span data-stu-id="2808b-106">However, this also means that new Q# users may find themselves confused or overwhelmed by the numerous options found in the [install guide](xref:microsoft.quantum.install).</span></span>
<span data-ttu-id="2808b-107">このページでは、プログラムの実行時の動作につい Q# て説明し、ユーザーが実行できるさまざまな方法を比較します。</span><span class="sxs-lookup"><span data-stu-id="2808b-107">On this page, we explain what happens when a Q# program is run, and compare the different ways in which users can do so.</span></span>

<span data-ttu-id="2808b-108">主な違いは、を Q# 実行できることです。</span><span class="sxs-lookup"><span data-stu-id="2808b-108">A primary distinction is that Q# can be run:</span></span>
- <span data-ttu-id="2808b-109">スタンドアロンアプリケーションとして、 Q# は関連する唯一の言語であり、プログラムは直接呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2808b-109">as a standalone application, where Q# is the only language involved and the program is invoked directly.</span></span> <span data-ttu-id="2808b-110">このカテゴリには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="2808b-110">Two methods actually fall in this category:</span></span>
  - <span data-ttu-id="2808b-111">コマンドラインインターフェイス</span><span class="sxs-lookup"><span data-stu-id="2808b-111">the command line interface</span></span>
  - <span data-ttu-id="2808b-112">Q#Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="2808b-112">Q# Jupyter Notebooks</span></span>
- <span data-ttu-id="2808b-113">Python または .NET 言語 (C# や F # など) で記述された追加の*ホストプログラム*を使用して、プログラムを呼び出し、返された結果をさらに処理することができます。</span><span class="sxs-lookup"><span data-stu-id="2808b-113">with an additional *host program*, written in Python or a .NET language (e.g. C# or F#), which then invokes the program and can further process returned results.</span></span>

<span data-ttu-id="2808b-114">これらのプロセスとその違いについて理解を深めるために、単純なプログラムを考えて、 Q# 実行する方法を比較します。</span><span class="sxs-lookup"><span data-stu-id="2808b-114">To best understand these processes and their differences, we consider a simple Q# program and compare the ways it can be executed.</span></span>

## <a name="basic-no-locq-program"></a><span data-ttu-id="2808b-115">基本 Q# プログラム</span><span class="sxs-lookup"><span data-stu-id="2808b-115">Basic Q# program</span></span>

<span data-ttu-id="2808b-116">基本的な量子プログラムは、法則の状態が $ \ket $ および $ \ket $ の qubit を準備し、それを測定し、結果を返すことで構成される場合があり {0} {1} ます。これは、これら2つの状態のうち、確率が等しい場合に、ランダムに発生します。</span><span class="sxs-lookup"><span data-stu-id="2808b-116">A basic quantum program might consist of preparing a qubit in an equal superposition of states $\ket{0}$ and $\ket{1}$, measuring it, and returning the result, which will be randomly either one of these two states with equal probability.</span></span>
<span data-ttu-id="2808b-117">実際には、このプロセスは、クォンタムの[乱数ジェネレーター](xref:microsoft.quantum.quickstarts.qrng)のクイックスタートの中核になっています。</span><span class="sxs-lookup"><span data-stu-id="2808b-117">Indeed, this process is at the core of the [quantum random number generator](xref:microsoft.quantum.quickstarts.qrng) quickstart.</span></span>

<span data-ttu-id="2808b-118">では Q# 、これは次のコードによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="2808b-118">In Q#, this would be performed by the following code:</span></span>

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

<span data-ttu-id="2808b-119">ただし、このコードだけをで実行することはできません Q# 。</span><span class="sxs-lookup"><span data-stu-id="2808b-119">However, this code alone can't be executed by Q#.</span></span>
<span data-ttu-id="2808b-120">そのためには、操作の本体を構成する必要があります。この[操作](xref:microsoft.quantum.guide.basics#q-operations-and-functions)は、直接または別の操作によって---呼び出されたときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="2808b-120">For that, it needs to make up the body of an [operation](xref:microsoft.quantum.guide.basics#q-operations-and-functions), which is then executed when called---either directly or by another operation.</span></span> <span data-ttu-id="2808b-121">そのため、次の形式の操作を記述できます。</span><span class="sxs-lookup"><span data-stu-id="2808b-121">Hence, you can write an operation of the following form:</span></span>
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
<span data-ttu-id="2808b-122">`MeasureSuperposition`入力を受け取らず、 [Result](xref:microsoft.quantum.guide.types)型の値を返す操作を定義しました。</span><span class="sxs-lookup"><span data-stu-id="2808b-122">You have defined an operation, `MeasureSuperposition`, which takes no inputs and returns a value of type [Result](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="2808b-123">このページの例は操作のみで構成 Q# *operations*されていますが、ここで説明するすべての概念は、関数にも同様に関係 Q# *functions*します。そのため、これらのすべての概念を*呼び出し*が許容できるものとして参照します。</span><span class="sxs-lookup"><span data-stu-id="2808b-123">While the examples on this page only consist of Q# *operations*, all of the concepts we will discuss pertain equally to Q# *functions*, and therefore we refer to them collectively as *callables*.</span></span> <span data-ttu-id="2808b-124">これらの違いについては、 [ Q# 「基本: 操作と関数](xref:microsoft.quantum.guide.basics#q-operations-and-functions)」で説明されています。これらの定義の詳細については、「[操作と関数](xref:microsoft.quantum.guide.operationsfunctions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2808b-124">Their differences are discussed at [Q# basics: operations and functions](xref:microsoft.quantum.guide.basics#q-operations-and-functions), and more details on defining them can be found at [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

### <a name="callable-defined-in-a-no-locq-file"></a><span data-ttu-id="2808b-125">ファイルで定義された呼び出し可能 Q#</span><span class="sxs-lookup"><span data-stu-id="2808b-125">Callable defined in a Q# file</span></span>

<span data-ttu-id="2808b-126">呼び出し可能なは、によって呼び出され、実行され Q# ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-126">The callable is precisely what's called and run by Q#.</span></span>
<span data-ttu-id="2808b-127">ただし、完全なファイルを構成するには、さらにいくつかの追加機能が必要です `*.qs` Q# 。</span><span class="sxs-lookup"><span data-stu-id="2808b-127">However, it requires a few more additions to comprise a full `*.qs` Q# file.</span></span>

<span data-ttu-id="2808b-128">すべての Q# 型と呼び出し可能 (定義したものと言語に固有の型の両方) は、*名前空間*内で定義されます。これらの名前は、参照可能な完全な名前を提供します。</span><span class="sxs-lookup"><span data-stu-id="2808b-128">All Q# types and callables (both those you define and those intrinsic to the language) are defined within *namespaces*, which provide each a full name that can then be referenced.</span></span>

<span data-ttu-id="2808b-129">たとえば、およびの [`H`](xref:microsoft.quantum.intrinsic.h) 各 [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) 操作は、 [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) 名前空間と名前空間 ( [ Q# 標準ライブラリ](xref:microsoft.quantum.qsharplibintro)の一部) にあります。</span><span class="sxs-lookup"><span data-stu-id="2808b-129">For example, the [`H`](xref:microsoft.quantum.intrinsic.h) and [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) operations are found in the [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) and [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) namespaces (part of the [Q# Standard Libraries](xref:microsoft.quantum.qsharplibintro)).</span></span>
<span data-ttu-id="2808b-130">そのため、常に*完全な*名前を使用してを呼び出すことができます `Microsoft.Quantum.Intrinsic.H(<qubit>)` が、 `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` 常にこの操作を実行すると、コードが乱雑になることがあります。</span><span class="sxs-lookup"><span data-stu-id="2808b-130">As such, they can always be called via their *full* names, `Microsoft.Quantum.Intrinsic.H(<qubit>)` and `Microsoft.Quantum.Measurement.MResetZ(<qubit>)`, but always doing this would lead to very cluttered code.</span></span>

<span data-ttu-id="2808b-131">ステートメントを `open` 使用すると、上記の操作本体で行ったように、より簡潔な短縮形で呼び出し可能なを参照できます。</span><span class="sxs-lookup"><span data-stu-id="2808b-131">Instead, `open` statements allow callables to be referenced with more concise shorthand, as we've done in the operation body above.</span></span>
<span data-ttu-id="2808b-132">Q#このため、操作を含む完全なファイルは、独自の名前空間を定義し、操作が使用する呼び出しの名前空間を開いて、次の操作を行うことで構成されます。</span><span class="sxs-lookup"><span data-stu-id="2808b-132">The full Q# file containing our operation would therefore consist of defining our own namespace, opening the namespaces for those callables our operation uses, and then our operation:</span></span>

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
> <span data-ttu-id="2808b-133">名前空間は、開いたときに*別名*を付けることもできます。これは、2つの名前空間の呼び出し可能な名前または型名が競合する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2808b-133">Namespaces can also be *aliased* when opened, which can be helpful if callable/type names in two namespaces conflict.</span></span>
> <span data-ttu-id="2808b-134">たとえば、代わりにを使用してから、を使用してを呼び出すこともでき `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` `H` `NamespaceWithH.H(<qubit>)` ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-134">For example, we could instead use `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` above, and then call `H` via `NamespaceWithH.H(<qubit>)`.</span></span>

> [!NOTE]
> <span data-ttu-id="2808b-135">すべての例外の1つとして、 [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) 常に自動的に開かれる名前空間があります。</span><span class="sxs-lookup"><span data-stu-id="2808b-135">One exception to all of this is the [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) namespace, which is always automatically opened.</span></span>
> <span data-ttu-id="2808b-136">そのため、のような呼び出し可能なは、 [`Length`](xref:microsoft.quantum.core.length) 常に直接使用できます。</span><span class="sxs-lookup"><span data-stu-id="2808b-136">Therefore, callables like [`Length`](xref:microsoft.quantum.core.length) can always be used directly.</span></span>

### <a name="execution-on-target-machines"></a><span data-ttu-id="2808b-137">ターゲットコンピューターでの実行</span><span class="sxs-lookup"><span data-stu-id="2808b-137">Execution on target machines</span></span>

<span data-ttu-id="2808b-138">これで、プログラムの一般的な実行モデルが明確になりました Q# 。</span><span class="sxs-lookup"><span data-stu-id="2808b-138">Now the general execution model of a Q# program becomes clear.</span></span>

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

<span data-ttu-id="2808b-139">最初に、実行される特定の呼び出し可能なは、同じ名前空間で定義されている他の呼び出し可能な型と型にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2808b-139">Firstly, the specific callable to be executed has access to any other callables and types defined in the same namespace.</span></span>
<span data-ttu-id="2808b-140">また、 [ Q# ライブラリ](xref:microsoft.quantum.libraries)からアクセスすることもできますが、フルネームを使用するか、上記のステートメントを使用して参照する必要があり `open` ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-140">It also access those from any of the [Q# libraries](xref:microsoft.quantum.libraries), but those must be referenced either via their full name, or through the use of `open` statements described above.</span></span>

<span data-ttu-id="2808b-141">その後、呼び出し可能なものが*[ターゲットコンピューター](xref:microsoft.quantum.machines)* 上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="2808b-141">The callable itself is then executed on a *[target machine](xref:microsoft.quantum.machines)*.</span></span>
<span data-ttu-id="2808b-142">このようなターゲットマシンは、実際の quantum ハードウェア、または QDK の一部として提供されている複数のシミュレーターにすることができます。</span><span class="sxs-lookup"><span data-stu-id="2808b-142">Such target machines can be actual quantum hardware or the multiple simulators available as part of the QDK.</span></span>
<span data-ttu-id="2808b-143">ここでの目的のために、最も役に立つターゲットコンピューターは、[フルステートシミュレーター](xref:microsoft.quantum.machines.full-state-simulator)のインスタンスです。これは `QuantumSimulator` 、ノイズフリーのクォンタムコンピューターで実行されているかのようにプログラムの動作を計算します。</span><span class="sxs-lookup"><span data-stu-id="2808b-143">For our purposes here, the most useful target machine is an instance of the [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator`, which calculates the program's behavior as if it were being executed on a noise-free quantum computer.</span></span>

<span data-ttu-id="2808b-144">ここまでは、特定の Q# 呼び出し可能が実行されたときの動作について説明しました。</span><span class="sxs-lookup"><span data-stu-id="2808b-144">So far, we've described what happens when a specific Q# callable is being executed.</span></span>
<span data-ttu-id="2808b-145">がスタンドアロンアプリケーションとホストプログラムのどちらで使用されているかにかかわらず Q# 、この一般的なプロセスは同じ---であるため、QDK の柔軟性があります。</span><span class="sxs-lookup"><span data-stu-id="2808b-145">Regardless of whether Q# is used in a standalone application or with a host program, this general process is more or less the same---hence the QDK's flexibility.</span></span>
<span data-ttu-id="2808b-146">クォンタム開発キットを呼び出すさまざまな方法の違いにより、呼び出し可能な呼び出しの実行*方法*と、結果が返される方法を区別して Q# います。</span><span class="sxs-lookup"><span data-stu-id="2808b-146">The differences between the different ways of calling into the Quantum Development Kit therefore reveal themselves in *how* that Q# callable is called to be executed, and in what manner any results are returned.</span></span>
<span data-ttu-id="2808b-147">具体的には、</span><span class="sxs-lookup"><span data-stu-id="2808b-147">More specifically, the differences revolve around</span></span> 
1. <span data-ttu-id="2808b-148">実行される呼び出し元を示します。 Q#</span><span class="sxs-lookup"><span data-stu-id="2808b-148">indicating which Q# callable is to be executed,</span></span>
2. <span data-ttu-id="2808b-149">可能性のある呼び出し可能な引数の提供方法</span><span class="sxs-lookup"><span data-stu-id="2808b-149">how potential callable arguments are provided,</span></span>
3. <span data-ttu-id="2808b-150">実行するターゲットコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="2808b-150">specifying the target machine on which to execute it, and</span></span>
4. <span data-ttu-id="2808b-151">結果が返される方法。</span><span class="sxs-lookup"><span data-stu-id="2808b-151">how any results are returned.</span></span>

<span data-ttu-id="2808b-152">まず、コマンドラインからスタンドアロンアプリケーションを使用してこれがどのように行われるかについて説明 Q# し、次に Python および C# ホストプログラムの使用に進みます。</span><span class="sxs-lookup"><span data-stu-id="2808b-152">First, we discuss how this is done with the Q# standalone application from the command line, and then proceed to using Python and C# host programs.</span></span>
<span data-ttu-id="2808b-153">Jupyter Notebook のスタンドアロンアプリケーションは、 Q# 最初の3つとは異なり、プライマリ機能はローカルファイルを中心にしていません Q# 。</span><span class="sxs-lookup"><span data-stu-id="2808b-153">We reserve the standalone application of Q# Jupyter Notebooks for last, because unlike the first three, it's primary functionality does not center around a local Q# file.</span></span>

> [!NOTE]
> <span data-ttu-id="2808b-154">これらの例では説明しませんが、実行メソッド間の1つの共通点として、プログラム内から Q# (またはなどによって) 出力されるすべてのメッセージは、 [`Message`](xref:microsoft.quantum.intrinsic.message) [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) 通常、それぞれのコンソールに出力されます。</span><span class="sxs-lookup"><span data-stu-id="2808b-154">Although we don't illustrate it in these examples, one commonality between the execution methods is that any messages printed from inside the Q# program (by way of [`Message`](xref:microsoft.quantum.intrinsic.message) or [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine), for example) will typically always be printed to the respective console.</span></span>

## <a name="no-locq-from-the-command-line"></a><span data-ttu-id="2808b-155">Q#コマンドラインから</span><span class="sxs-lookup"><span data-stu-id="2808b-155">Q# from the command line</span></span>
<span data-ttu-id="2808b-156">プログラムの記述を開始する最も簡単な方法の1つ Q# は、個別のファイルと2番目の言語をまったく気にすることがないようにすることです。</span><span class="sxs-lookup"><span data-stu-id="2808b-156">One of the easiest ways to get started writing Q# programs is to avoid worrying about separate files and a second language altogether.</span></span>
<span data-ttu-id="2808b-157">QDK 拡張機能を使用して Visual Studio Code または Visual Studio を使用すると、 Q# 1 つのファイルから呼び出し可能なものだけを実行するシームレスな作業フローを実現でき Q# ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-157">Using Visual Studio Code or Visual Studio with the QDK extension allows for a seamless work flow in which we run Q# callables from only a single Q# file.</span></span>

<span data-ttu-id="2808b-158">この場合、最終的には、次のように入力して、プログラムの実行を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2808b-158">For this, we will ultimately invoke the program's execution by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="2808b-159">をコマンドラインで実行します。</span><span class="sxs-lookup"><span data-stu-id="2808b-159">in the command line.</span></span>
<span data-ttu-id="2808b-160">最も単純なワークフローは、ターミナルのディレクトリの場所がファイルと同じ場合です Q# Q# 。たとえば、VS Code の統合ターミナルを使用して、ファイルの編集と共に簡単に処理できます。</span><span class="sxs-lookup"><span data-stu-id="2808b-160">The simplest workflow is when the terminal's directory location is the same as the Q# file, which can be easily handled alongside Q# file editing by using the integrated terminal in VS Code, for example.</span></span>
<span data-ttu-id="2808b-161">ただし、 [ `dotnet run` コマンド](https://docs.microsoft.com/dotnet/core/tools/dotnet-run)は多くのオプションを受け入れます。プログラムは、 `--project <PATH>` ファイルの場所を指定するだけで別の場所から実行することもできます Q# 。</span><span class="sxs-lookup"><span data-stu-id="2808b-161">However, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) accepts numerous options, and the program can also be run from a different location by simply providing `--project <PATH>` with the location of the Q# file.</span></span>


### <a name="add-entry-point-to-no-locq-file"></a><span data-ttu-id="2808b-162">ファイルへのエントリポイントの追加 Q#</span><span class="sxs-lookup"><span data-stu-id="2808b-162">Add entry point to Q# file</span></span>

<span data-ttu-id="2808b-163">ほとんど Q# のファイルには複数の呼び出し可能が含まれているため、当然ながら、コマンドを指定したときに実行さ*れる呼び出し元*をコンパイラに知らせる必要があり `dotnet run` ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-163">Most Q# files will contain more than one callable, so naturally we need to let the compiler know *which* callable to execute when we provide the `dotnet run` command.</span></span>
<span data-ttu-id="2808b-164">これは、ファイル自体を単純に変更することで行われ Q# ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-164">This is done with a simple change to the Q# file itself:</span></span> 
    - <span data-ttu-id="2808b-165">呼び出し可能なの直前に行を追加 `@EntryPoint()` します。</span><span class="sxs-lookup"><span data-stu-id="2808b-165">add a line with `@EntryPoint()` directly preceding the callable.</span></span>

<span data-ttu-id="2808b-166">そのため、上記のファイルは</span><span class="sxs-lookup"><span data-stu-id="2808b-166">Our file from above would therefore become</span></span>
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

<span data-ttu-id="2808b-167">これで、コマンドラインからを呼び出すと、が `dotnet run` `MeasureSuperposition` 実行され、返された値がターミナルに直接出力されます。</span><span class="sxs-lookup"><span data-stu-id="2808b-167">Now, a call of `dotnet run` from the command line leads to `MeasureSuperposition` being run, and the returned value is then printed directly to the terminal.</span></span>
<span data-ttu-id="2808b-168">そのため、またはのどちらかが表示され `One` `Zero` ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-168">So, you will see either `One` or `Zero` printed.</span></span> 

<span data-ttu-id="2808b-169">より多くの呼び出し可能を定義しているかどうかは関係ありません `MeasureSuperposition` 。実行されるのはのみです。</span><span class="sxs-lookup"><span data-stu-id="2808b-169">Note that it doesn't matter if you have more callables defined below it, only `MeasureSuperposition` will be run.</span></span>
<span data-ttu-id="2808b-170">また、呼び出し元が宣言の前に[ドキュメントコメント](xref:microsoft.quantum.guide.filestructure#documentation-comments)を含んでいる場合は問題ありません `@EntryPoint()` 。属性は、単純にその上に配置できます。</span><span class="sxs-lookup"><span data-stu-id="2808b-170">Additionally, it's no problem if your callable includes [documentation comments](xref:microsoft.quantum.guide.filestructure#documentation-comments) before its declaration, the `@EntryPoint()` attribute can be simply placed above them.</span></span>

### <a name="callable-arguments"></a><span data-ttu-id="2808b-171">呼び出し可能引数</span><span class="sxs-lookup"><span data-stu-id="2808b-171">Callable arguments</span></span>

<span data-ttu-id="2808b-172">ここまでは、入力を必要としない操作についてのみ検討しました。</span><span class="sxs-lookup"><span data-stu-id="2808b-172">So far, we've only considered an operation that takes no inputs.</span></span>
<span data-ttu-id="2808b-173">同様の操作を実行するとしますが、複数の qubits---、引数として指定されている数を示しています。</span><span class="sxs-lookup"><span data-stu-id="2808b-173">Suppose we wanted to perform a similar operation, but on multiple qubits---the number of which is provided as an argument.</span></span>
<span data-ttu-id="2808b-174">このような操作は、</span><span class="sxs-lookup"><span data-stu-id="2808b-174">Such an operation could be written as</span></span>
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
<span data-ttu-id="2808b-175">返される値は、測定結果の配列です。</span><span class="sxs-lookup"><span data-stu-id="2808b-175">where the returned value is an array of the measurement results.</span></span>
<span data-ttu-id="2808b-176">[`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach)と [`ForEach`](xref:microsoft.quantum.arrays.foreach) は名前空間にあり [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) 、 `open` それぞれに対して追加のステートメントが必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2808b-176">Note that [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) and [`ForEach`](xref:microsoft.quantum.arrays.foreach) are in the [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) and [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) namespaces, requiring additional `open` statements for each.</span></span>

<span data-ttu-id="2808b-177">`@EntryPoint()`この新しい操作の前に属性を移動した場合 (ファイル内にはそのような行が1つだけ存在する場合があることに注意してください)、を使用して実行しようとすると、 `dotnet run` 必要な追加のコマンドラインオプションを示すエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2808b-177">If we move the `@EntryPoint()` attribute to precede this new operation (note there can only be one such line in a file), attempting to run it with simply `dotnet run` results in an error message which indicates what additional command line options are required, and how to express them.</span></span>

<span data-ttu-id="2808b-178">コマンドラインの一般的な形式は実際にはであり、呼び出し可能な引数がそこに用意されてい `dotnet run [options]` ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-178">The general format for the command line is actually `dotnet run [options]`, and callable arguments are provided there.</span></span>
<span data-ttu-id="2808b-179">この場合、引数 `n` が不足しているため、オプションを指定する必要があることが示されて `-n <n>` います。</span><span class="sxs-lookup"><span data-stu-id="2808b-179">In this case, the argument `n` is missing, and it shows that we need to provide the option `-n <n>`.</span></span> <span data-ttu-id="2808b-180">Qubits でを実行するには、次のように `MeasureSuperpositionArray` `n=4` します。</span><span class="sxs-lookup"><span data-stu-id="2808b-180">To run `MeasureSuperpositionArray` for `n=4` qubits, we therefore use</span></span>

```dotnetcli
dotnet run -n 4
```

<span data-ttu-id="2808b-181">のような出力を生成する</span><span class="sxs-lookup"><span data-stu-id="2808b-181">yielding an output similar to</span></span>

```output
[Zero,One,One,One]
```

<span data-ttu-id="2808b-182">これは、複数の引数にまで拡張されています。</span><span class="sxs-lookup"><span data-stu-id="2808b-182">This of course extends to multiple arguments.</span></span>

> [!NOTE]
> <span data-ttu-id="2808b-183">で定義されている引数名 `camelCase` は、入力として受け入れられるように、コンパイラによって若干変更されてい Q# ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-183">Argument names defined in `camelCase` are slightly altered by the compiler to be accepted as Q# inputs.</span></span> <span data-ttu-id="2808b-184">たとえば、の代わりに上記の名前を使用した場合、この入力はでは `n` `numQubits` なく、コマンドラインで指定され `--num-qubits 4` `-n 4` ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-184">For example, if instead of `n`, we used the name `numQubits` above, then this input would be provided in the command line via `--num-qubits 4` instead of `-n 4`.</span></span>

<span data-ttu-id="2808b-185">このエラーメッセージには、ターゲットコンピューターの変更方法など、使用できるその他のオプションも表示されます。</span><span class="sxs-lookup"><span data-stu-id="2808b-185">The error message also provides other options which can be used, including how to change the target machine.</span></span>

### <a name="different-target-machines"></a><span data-ttu-id="2808b-186">異なるターゲットコンピューター</span><span class="sxs-lookup"><span data-stu-id="2808b-186">Different target machines</span></span>

<span data-ttu-id="2808b-187">これまでの操作からの出力が実際の qubits でのアクションの予想される結果であるため、コマンドラインからの既定のターゲットコンピューターが完全な状態の quauntum シミュレーターであることは明らかです `QuantumSimulator` 。</span><span class="sxs-lookup"><span data-stu-id="2808b-187">As the outputs from our operations thus far have been the expected results of their action on real qubits, it's clear that the default target machine from the command line is the full-state quauntum simulator, `QuantumSimulator`.</span></span>
<span data-ttu-id="2808b-188">ただし、オプション `--simulator` (または短縮形) を使用して、特定のターゲットコンピューターで実行するように指定することもでき `-s` ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-188">However, we can instruct callables to be run on a specific target machine with the option `--simulator` (or the shorthand `-s`).</span></span>

<span data-ttu-id="2808b-189">たとえば、次のように実行でき [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-189">For example, we could run it on [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator):</span></span>

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

<span data-ttu-id="2808b-190">印刷出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2808b-190">The printed output is then</span></span>

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

<span data-ttu-id="2808b-191">これらのメトリックが示す内容の詳細については、「[リソースの推定機能: 報告](xref:microsoft.quantum.machines.resources-estimator#metrics-reported)されるメトリック」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2808b-191">For details on what these metrics indicate, see [Resource estimator: metrics reported](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).</span></span>

### <a name="command-line-execution-summary"></a><span data-ttu-id="2808b-192">コマンドライン実行の概要</span><span class="sxs-lookup"><span data-stu-id="2808b-192">Command line execution summary</span></span>
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-no-locq-dotnet-run-options"></a><span data-ttu-id="2808b-193">オプション以外 Q# `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="2808b-193">Non-Q# `dotnet run` options</span></span>

<span data-ttu-id="2808b-194">前述のようにオプションを使用 `--project` すると、 [ `dotnet run` コマンド](https://docs.microsoft.com/dotnet/core/tools/dotnet-run)は呼び出し可能な引数とは無関係のオプションも受け入れ Q# ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-194">As we briefly mentioned above with the `--project` option, the [`dotnet run` command](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) also accepts options unrelated to the Q# callable arguments.</span></span>
<span data-ttu-id="2808b-195">両方の種類のオプションを指定する場合は、固有のオプションを指定し、その後に区切り記号を指定してから、固有のオプションを `dotnet` 指定する必要があり `--` Q# ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-195">If providing both kinds of options, the `dotnet`-specific options must be provided first, followed by a delimeter `--`, and then the Q#-specific options.</span></span>
<span data-ttu-id="2808b-196">たとえば、上記の操作に対してパスと数値 qubits を指定するした場合は、を使用して実行さ `dotnet run --project <PATH> -- -n <n>` れます。</span><span class="sxs-lookup"><span data-stu-id="2808b-196">For example, specifiying a path along with a number qubits for the operation above would be executed via `dotnet run --project <PATH> -- -n <n>`.</span></span>

## <a name="no-locq-with-host-programs"></a><span data-ttu-id="2808b-197">Q#ホストプログラムを使用する</span><span class="sxs-lookup"><span data-stu-id="2808b-197">Q# with host programs</span></span>

<span data-ttu-id="2808b-198">ファイルを Q# 手に置いた場合、コマンドラインから直接操作または関数を呼び出す代わりに、別のクラシック言語で*ホストプログラム*を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="2808b-198">With our Q# file in hand, an alternative to calling an operation or function directly from the command line is to use a *host program* in another classical language.</span></span> <span data-ttu-id="2808b-199">具体的には、Python または C# や F # などの .NET 言語で行うことができます (簡潔にするために、ここでは C# についてのみ説明します)。</span><span class="sxs-lookup"><span data-stu-id="2808b-199">Specifically, this can be done with either Python or a .NET language such as C# or F# (for the sake of brevity we will only detail C# here).</span></span>
<span data-ttu-id="2808b-200">相互運用性を実現するにはもう少しセットアップが必要ですが、これらの詳細については、[インストールガイド](xref:microsoft.quantum.install)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2808b-200">A little more setup is required to enable the interoperability, but those details can be found in the [install guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="2808b-201">簡単に言うと、この状況で `*.py` は、 `*.cs` ファイルと同じ場所にホストプログラムファイル (やなど) が含まれるようになりました Q# 。</span><span class="sxs-lookup"><span data-stu-id="2808b-201">In a nutshell, the situation now includes a host program file (e.g. `*.py` or `*.cs`) in the same location as our Q# file.</span></span>
<span data-ttu-id="2808b-202">これが実行される*ホスト*プログラムになり、実行中にファイルから特定の操作と関数を呼び出すことができ Q# Q# ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-202">It's now the *host* program that gets run, and in the course of its execution it can call specific Q# operations and functions from the Q# file.</span></span>
<span data-ttu-id="2808b-203">相互運用性の中核となるのは、コンパイラを使用して、 Q# ファイルの内容を Q# ホストプログラムからアクセスできるようにし、それらを呼び出すことができるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="2808b-203">The core of the interoperability is based on the Q# compiler making the contents of the Q# file accessible to the host program so that they can be called.</span></span>

<span data-ttu-id="2808b-204">ホストプログラムを使用する主な利点の1つは、プログラムによって返される古典的なデータを Q# ホスト言語でさらに処理できることです。</span><span class="sxs-lookup"><span data-stu-id="2808b-204">One of the main benefits of using a host program is that the classical data returned by the Q# program can then be further processed in the host language.</span></span>
<span data-ttu-id="2808b-205">これには、一部の高度なデータ処理 (で内部で実行できないものなど) があり Q# 、その結果に基づいてさらにアクションを呼び出すことができ Q# ます。また、結果をプロットするのと同じように簡単です。 Q#</span><span class="sxs-lookup"><span data-stu-id="2808b-205">This could consist of some advanced data processing (e.g. something that can't be performed internally in Q#), and then calling further Q# actions based on those results, or something as simple as plotting the Q# results.</span></span>

<span data-ttu-id="2808b-206">一般的なスキームを次に示します。以下では、Python と C# の特定の実装について説明します。</span><span class="sxs-lookup"><span data-stu-id="2808b-206">The general scheme is shown here, and we discuss the specific implementations for Python and C# below.</span></span> <span data-ttu-id="2808b-207">F # ホストプログラムを使用するサンプルについては、 [.net 相互運用性のサンプル](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2808b-207">A sample using an F# host program can be found at the [.NET interoperability samples](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span></span>

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> <span data-ttu-id="2808b-208">`@EntryPoint()`コマンドラインアプリケーションに使用される属性は、 Q# ホストプログラムでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="2808b-208">The `@EntryPoint()` attribute used for Q# command line applications cannot be used with host programs.</span></span>
> <span data-ttu-id="2808b-209">Q#ホストによって呼び出されているファイルにエラーがある場合は、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="2808b-209">An error will be raised if it is present in the Q# file being called by a host.</span></span> 

<span data-ttu-id="2808b-210">別のホストプログラムを使用する場合は、ファイルに対する変更は必要ありません `*.qs` Q# 。</span><span class="sxs-lookup"><span data-stu-id="2808b-210">To work with different host programs, there are no changes required to a `*.qs` Q# file.</span></span>
<span data-ttu-id="2808b-211">次のホストプログラムの実装はすべて、同じファイルで動作し Q# ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-211">The following host program implementations all work with the same Q# file:</span></span>

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

<span data-ttu-id="2808b-212">目的のホスト言語に対応するタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="2808b-212">Select the tab corresponding to your host language of interest.</span></span>

### <a name="python"></a>[<span data-ttu-id="2808b-213">Python</span><span class="sxs-lookup"><span data-stu-id="2808b-213">Python</span></span>](#tab/tabid-python)
<span data-ttu-id="2808b-214">Python ホストプログラムは次のように構成されます。</span><span class="sxs-lookup"><span data-stu-id="2808b-214">A Python host program is constructed as follows:</span></span>
1. <span data-ttu-id="2808b-215">モジュールをインポートし `qsharp` ます。これにより、モジュールローダーが相互運用性のために登録され Q# ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-215">Import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="2808b-216">これ Q# により、名前空間を Python モジュールとして表示できるようになります。そこから、"インポート" 呼び出しを実行でき Q# ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-216">This allows Q# namespaces to appear as Python modules, from which we can "import" Q# callables.</span></span>
    <span data-ttu-id="2808b-217">これは技術的には呼び出し可能なものではなく Q# 、インポートされる Python スタブであり、それを呼び出すことができることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2808b-217">Note that it is technically not the Q# callables themselves which are imported, but rather Python stubs which allow calling into them.</span></span>
    <span data-ttu-id="2808b-218">これらは Python クラスのオブジェクトとして動作します。この場合、メソッドを使用して、操作を実行する対象のコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="2808b-218">These then behave as objects of Python classes, on which we use methods to specify the target machines to send the operation to for execution.</span></span>

2. <span data-ttu-id="2808b-219">そのような呼び出しをインポート Q# します。ここでは、を直接呼び出します。この場合、 `MeasureSuperposition` と--- `MeasureSuperpositionArray` ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-219">Import those Q# callables which we will directly invoke---in this case, `MeasureSuperposition` and `MeasureSuperpositionArray`.</span></span>
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    <span data-ttu-id="2808b-220">モジュールをインポートした場合は、 `qsharp` ライブラリの名前空間から直接 callables 実行可能ファイルをインポートすることもでき Q# ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-220">With the `qsharp` module imported, you can also import callables directly from the Q# library namespaces.</span></span>

3. <span data-ttu-id="2808b-221">その他の Python コードでは、特定のターゲットコンピューターでそれらの呼び出しを呼び出すことができるようになりました。さらに使用するために、その戻り値を変数に代入します (値を返す場合)。</span><span class="sxs-lookup"><span data-stu-id="2808b-221">Among any other Python code, you can now call those callables on specific target machines, and assign their returns to variables (if they return a value) for further use.</span></span>

#### <a name="specifying-target-machines"></a><span data-ttu-id="2808b-222">ターゲットコンピューターの指定</span><span class="sxs-lookup"><span data-stu-id="2808b-222">Specifying target machines</span></span>
<span data-ttu-id="2808b-223">特定のターゲットコンピューターで実行される操作の呼び出しは、インポートされたオブジェクトのさまざまな Python メソッドを使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="2808b-223">Calling an operation to be run on a specific target machine is done via different Python methods on the imported object.</span></span>
<span data-ttu-id="2808b-224">たとえば、は、を使用して `.simulate(<args>)` 操作を実行しますが、ではを使用 `QuantumSimulator` `.estimate_resources(<args>)` `ResourcesEstimator` します。</span><span class="sxs-lookup"><span data-stu-id="2808b-224">For example, `.simulate(<args>)`, uses the `QuantumSimulator` to run the operation, whereas `.estimate_resources(<args>)` does so on the `ResourcesEstimator`.</span></span>

#### <a name="passing-inputs-to-q"></a><span data-ttu-id="2808b-225">入力を Q に渡す\#</span><span class="sxs-lookup"><span data-stu-id="2808b-225">Passing inputs to Q\#</span></span>
<span data-ttu-id="2808b-226">呼び出し可能な引数は、キーワード Q# 引数の形式で指定する必要があります。キーワードは呼び出し可能な定義の引数名です Q# 。</span><span class="sxs-lookup"><span data-stu-id="2808b-226">Arguments for the Q# callable should be provided in the form of a keyword argument, where the keyword is the argument name in the Q# callable definition.</span></span>
<span data-ttu-id="2808b-227">つまり、は有効ですが、では `MeasureSuperpositionArray.simulate(n=4)` エラーがスローされ `MeasureSuperpositionArray.simulate(4)` ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-227">That is, `MeasureSuperpositionArray.simulate(n=4)` is valid, whereas `MeasureSuperpositionArray.simulate(4)` would throw an error.</span></span>

<span data-ttu-id="2808b-228">そのため、Python ホストプログラム</span><span class="sxs-lookup"><span data-stu-id="2808b-228">Therefore, the Python host program</span></span> 

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

<span data-ttu-id="2808b-229">次のような結果が出力されます。</span><span class="sxs-lookup"><span data-stu-id="2808b-229">results in an output like the following:</span></span>

```python
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

### <a name="c"></a>[<span data-ttu-id="2808b-230">C#</span><span class="sxs-lookup"><span data-stu-id="2808b-230">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="2808b-231">C# ホストプログラムには複数のコンポーネントがあり、QDK の一部のコンポーネントと密接に連携しています。たとえば、シミュレーターは、それ自体が C# 上に構築されています。</span><span class="sxs-lookup"><span data-stu-id="2808b-231">A C# host program has multiple components, and works very closely with some components of the QDK, such as the simulators, which are themselves built on C#.</span></span>

<span data-ttu-id="2808b-232">ここでは、 Q# ファイルの名前空間から同等の名前付き C# 名前空間を生成することによって、コンパイラが動作し Q# Q# ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-232">The Q# compiler works here by generating an equivalently named C# namespace from the Q# namespace in our Q# file.</span></span>
<span data-ttu-id="2808b-233">さらに、呼び出しが許容される型またはその中に定義された型ごとに、同等の名前付き C# クラスを生成 Q# します。</span><span class="sxs-lookup"><span data-stu-id="2808b-233">It further generates an equivalently named C# class for each of the Q# callables or types defined therein.</span></span>

<span data-ttu-id="2808b-234">まず、ホストプログラムで使用されるすべてのクラスをステートメントで使用できるようにし `using` ます。これは、 `open` ファイル内のステートメントに対しておおよその順序で実行され Q# ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-234">First, we make any classes used in our host program available with `using` statements, which are roughly analagous to the `open` statements in our Q# file:</span></span>

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (e.g. QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

<span data-ttu-id="2808b-235">次に、C# の名前空間、他のいくつかのビットと部分 (次の完全なコードブロックを参照) と、必要なすべてのクラシックプログラミング (呼び出しが許容されるように引数を計算するなど) を宣言し Q# ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-235">Next, we declare our C# namespace, a few other bits and pieces (see the full code block below), and then any classical programming we would like (e.g. computing arguments for the Q# callables).</span></span>
<span data-ttu-id="2808b-236">この場合、後者は必要ありませんが、このような使用例については、 [.net 相互運用性のサンプル](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2808b-236">The latter isn't necessary in our case, but an example of such usage can be found at the  [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).</span></span>

#### <a name="target-machines"></a><span data-ttu-id="2808b-237">ターゲット コンピューター</span><span class="sxs-lookup"><span data-stu-id="2808b-237">Target machines</span></span>

<span data-ttu-id="2808b-238">に戻るには Q# 、操作を実行する対象コンピューターのインスタンスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2808b-238">Getting back to Q#, we must create an instance of whatever target machine we will execute our operations on.</span></span>

```csharp
            using var sim = new QuantumSimulator();
```

<span data-ttu-id="2808b-239">他のターゲットマシンの使用は、別のターゲットコンピューターをインスタンス化するのと同じように簡単ですが、それを行う方法と戻り値を処理する方法は若干異なります。</span><span class="sxs-lookup"><span data-stu-id="2808b-239">Using other target machines is as simple as instantiating a different one, although the manner of doing so and processing the returns can be slightly different.</span></span>
<span data-ttu-id="2808b-240">簡潔にするために、ここではについて説明 [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) し、次のものを含め [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator)ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-240">For brevity, we stick to the [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) for now, and include the [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).</span></span>

<span data-ttu-id="2808b-241">操作から生成された各 C# クラスには Q# メソッドがあり `Run` 、その最初の引数はターゲットコンピューターインスタンスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2808b-241">Each C# class generated from the Q# operations have a `Run` method, the first argument of which must be the target machine instance.</span></span>
<span data-ttu-id="2808b-242">そのため、でを実行するには、を `MeasureSuperposition` `QuantumSimulator` 使用 `MeasureSuperposition.Run(sim)` します。</span><span class="sxs-lookup"><span data-stu-id="2808b-242">So, to run `MeasureSuperposition` on the `QuantumSimulator`, we use `MeasureSuperposition.Run(sim)`.</span></span>
<span data-ttu-id="2808b-243">返された結果は、C# の変数に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2808b-243">The returned results can then be assigned to variables in C#:</span></span>

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> <span data-ttu-id="2808b-244">`Run`このメソッドは、実際のクォンタムハードウェアの場合に発生するため、非同期的に実行されます。したがって、 `await` キーワードはタスクが完了するまでさらに実行をブロックします。</span><span class="sxs-lookup"><span data-stu-id="2808b-244">The `Run` method is executed asynchronously because this will be the case for real quantum hardware, and therefore the `await` keyword blocks further execution until the task completes.</span></span>

<span data-ttu-id="2808b-245">呼び出し可能 Q# なが戻り値の型を持っていない場合でも、 `Unit` 変数に代入せずに同じ方法で実行を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2808b-245">If the Q# callable does not have any returns (i.e. has return type `Unit`), then the execution can still be done in the same manner without assigning it to a variable.</span></span>
<span data-ttu-id="2808b-246">その場合、行全体は単に</span><span class="sxs-lookup"><span data-stu-id="2808b-246">In that case, the entire line would simply consist of</span></span> 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a><span data-ttu-id="2808b-247">引数</span><span class="sxs-lookup"><span data-stu-id="2808b-247">Arguments</span></span>

<span data-ttu-id="2808b-248">呼び出し可能な引数 Q# は、ターゲットコンピューターに追加の引数として渡されるだけです。</span><span class="sxs-lookup"><span data-stu-id="2808b-248">Any arguments to the Q# callable are simply passed as additional arguments afer the target machine.</span></span>
<span data-ttu-id="2808b-249">したがって、qubits での結果は、を使用してフェッチされます。 `MeasureSuperpositionArray` `n=4`</span><span class="sxs-lookup"><span data-stu-id="2808b-249">Hence the results of `MeasureSuperpositionArray` on `n=4` qubits would fetched via</span></span> 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

<span data-ttu-id="2808b-250">完全な C# ホストプログラムは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2808b-250">A full C# host program could thus look like</span></span>

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

<span data-ttu-id="2808b-251">C# ファイルの位置で、「」と入力すると、コマンドラインからホストプログラムを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2808b-251">At the location of the C# file, the host program can be run from the command line by entering</span></span>
```dotnetcli
dotnet run
```
<span data-ttu-id="2808b-252">この場合、次のような出力がコンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="2808b-252">and in this case you will see output written to the console similar to</span></span> 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> <span data-ttu-id="2808b-253">コンパイラの名前空間との相互運用性により、 Q# ステートメントを使用せずに呼び出し可能にすることができ `using NamespaceName;` ます。また、C# の名前空間のタイトルと単純に一致させることもできます。</span><span class="sxs-lookup"><span data-stu-id="2808b-253">Due to the compiler's interoperability with namespaces, we could alternatively make our Q# callables available without the `using NamespaceName;` statement, and simply matching the C# namespace title to it.</span></span>
> <span data-ttu-id="2808b-254">つまり、をに置き換え `namespace host` `namespace NamespaceName` ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-254">That is, by replacing `namespace host` with `namespace NamespaceName`.</span></span>

#### <a name="including-the-resources-estimator"></a><span data-ttu-id="2808b-255">リソースの推定機能を含む</span><span class="sxs-lookup"><span data-stu-id="2808b-255">Including the resources estimator</span></span>

<span data-ttu-id="2808b-256">では、 [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) 出力を取得するために若干異なる実装が必要です。</span><span class="sxs-lookup"><span data-stu-id="2808b-256">The [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) requires a slightly different implementation to retrieve the output.</span></span>

<span data-ttu-id="2808b-257">まず、ステートメントを使用して変数としてインスタンス化する代わりに、を使用して `using` `QuantumSimulator` クラスのオブジェクトを直接インスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="2808b-257">Firstly, instead of instantiating them as a variable with a `using` statement (as we do with the `QuantumSimulator`), we more directly instantiate objects of the class via</span></span>

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

<span data-ttu-id="2808b-258">複数の操作で1つのターゲットシミュレーターが使用されるのではなく Q# 、それぞれに対して1つのターゲットシミュレーターがインスタンス化されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2808b-258">Notice that instead of a single target simulator to be used by multiple Q# operations, we have instantiated one for each.</span></span> <span data-ttu-id="2808b-259">これは、ターゲットコンピューターとして使用されたときにオブジェクト自体が変更され、その結果をクラスメソッドで後から取得できるためです `.ToTSV()` 。</span><span class="sxs-lookup"><span data-stu-id="2808b-259">This is because the objects themselves are modified when used as target machines, and their results can then be retrieved afterwards with the class method `.ToTSV()`.</span></span>

<span data-ttu-id="2808b-260">リソース estimators に対して操作を実行するには、次を使用します。</span><span class="sxs-lookup"><span data-stu-id="2808b-260">To run the operations on the resource estimators, we use</span></span>

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
<span data-ttu-id="2808b-261">次に、とを使用して、結果をタブ区切り値 (TSV) としてフェッチし `estimatorSingleQ.ToTSV()` `estimatorMultiQ.ToTSV()` ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-261">and then fetch the results as tab-separated-values (TSV) with `estimatorSingleQ.ToTSV()` and `estimatorMultiQ.ToTSV()`.</span></span>

<span data-ttu-id="2808b-262">したがって、との両方を使用する完全な C# ホストプログラムは、次のような `QuantumSimulator` `ResourcesEstimator` 形式になります。</span><span class="sxs-lookup"><span data-stu-id="2808b-262">So, a full C# host program making use of both the `QuantumSimulator` and `ResourcesEstimator` could take the form:</span></span>

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


<span data-ttu-id="2808b-263">これにより、のような出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="2808b-263">which would yield output similar to</span></span>

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

## <a name="no-locq-jupyter-notebooks"></a><span data-ttu-id="2808b-264">Q#Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="2808b-264">Q# Jupyter Notebooks</span></span>
<span data-ttu-id="2808b-265">Q#Jupyter Notebook では、I カーネルを使用します Q# 。これにより、 Q# すべての命令、メモ、およびその他のコンテンツと共に、呼び出し可能なを1つのノートブックで定義、コンパイル、および実行することが---ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-265">Q# Jupyter Notebooks make use of the IQ# kernel, which allows you to define, compile, and run Q# callables in a single notebook---all alongside instructions, notes, and other content.</span></span>
<span data-ttu-id="2808b-266">つまり、ファイルの内容をインポートして使用することはできますが、 `*.qs` Q# 実行モデルでは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="2808b-266">This means that while it is possible to import and use the contents of `*.qs` Q# files, they are not necessary in the execution model.</span></span>

<span data-ttu-id="2808b-267">ここでは、上で定義した操作を実行する方法について詳しく説明します Q# が、jupyter notebook の使用方法の概要については、「 Q# 概要」と「 [ Q# jupyter notebook](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2808b-267">Here, we will detail how to run the Q# operations defined above, but a more broad introduction to using Q# Jupyter Notebooks is provided at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).</span></span>

### <a name="defining-operations"></a><span data-ttu-id="2808b-268">定義 (操作を)</span><span class="sxs-lookup"><span data-stu-id="2808b-268">Defining operations</span></span>

<span data-ttu-id="2808b-269">Jupyter Notebook では Q# 、 Q# ファイルの名前空間内と同様にコードを入力し Q# ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-269">In a Q# Jupyter Notebook, you enter Q# code just as we would from inside the namespace of a Q# file.</span></span>

<span data-ttu-id="2808b-270">そのため、 [ Q# 標準ライブラリ](xref:microsoft.quantum.qsharplibintro)から、 `open` それぞれの名前空間のステートメントを使用して、呼び出し可能なアクセスを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2808b-270">So, we can enable access to callables from the [Q# standard libraries](xref:microsoft.quantum.qsharplibintro) with `open` statements for their respective namespaces.</span></span>
<span data-ttu-id="2808b-271">このようなステートメントでセルを実行すると、その名前空間の定義がワークスペース全体で使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2808b-271">Upon running a cell with such a statement, the definitions from those namespaces are available throughout the workspace.</span></span>

> [!NOTE]
> <span data-ttu-id="2808b-272">[Microsoft の quantum](xref:microsoft.quantum.intrinsic)および[microsoft の quantum](xref:microsoft.quantum.canon) (やなど) からの呼び出し [`H`](xref:microsoft.quantum.intrinsic.h) は、 [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) jupyter notebook のセル内で定義されている操作で自動的に使用できるようになります。 Q#</span><span class="sxs-lookup"><span data-stu-id="2808b-272">Callables from [Microsoft.Quantum.Intrinsic](xref:microsoft.quantum.intrinsic) and [Microsoft.Quantum.Canon](xref:microsoft.quantum.canon) (e.g. [`H`](xref:microsoft.quantum.intrinsic.h) and [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach)) are automatically available to operations defined within cells in Q# Jupyter Notebooks.</span></span>
> <span data-ttu-id="2808b-273">ただし、外部ソースファイルからのコードには当てはまりません Q# ([概要 Q# と Jupyter notebook](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)に示されているプロセス)。</span><span class="sxs-lookup"><span data-stu-id="2808b-273">However, this is not true for code brought in from external Q# source files (a process shown at [Intro to Q# and Jupyter Notebooks](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)).</span></span> 
> 

<span data-ttu-id="2808b-274">同様に、操作を定義するには、コードの記述 Q# とセルの実行のみが必要です。</span><span class="sxs-lookup"><span data-stu-id="2808b-274">Similarly, defining operations requires only writing the Q# code and running the cell.</span></span>

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="600">

<span data-ttu-id="2808b-275">出力には、これらの操作が一覧表示されます。これらの操作は、今後のセルから呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="2808b-275">The output then lists those operations, which can then be called from future cells.</span></span>

### <a name="target-machines"></a><span data-ttu-id="2808b-276">ターゲット コンピューター</span><span class="sxs-lookup"><span data-stu-id="2808b-276">Target machines</span></span>

<span data-ttu-id="2808b-277">特定の対象コンピューターで操作を実行する機能は、 [I Q# マジックコマンド](xref:microsoft.quantum.guide.quickref.iqsharp)を使用して提供されます。</span><span class="sxs-lookup"><span data-stu-id="2808b-277">The functionality to run operations on specific target machines is provided via [IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp).</span></span>
<span data-ttu-id="2808b-278">たとえば、はを使用し、を使用し `%simulate` `QuantumSimulator` `%estimate` `ResourcesEstimator` ます。</span><span class="sxs-lookup"><span data-stu-id="2808b-278">For example, `%simulate` makes use of the `QuantumSimulator`, and `%estimate` uses the `ResourcesEstimator`:</span></span>

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Simulate and estimate resources Jupyter cell" width="500">

### <a name="passing-inputs-to-functions-and-operations"></a><span data-ttu-id="2808b-279">関数および操作への入力の引き渡し</span><span class="sxs-lookup"><span data-stu-id="2808b-279">Passing inputs to functions and operations</span></span>

<span data-ttu-id="2808b-280">現在、実行マジックコマンドは、引数を受け取らない操作でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2808b-280">Currently the execution magic commands can only be used with operations that take no arguments.</span></span> <span data-ttu-id="2808b-281">そのため、を実行するには、次に引数を指定し `MeasureSuperpositionArray` て操作を呼び出す "ラッパー" 操作を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2808b-281">So, to run `MeasureSuperpositionArray`, we need to define a "wrapper" operation which then calls the operation with the arguments:</span></span>

<img src="../media/hostprograms_jupyter_wrapper_def_sim_crop.png" alt="Wrapper function and simulate Jupyter cell" width="550">

<span data-ttu-id="2808b-282">この操作は `%estimate` 、やその他の実行コマンドと同様に使用できます。</span><span class="sxs-lookup"><span data-stu-id="2808b-282">This operation can of course be used similarly with `%estimate` and other execution commands.</span></span>
