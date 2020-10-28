---
title: テストとデバッグ
description: 単体テスト、ファクトとアサーション、およびダンプ関数を使用して、クォンタムプログラムをテストおよびデバッグする方法について説明します。
author: tcNickolas
ms.author: mamykhai
ms.date: 06/01/2020
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 5505086c5efac89f6940cde1ecae2ce629cfeda5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690975"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="f6e00-103">テストとデバッグ</span><span class="sxs-lookup"><span data-stu-id="f6e00-103">Testing and debugging</span></span>

<span data-ttu-id="f6e00-104">従来のプログラミングと同様に、クォンタムプログラムが意図したとおりに動作することを確認し、正しくない動作を診断できるようにすることが不可欠です。</span><span class="sxs-lookup"><span data-stu-id="f6e00-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose incorrect behavior.</span></span>
<span data-ttu-id="f6e00-105">このセクションでは、 :::no-loc(Q#)::: クォンタムプログラムをテストおよびデバッグするためにに用意されているツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f6e00-105">In this section, we cover the tools offered by :::no-loc(Q#)::: for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="f6e00-106">単体テスト</span><span class="sxs-lookup"><span data-stu-id="f6e00-106">Unit Tests</span></span>

<span data-ttu-id="f6e00-107">従来のプログラムをテストする一般的な方法の1つは、 *単体テスト* と呼ばれる小さなプログラムを作成することです。これにより、ライブラリでコードを実行し、出力を予想される出力と比較します。</span><span class="sxs-lookup"><span data-stu-id="f6e00-107">One common approach to testing classical programs is to write small programs called *unit tests* , which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="f6e00-108">たとえば、 `Square(2)` `4` $ 2 ^ 2 = $4 の *priori* がわかっているため、がを返すようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-108">For example, you can ensure that `Square(2)` returns `4` since you know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="f6e00-109">:::no-loc(Q#)::: は、クォンタムプログラムの単体テストの作成をサポートしています。これは、 [Xunit](https://xunit.github.io/) 単体テストフレームワーク内でテストとして実行できます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-109">:::no-loc(Q#)::: supports creating unit tests for quantum programs, and which can run as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="f6e00-110">テストプロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="f6e00-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="f6e00-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f6e00-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="f6e00-112">Visual Studio 2019 を開きます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="f6e00-113">[ **ファイル** ] メニューにアクセスし、[ **新しい > プロジェクト** ] を選択します。右上隅にあるを検索し、 `:::no-loc(Q#):::` **:::no-loc(Q#)::: テストプロジェクト** テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="f6e00-113">Go to the **File** menu and select **New > Project...** . In the upper right corner, search for `:::no-loc(Q#):::`, and select the **:::no-loc(Q#)::: Test Project** template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="f6e00-114">コマンドライン/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f6e00-114">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="f6e00-115">お気に入りのコマンドラインから、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f6e00-115">From your favorite command line, run the following command:</span></span>
```dotnetcli
$ dotnet new xunit -lang :::no-loc(Q#)::: -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="f6e00-116">新しいプロジェクトには `Tests.qs` 、新しい単体テストを定義するための便利な場所を提供する1つのファイルがあり :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-116">Your new project has a single file `Tests.qs`, which provides a convenient place to define new :::no-loc(Q#)::: unit tests.</span></span>
<span data-ttu-id="f6e00-117">初期状態では、このファイルに `AllocateQubit` は、新しく割り当てられた qubit が $ \ket $ 状態であることを確認し、メッセージを出力するサンプル単体テストが1つ含まれてい {0} ます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-117">Initially, this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            AssertMeasurement([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="f6e00-118">:::no-loc(Q#):::型の引数を受け取り、を返すすべての操作または関数は `Unit` `Unit` 、属性を使用して単体テストとしてマークでき `@Test("...")` ます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-118">Any :::no-loc(Q#)::: operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="f6e00-119">前の例では、その属性の引数が、 `"QuantumSimulator"` テストを実行するターゲットを指定しています。</span><span class="sxs-lookup"><span data-stu-id="f6e00-119">In the previous example, the argument to that attribute, `"QuantumSimulator"`, specifies the target on which the test runs.</span></span> <span data-ttu-id="f6e00-120">1つのテストを複数のターゲットで実行できます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-120">A single test can run on multiple targets.</span></span> <span data-ttu-id="f6e00-121">たとえば、の前に属性を追加し `@Test("ResourcesEstimator")` `AllocateQubit` ます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-121">For example, add an attribute `@Test("ResourcesEstimator")` before `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="f6e00-122">ファイルを保存し、すべてのテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f6e00-122">Save the file and run all tests.</span></span> <span data-ttu-id="f6e00-123">ここで、2つの単体テストがあります。1つはで実行され、もう1つは `AllocateQubit` `QuantumSimulator` で実行さ `ResourcesEstimator` れます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-123">There should now be two unit tests, one where `AllocateQubit` runs on the `QuantumSimulator`, and one where it runs in the `ResourcesEstimator`.</span></span> 

<span data-ttu-id="f6e00-124">コンパイラは、 :::no-loc(Q#)::: 組み込みのターゲット、、を、 `"QuantumSimulator"` `"ToffoliSimulator"` `"ResourcesEstimator"` 単体テストの有効な実行ターゲットとして認識します。</span><span class="sxs-lookup"><span data-stu-id="f6e00-124">The :::no-loc(Q#)::: compiler recognizes the built-in targets `"QuantumSimulator"`, `"ToffoliSimulator"`, and `"ResourcesEstimator"` as valid run targets for unit tests.</span></span> <span data-ttu-id="f6e00-125">また、任意の完全修飾名を指定して、カスタム実行ターゲットを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-125">It is also possible to specify any fully qualified name to define a custom run target.</span></span> 

### <a name="running-no-locq-unit-tests"></a><span data-ttu-id="f6e00-126">:::no-loc(Q#):::単体テストの実行</span><span class="sxs-lookup"><span data-stu-id="f6e00-126">Running :::no-loc(Q#)::: Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="f6e00-127">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f6e00-127">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="f6e00-128">ソリューションごとの1回限りの設定として、[ **テスト** ] メニューの [テストの設定] を選択し、[ **既定のプロセッサアーキテクチャ > X64 >** ます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-128">As a one-time per-solution setup, go to the **Test** menu and select **Test Settings > Default Processor Architecture > X64** .</span></span>

> [!TIP]
> <span data-ttu-id="f6e00-129">Visual Studio の既定のプロセッサアーキテクチャ設定は、各ソリューションのソリューションオプション () ファイルに格納され `.suo` ます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-129">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="f6e00-130">このファイルを削除する場合は、プロセッサアーキテクチャとして **X64** を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6e00-130">If you delete this file, then you need to select **X64** as your processor architecture again.</span></span>

<span data-ttu-id="f6e00-131">プロジェクトをビルドし、[ **テスト** ] メニューを開き、[ **Windows > テストエクスプローラー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6e00-131">Build the project, open the **Test** menu, and select **Windows > Test Explorer** .</span></span> <span data-ttu-id="f6e00-132">**Allocatequbit** は、[ **テストを実行しない** ] グループのテストの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-132">**AllocateQubit** displays in the list of tests in the **Not Run Tests** group.</span></span> <span data-ttu-id="f6e00-133">[ **すべて実行** ] を選択するか、この個々のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f6e00-133">Select **Run All** or run this individual test.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="f6e00-134">コマンドライン/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f6e00-134">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="f6e00-135">テストを実行するには、プロジェクトフォルダー (を含むフォルダー) に移動 `Tests.csproj` し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f6e00-135">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and run the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="f6e00-136">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-136">You should get output similar to the following:</span></span>

```
Build started, please wait...
Build completed.

Test run for C:\Users\chgranad.REDMOND\tmp\Tests\bin\Debug\netcoreapp2.0\Tests.dll(.NETCoreApp,Version=v2.0)
Microsoft (R) Test Execution Command Line Tool Version 15.3.0-preview-20170628-02
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.5864002]   Discovering: Tests
[xUnit.net 00:00:00.7073844]   Discovered:  Tests
[xUnit.net 00:00:00.7453826]   Starting:    Tests
[xUnit.net 00:00:00.9590439]   Finished:    Tests

Total tests: 1. Passed: 1. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.9607 Seconds
```

<span data-ttu-id="f6e00-137">単体テストは、名前または実行ターゲットに応じてフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-137">Unit tests can be filtered according to their name or the run target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


<span data-ttu-id="f6e00-138">\*\*_</span><span class="sxs-lookup"><span data-stu-id="f6e00-138">\*\*_</span></span>

<span data-ttu-id="f6e00-139">組み込み関数に <xref:Microsoft.Quantum.Intrinsic.Message> は型があり、 `(String -> Unit)` 診断メッセージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-139">The intrinsic function <xref:Microsoft.Quantum.Intrinsic.Message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="f6e00-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f6e00-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="f6e00-141">テストエクスプローラーでテストを実行し、テストをクリックすると、テストの実行に関する情報がパネルに表示されます (成功/失敗の状態、経過時間、および出力へのリンク)。</span><span class="sxs-lookup"><span data-stu-id="f6e00-141">After you run a test in Test Explorer and click on the test, a panel displays with information about test run: Pass/fail status, elapsed time, and a link to the output.</span></span> <span data-ttu-id="f6e00-142">[_ *出力* ] \* をクリックして、新しいウィンドウでテスト出力を開きます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-142">Click _ *Output* \* to open the test output in a new window.</span></span>

![テスト出力](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="f6e00-144">コマンドライン/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f6e00-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="f6e00-145">各テストの成功/失敗の状態は、によってコンソールに出力され `dotnet test` ます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="f6e00-146">失敗したテストの場合は、エラーの診断に役立つ出力もコンソールに出力されます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

<span data-ttu-id="f6e00-147">\*\*_</span><span class="sxs-lookup"><span data-stu-id="f6e00-147">\*\*_</span></span>

## <a name="facts-and-assertions"></a><span data-ttu-id="f6e00-148">ファクトとアサーション</span><span class="sxs-lookup"><span data-stu-id="f6e00-148">Facts and Assertions</span></span>

<span data-ttu-id="f6e00-149">の関数には :::no-loc(Q#)::: _論理的_ な副作用がないため、プログラム内から、 :::no-loc(Q#)::: 出力の種類が空のタプルである関数の実行によって他の種類の影響が発生しないようにすることはできません `()` 。</span><span class="sxs-lookup"><span data-stu-id="f6e00-149">Because functions in :::no-loc(Q#)::: have no _logical_ side effects, you can never observe, from within a :::no-loc(Q#)::: program, any other kinds of effects from running a function whose output type is the empty tuple `()`.</span></span>
<span data-ttu-id="f6e00-150">つまり、ターゲットコンピューターは、この省略によって `()` 次のコードの動作が変更されないことを保証して、が返す関数を実行しないことを選択でき :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-150">That is, a target machine can choose not to run any function which returns `()` with the guarantee that this omission will not modify the behavior of any following :::no-loc(Q#)::: code.</span></span>
<span data-ttu-id="f6e00-151">この動作により `()` 、関数 (など `Unit` ) が、アサーションの埋め込みとプログラムへのデバッグロジックに便利なツールとして返さ :::no-loc(Q#)::: れます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-151">This behavior makes functions returning `()` (such as `Unit`) a useful tool for embedding assertions and debugging logic into :::no-loc(Q#)::: programs.</span></span> 

<span data-ttu-id="f6e00-152">単純な例を考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="f6e00-152">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="f6e00-153">ここで、キーワードは、 `fail` 計算が続行されないことを示し、プログラムを実行しているターゲットコンピューターで例外を発生させ :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-153">Here, the keyword `fail` indicates that the computation should not proceed, and raises an exception in the target machine running the :::no-loc(Q#)::: program.</span></span>
<span data-ttu-id="f6e00-154">定義上、この種のエラーは、 :::no-loc(Q#)::: ターゲットコンピューターが :::no-loc(Q#)::: ステートメントに到達した後にコードを実行しなくなったため、内からは確認できません `fail` 。</span><span class="sxs-lookup"><span data-stu-id="f6e00-154">By definition, a failure of this kind cannot be observed from within :::no-loc(Q#):::, as the target machine no longer runs the :::no-loc(Q#)::: code after reaching a `fail` statement.</span></span>
<span data-ttu-id="f6e00-155">したがって、への呼び出しを実行した後にを続行すると、入力が肯定的であることが `PositivityFact` 保証されます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-155">Thus, if we proceed past a call to `PositivityFact`, we can be assured that its input was positive.</span></span>

<span data-ttu-id="f6e00-156">名前空間の関数を使用するのと同じ動作を実装できることに注意して `PositivityFact` [`Fact`](xref:Microsoft.Quantum.Diagnostics.fact) <xref:Microsoft.Quantum.Diagnostics> ください。</span><span class="sxs-lookup"><span data-stu-id="f6e00-156">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:Microsoft.Quantum.Diagnostics.fact) function from the <xref:Microsoft.Quantum.Diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="f6e00-157">一方、_Assertions \* はファクトと同様に使用されますが、ターゲットコンピューターの状態によって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f6e00-157">_Assertions\*, on the other hand, are used similarly to facts but may depend on the state of the target machine.</span></span> <span data-ttu-id="f6e00-158">それに応じて、これらは操作として定義されますが、ファクトは関数として定義されます (前の例のように)。</span><span class="sxs-lookup"><span data-stu-id="f6e00-158">Correspondingly, they are defined as operations, whereas facts are defined as functions (as in the previous example).</span></span>
<span data-ttu-id="f6e00-159">この違いを理解するには、アサーション内で次のファクトを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="f6e00-159">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="f6e00-160">ここでは、操作を使用して、 <xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse> 使用可能な qubits の数を返します。</span><span class="sxs-lookup"><span data-stu-id="f6e00-160">Here, we are using the operation <xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="f6e00-161">これは、プログラムとその実行環境のグローバルな状態によって異なりますが、の定義 `AssertQubitsAreAvailable` も操作である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6e00-161">As this depends on the global state of the program and its run environment, our definition of `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="f6e00-162">ただし、そのグローバル状態を使用し `Bool` て、関数への入力として単純な値を生成することができ `Fact` ます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-162">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="f6e00-163">これらのアイデアを基にして構築さ[れた準備は](xref:microsoft.quantum.libraries.standard.prelude)、2つの便利なアサーションを提供 <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> し、 <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> 両方とも操作としてモデル化されて `()` います。</span><span class="sxs-lookup"><span data-stu-id="f6e00-163">[The prelude](xref:microsoft.quantum.libraries.standard.prelude), building on these ideas, offers two especially useful assertions, <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> and <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> both modeled as operations onto `()`.</span></span> <span data-ttu-id="f6e00-164">これらのアサーションは、特定の対象測定、測定が実行されるクォンタムレジスタ、および仮定の結果を記述する P# li オペレーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f6e00-164">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="f6e00-165">シミュレーションによって動作するターゲットコンピューターは、 [複製なしの定理](https://en.wikipedia.org/wiki/No-cloning_theorem)によってバインドされないため、このようなアサーションに合格するレジスタに支障をきたすことなく、このような測定を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-165">Target machines which work by simulation are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register that passes to such assertions.</span></span>
<span data-ttu-id="f6e00-166">次に、シミュレーターは、前の関数と同様に、 `PositivityFact` 仮定の結果が実際に観測されていない場合に計算を停止できます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-166">A simulator can then, similar to the `PositivityFact` function previous, stop computation if the hypothetical outcome is not observed in practice:</span></span>

```qsharp
using (register = Qubit()) 
{
    H(register);
    AssertMeasurement([PauliX], [register], Zero);
    // Even though we do not have access to states in :::no-loc(Q#):::,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

<span data-ttu-id="f6e00-167">物理クォンタムハードウェアでは、複製なしの定理がクォンタムの状態を検査できない場合 `AssertMeasurement` 、 `AssertMeasurementProbability` 操作と操作は単 `()` に他の効果なしでを返します。</span><span class="sxs-lookup"><span data-stu-id="f6e00-167">On physical quantum hardware, where the no-cloning theorem prevents examination of a quantum state, the `AssertMeasurement` and `AssertMeasurementProbability` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="f6e00-168">名前空間には、 <xref:Microsoft.Quantum.Diagnostics> `Assert` さらに高度な条件を確認できるファミリの機能がいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="f6e00-168">The <xref:Microsoft.Quantum.Diagnostics> namespace provides several more functions of the `Assert` family, with which you can check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="f6e00-169">ダンプ関数</span><span class="sxs-lookup"><span data-stu-id="f6e00-169">Dump Functions</span></span>

<span data-ttu-id="f6e00-170">クォンタムプログラムのトラブルシューティングに役立つように、名前空間には、 <xref:Microsoft.Quantum.Diagnostics> ターゲットコンピューターの現在の状態をファイルにダンプできる2つの関数 (および) が用意されて <xref:Microsoft.Quantum.Diagnostics.DumpMachine> <xref:Microsoft.Quantum.Diagnostics.DumpRegister> います。</span><span class="sxs-lookup"><span data-stu-id="f6e00-170">To help troubleshooting quantum programs, the <xref:Microsoft.Quantum.Diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:Microsoft.Quantum.Diagnostics.DumpMachine> and <xref:Microsoft.Quantum.Diagnostics.DumpRegister>.</span></span> <span data-ttu-id="f6e00-171">それぞれのの生成された出力は、ターゲットコンピューターによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f6e00-171">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="f6e00-172">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="f6e00-172">DumpMachine</span></span>

<span data-ttu-id="f6e00-173">Quantum 開発キットの一部として配布された完全な状態のクォンタムシミュレーターは、クォンタムシステム全体の [wave 関数](https://en.wikipedia.org/wiki/Wave_function) を、1次元の複素数の配列としてファイルに書き込みます。各要素は、コンピューティングベースの状態を測定する確率の振幅 ($ \ket{n} = \ket{b_ {n-1}...) を表します。b_1b_0} $ (bits $ \{ b_i $ の場合) \} 。</span><span class="sxs-lookup"><span data-stu-id="f6e00-173">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="f6e00-174">たとえば、2つの qubits のみが割り当てられ、クォンタム状態が $ $ \begin{align} \ket{\psi} = \ frac {1} {\ sqrt {2} } \ket {00} -\frac{(1 + i)} \ket であるコンピューターでは、 {2} {10} \end{align} $ $ を呼び出すと、次の出力が生成され <xref:Microsoft.Quantum.Diagnostics.DumpMachine> ます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-174">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:Microsoft.Quantum.Diagnostics.DumpMachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="f6e00-175">最初の行は、対応する qubits の id を持つコメントを有意な順序で提供します。</span><span class="sxs-lookup"><span data-stu-id="f6e00-175">The first row provides a comment with the ids of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="f6e00-176">残りの行は、デカルト形式と極座標形式の両方で、basis 状態ベクター $ \ket{n} $ を測定する確率の振幅を示しています。</span><span class="sxs-lookup"><span data-stu-id="f6e00-176">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="f6e00-177">最初の行の詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f6e00-177">In detail for the first row:</span></span>

* <span data-ttu-id="f6e00-178">**`∣0❭:`** この行は、計算基礎の状態に対応します。 `0`</span><span class="sxs-lookup"><span data-stu-id="f6e00-178">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="f6e00-179">**`0.707107 +  0.000000 i`** : デカルト形式の確率の振幅。</span><span class="sxs-lookup"><span data-stu-id="f6e00-179">**`0.707107 +  0.000000 i`** : the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="f6e00-180">**` == `** : 符号は、 `equal` 両方の同等の表現を分離します。</span><span class="sxs-lookup"><span data-stu-id="f6e00-180">**` == `** : the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="f6e00-181">**`**********  `** : 大きさをグラフィカルに表示します。の数は、 `*` この状態ベクターを測定する確率に比例します。</span><span class="sxs-lookup"><span data-stu-id="f6e00-181">**`**********  `** : A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="f6e00-182">**`[ 0.500000 ]`** : マグニチュードの数値</span><span class="sxs-lookup"><span data-stu-id="f6e00-182">**`[ 0.500000 ]`** : the numeric value of the magnitude</span></span>
* <span data-ttu-id="f6e00-183">**`    ---`** : 振幅のフェーズをグラフィカルに表示します (次の出力を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="f6e00-183">**`    ---`** : A graphical representation of the amplitude's phase (see the following output).</span></span>
* <span data-ttu-id="f6e00-184">**`[ 0.0000 rad ]`** : フェーズの数値 (ラジアン)。</span><span class="sxs-lookup"><span data-stu-id="f6e00-184">**`[ 0.0000 rad ]`** : the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="f6e00-185">大きさとフェーズの両方がグラフィック表示で表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-185">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="f6e00-186">マグニチュード表現は、水平方向です。の棒が大きいほど、 `*` 棒が大きくなる確率が大きくなります。</span><span class="sxs-lookup"><span data-stu-id="f6e00-186">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="f6e00-187">フェーズでは、次の記号を使用して範囲に基づく角度を表します。</span><span class="sxs-lookup"><span data-stu-id="f6e00-187">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

```
[ -π/16,   π/16)       ---
[  π/16,  3π/16)        /-
[ 3π/16,  5π/16)        / 
[ 5π/16,  7π/16)       +/ 
[ 7π/16,  9π/16)      ↑   
[ 8π/16, 11π/16)    \-    
[ 7π/16, 13π/16)    \     
[ 7π/16, 15π/16)   +\     
[15π/16, 19π/16)   ---    
[17π/16, 19π/16)   -/     
[19π/16, 21π/16)    /     
[21π/16, 23π/16)    /+    
[23π/16, 25π/16)      ↓   
[25π/16, 27π/16)       -\ 
[27π/16, 29π/16)        \ 
[29π/16, 31π/16)        \+
[31π/16,   π/16)       ---
```

<span data-ttu-id="f6e00-188">次の例は、 `DumpMachine` いくつかの一般的な状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="f6e00-188">The following examples show `DumpMachine` for some common states:</span></span>

### `∣0❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

### `∣1❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣1❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
```

### `∣+❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
```

### `∣-❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:    -0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]  ---     [  3.14159 rad ]
```


  > [!NOTE]
  > <span data-ttu-id="f6e00-189">Qubit の id は実行時に割り当てられ、必ずしも qubit が割り当てられた順序、または qubit レジスタ内の位置に一致するとは限りません。</span><span class="sxs-lookup"><span data-stu-id="f6e00-189">The id of a qubit is assigned at runtime and is not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="f6e00-190">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f6e00-190">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="f6e00-191">コードにブレークポイントを配置し、qubit 変数の値を調べることで、Visual Studio で qubit id を見つけることができます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f6e00-191">You can locate a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![Visual Studio での qubit id の表示](~/media/qubit_id.png)
  >
  > <span data-ttu-id="f6e00-193">インデックスがである qubit の `0` `register2` id = `3` 、qubit with index `1` は id = `2` です。</span><span class="sxs-lookup"><span data-stu-id="f6e00-193">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="f6e00-194">コマンドライン/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f6e00-194">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="f6e00-195">関数を使用し、メッセージに qubit 変数を渡すことによって、qubit id を見つけることができ <xref:Microsoft.Quantum.Intrinsic.Message> ます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f6e00-195">You can locate a qubit id by using the <xref:Microsoft.Quantum.Intrinsic.Message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="f6e00-196">次のような出力が生成できます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-196">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="f6e00-197">これは、インデックスを持つ qubit の id がであることを意味します。これは、 `0` `register2` `3` インデックスを持つ qubit `1` が id = であることを意味し `2` ます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-197">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


<span data-ttu-id="f6e00-198">\*\*_</span><span class="sxs-lookup"><span data-stu-id="f6e00-198">\*\*_</span></span>

<span data-ttu-id="f6e00-199"><xref:Microsoft.Quantum.Diagnostics.DumpMachine>は名前空間の一部 <xref:Microsoft.Quantum.Diagnostics> であるため、 `open` それにアクセスするためのステートメントを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6e00-199">Since <xref:Microsoft.Quantum.Diagnostics.DumpMachine> is part of the  <xref:Microsoft.Quantum.Diagnostics> namespace, you must add an `open` statement to access it:</span></span>

```qsharp
namespace Samples {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {
        using (qubits = Qubit[2]) {
            H(qubits[1]);
            DumpMachine("dump.txt");
        }
    }
}
```


### <a name="dumpregister"></a><span data-ttu-id="f6e00-200">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="f6e00-200">DumpRegister</span></span>

<span data-ttu-id="f6e00-201"><xref:Microsoft.Quantum.Diagnostics.DumpRegister> はと同じように動作し <xref:Microsoft.Quantum.Diagnostics.DumpMachine> ますが、情報の量を対応する qubits に限定するために、qubits の配列も取得する点が異なります。</span><span class="sxs-lookup"><span data-stu-id="f6e00-201"><xref:Microsoft.Quantum.Diagnostics.DumpRegister> works like <xref:Microsoft.Quantum.Diagnostics.DumpMachine>, except that it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="f6e00-202">と同様に <xref:Microsoft.Quantum.Diagnostics.DumpMachine> 、によって生成される情報は <xref:Microsoft.Quantum.Diagnostics.DumpRegister> ターゲットコンピューターによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f6e00-202">As with <xref:Microsoft.Quantum.Diagnostics.DumpMachine>, the information generated by <xref:Microsoft.Quantum.Diagnostics.DumpRegister> depends on the target machine.</span></span> <span data-ttu-id="f6e00-203">完全な状態のクォンタムシミュレーターでは、と同じ形式で指定された qubits によって生成されるクォンタムサブシステムのグローバルフェーズまで、wave 関数がファイルに書き込まれ <xref:Microsoft.Quantum.Diagnostics.DumpMachine> ます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-203">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:Microsoft.Quantum.Diagnostics.DumpMachine>.</span></span>  <span data-ttu-id="f6e00-204">たとえば、2つの qubits のみが割り当てられ、クォンタム状態が $ $ \begin{align} \ket{\psi} = \ frac {1} {\ sqrt {2} } \ket {00} -\frac{(1 + i)} \ket =-e ^ {であるマシンをもう一度実行します。 {2} {10} -i \ pi/4} ((\ frac {1} {\ sqrt {2} } \ket {0} -\frac{(1 + i)} {2} \ket {1} ) \ otimes \frac{-(1 + i)} {\ sqrt {2} } \ket {0} )、\end{align} $ $ を呼び出すと <xref:Microsoft.Quantum.Diagnostics.DumpRegister> 、次の出力が生成され `qubit[0]` ます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-204">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:Microsoft.Quantum.Diagnostics.DumpRegister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     _******************* [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="f6e00-205">とを呼び出すと、次 <xref:Microsoft.Quantum.Diagnostics.DumpRegister> の出力が生成され `qubit[1]` ます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-205">and calling <xref:Microsoft.Quantum.Diagnostics.DumpRegister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="f6e00-206">一般に、別のレジスタによって使用されるレジスタの状態は、純粋な状態ではなく混合状態になります。</span><span class="sxs-lookup"><span data-stu-id="f6e00-206">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="f6e00-207">この場合、は <xref:Microsoft.Quantum.Diagnostics.DumpRegister> 次のメッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="f6e00-207">In this case, <xref:Microsoft.Quantum.Diagnostics.DumpRegister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="f6e00-208">次の例は、 <xref:Microsoft.Quantum.Diagnostics.DumpRegister> コード内でとの両方を使用する方法を示してい <xref:Microsoft.Quantum.Diagnostics.DumpMachine> :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="f6e00-208">The following example shows you how you can use both <xref:Microsoft.Quantum.Diagnostics.DumpRegister> and <xref:Microsoft.Quantum.Diagnostics.DumpMachine> in your :::no-loc(Q#)::: code:</span></span>

```qsharp
namespace app
{
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {

        using (qubits = Qubit[2]) {
            X(qubits[1]);
            H(qubits[1]);
            R1Frac(1, 2, qubits[1]);
            
            DumpMachine("dump.txt");
            DumpRegister("q0.txt", qubits[0..0]);
            DumpRegister("q1.txt", qubits[1..1]);

            ResetAll(qubits);
        }
    }
}
```

## <a name="debugging"></a><span data-ttu-id="f6e00-209">デバッグ</span><span class="sxs-lookup"><span data-stu-id="f6e00-209">Debugging</span></span>

<span data-ttu-id="f6e00-210">`Assert`およびの `Dump` 関数と操作の上で、は、 :::no-loc(Q#)::: 標準の Visual Studio デバッグ機能のサブセットをサポートしています。[行ブレークポイントの設定](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)、 [F10 を使用したコードのステップ](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)実行、および[クラシック変数の値の検査](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)は、シミュレーターでコードを実行するときにすべて可能です。</span><span class="sxs-lookup"><span data-stu-id="f6e00-210">On top of `Assert` and `Dump` functions and operations, :::no-loc(Q#)::: supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger), and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible when running your code on the simulator.</span></span>

<span data-ttu-id="f6e00-211">Visual Studio Code でのデバッグでは、OmniSharp によって強化された Visual Studio Code 拡張機能のために C# によって提供されるデバッグ機能を利用し、 [最新バージョン](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6e00-211">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 
