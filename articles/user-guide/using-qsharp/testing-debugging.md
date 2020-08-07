---
title: テストとデバッグ
description: 単体テスト、ファクトとアサーション、およびダンプ関数を使用して、クォンタムプログラムをテストおよびデバッグする方法について説明します。
author: tcNickolas
ms.author: mamykhai@microsoft.com
ms.date: 06/01/2020
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2b5276da594ba263177d435c1153f6d96e29c4e8
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867915"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="0603c-103">テストとデバッグ</span><span class="sxs-lookup"><span data-stu-id="0603c-103">Testing and debugging</span></span>

<span data-ttu-id="0603c-104">従来のプログラミングと同様に、クォンタムプログラムが意図したとおりに動作することを確認し、正しくない動作を診断できるようにすることが不可欠です。</span><span class="sxs-lookup"><span data-stu-id="0603c-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose incorrect behavior.</span></span>
<span data-ttu-id="0603c-105">このセクションでは、 Q# クォンタムプログラムをテストおよびデバッグするためにに用意されているツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0603c-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="0603c-106">単体テスト</span><span class="sxs-lookup"><span data-stu-id="0603c-106">Unit Tests</span></span>

<span data-ttu-id="0603c-107">従来のプログラムをテストする一般的な方法の1つは、*単体テスト*と呼ばれる小さなプログラムを作成することです。これにより、ライブラリでコードを実行し、出力を予想される出力と比較します。</span><span class="sxs-lookup"><span data-stu-id="0603c-107">One common approach to testing classical programs is to write small programs called *unit tests*, which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="0603c-108">たとえば、 `Square(2)` `4` $ 2 ^ 2 = $4 の*priori*がわかっているため、がを返すようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="0603c-108">For example, you can ensure that `Square(2)` returns `4` since you know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="0603c-109">Q#は、クォンタムプログラムの単体テストの作成をサポートしています。これは、 [Xunit](https://xunit.github.io/)単体テストフレームワーク内でテストとして実行できます。</span><span class="sxs-lookup"><span data-stu-id="0603c-109">Q# supports creating unit tests for quantum programs, and which can run as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="0603c-110">テストプロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="0603c-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="0603c-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="0603c-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="0603c-112">Visual Studio 2019 を開きます。</span><span class="sxs-lookup"><span data-stu-id="0603c-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="0603c-113">[**ファイル**] メニューにアクセスし、[**新しい > プロジェクト**] を選択します。右上隅にあるを検索し、 `Q#` \*\* Q# テストプロジェクト\*\*テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="0603c-113">Go to the **File** menu and select **New > Project...**. In the upper right corner, search for `Q#`, and select the **Q# Test Project** template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="0603c-114">コマンドライン/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="0603c-114">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="0603c-115">お気に入りのコマンドラインから、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0603c-115">From your favorite command line, run the following command:</span></span>
```dotnetcli
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="0603c-116">新しいプロジェクトには `Tests.qs` 、新しい単体テストを定義するための便利な場所を提供する1つのファイルがあり Q# ます。</span><span class="sxs-lookup"><span data-stu-id="0603c-116">Your new project has a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="0603c-117">初期状態では、このファイルに `AllocateQubit` は、新しく割り当てられた qubit が $ \ket $ 状態であることを確認し、メッセージを出力するサンプル単体テストが1つ含まれてい {0} ます。</span><span class="sxs-lookup"><span data-stu-id="0603c-117">Initially, this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            AssertMeasurement([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="0603c-118">Q#型の引数を受け取り、を返すすべての操作または関数は `Unit` `Unit` 、属性を使用して単体テストとしてマークでき `@Test("...")` ます。</span><span class="sxs-lookup"><span data-stu-id="0603c-118">Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="0603c-119">前の例では、その属性の引数が、 `"QuantumSimulator"` テストを実行するターゲットを指定しています。</span><span class="sxs-lookup"><span data-stu-id="0603c-119">In the previous example, the argument to that attribute, `"QuantumSimulator"`, specifies the target on which the test runs.</span></span> <span data-ttu-id="0603c-120">1つのテストを複数のターゲットで実行できます。</span><span class="sxs-lookup"><span data-stu-id="0603c-120">A single test can run on multiple targets.</span></span> <span data-ttu-id="0603c-121">たとえば、の前に属性を追加し `@Test("ResourcesEstimator")` `AllocateQubit` ます。</span><span class="sxs-lookup"><span data-stu-id="0603c-121">For example, add an attribute `@Test("ResourcesEstimator")` before `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="0603c-122">ファイルを保存し、すべてのテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="0603c-122">Save the file and run all tests.</span></span> <span data-ttu-id="0603c-123">ここで、2つの単体テストがあります。1つはで実行され、もう1つは `AllocateQubit` `QuantumSimulator` で実行さ `ResourcesEstimator` れます。</span><span class="sxs-lookup"><span data-stu-id="0603c-123">There should now be two unit tests, one where `AllocateQubit` runs on the `QuantumSimulator`, and one where it runs in the `ResourcesEstimator`.</span></span> 

<span data-ttu-id="0603c-124">コンパイラは、 Q# 組み込みのターゲット、、を、 `"QuantumSimulator"` `"ToffoliSimulator"` `"ResourcesEstimator"` 単体テストの有効な実行ターゲットとして認識します。</span><span class="sxs-lookup"><span data-stu-id="0603c-124">The Q# compiler recognizes the built-in targets `"QuantumSimulator"`, `"ToffoliSimulator"`, and `"ResourcesEstimator"` as valid execution targets for unit tests.</span></span> <span data-ttu-id="0603c-125">また、任意の完全修飾名を指定して、カスタム実行ターゲットを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="0603c-125">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-no-locq-unit-tests"></a><span data-ttu-id="0603c-126">Q#単体テストの実行</span><span class="sxs-lookup"><span data-stu-id="0603c-126">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="0603c-127">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="0603c-127">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="0603c-128">ソリューションごとの1回限りの設定として、[**テスト**] メニューの [テストの設定] を選択し、[**既定のプロセッサアーキテクチャ > X64 >** ます。</span><span class="sxs-lookup"><span data-stu-id="0603c-128">As a one-time per-solution setup, go to the **Test** menu and select **Test Settings > Default Processor Architecture > X64**.</span></span>

> [!TIP]
> <span data-ttu-id="0603c-129">Visual Studio の既定のプロセッサアーキテクチャ設定は、各ソリューションのソリューションオプション () ファイルに格納され `.suo` ます。</span><span class="sxs-lookup"><span data-stu-id="0603c-129">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="0603c-130">このファイルを削除する場合は、プロセッサアーキテクチャとして**X64**を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0603c-130">If you delete this file, then you need to select **X64** as your processor architecture again.</span></span>

<span data-ttu-id="0603c-131">プロジェクトをビルドし、[**テスト**] メニューを開き、[ **Windows > テストエクスプローラー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0603c-131">Build the project, open the **Test** menu, and select **Windows > Test Explorer**.</span></span> <span data-ttu-id="0603c-132">**Allocatequbit**は、[**テストを実行しない**] グループのテストの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0603c-132">**AllocateQubit** displays in the list of tests in the **Not Run Tests** group.</span></span> <span data-ttu-id="0603c-133">[**すべて実行**] を選択するか、この個々のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="0603c-133">Select **Run All** or run this individual test.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="0603c-134">コマンドライン/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="0603c-134">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="0603c-135">テストを実行するには、プロジェクトフォルダー (を含むフォルダー) に移動 `Tests.csproj` し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0603c-135">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and run the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="0603c-136">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0603c-136">You should get output similar to the following:</span></span>

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

<span data-ttu-id="0603c-137">単体テストは、名前または実行ターゲットに応じてフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="0603c-137">Unit tests can be filtered according to their name or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="0603c-138">組み込み関数に <xref:microsoft.quantum.intrinsic.message> は型があり、 `(String -> Unit)` 診断メッセージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0603c-138">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="0603c-139">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="0603c-139">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="0603c-140">テストエクスプローラーでテストを実行し、テストをクリックすると、テストの実行に関する情報がパネルに表示されます (成功/失敗の状態、経過時間、および出力へのリンク)。</span><span class="sxs-lookup"><span data-stu-id="0603c-140">After you run a test in Test Explorer and click on the test, a panel displays with information about test execution: Pass/fail status, elapsed time, and a link to the output.</span></span> <span data-ttu-id="0603c-141">[**出力**] をクリックして、新しいウィンドウでテスト出力を開きます。</span><span class="sxs-lookup"><span data-stu-id="0603c-141">Click **Output** to open the test output in a new window.</span></span>

![テスト出力](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="0603c-143">コマンドライン/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="0603c-143">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="0603c-144">各テストの成功/失敗の状態は、によってコンソールに出力され `dotnet test` ます。</span><span class="sxs-lookup"><span data-stu-id="0603c-144">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="0603c-145">失敗したテストの場合は、エラーの診断に役立つ出力もコンソールに出力されます。</span><span class="sxs-lookup"><span data-stu-id="0603c-145">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="facts-and-assertions"></a><span data-ttu-id="0603c-146">ファクトとアサーション</span><span class="sxs-lookup"><span data-stu-id="0603c-146">Facts and Assertions</span></span>

<span data-ttu-id="0603c-147">の関数には Q# _論理的_な副作用がないため、プログラム内から、 Q# 出力の種類が空のタプルである関数の実行によって他の種類の影響が発生しないようにすることはできません `()` 。</span><span class="sxs-lookup"><span data-stu-id="0603c-147">Because functions in Q# have no _logical_ side effects, you can never observe, from within a Q# program, any other kinds of effects from running a function whose output type is the empty tuple `()`.</span></span>
<span data-ttu-id="0603c-148">つまり、ターゲットコンピューターは、この省略によって `()` 次のコードの動作が変更されないことを保証して、が返す関数を実行しないことを選択でき Q# ます。</span><span class="sxs-lookup"><span data-stu-id="0603c-148">That is, a target machine can choose not to run any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="0603c-149">この動作により `()` 、関数 (など `Unit` ) が、アサーションの埋め込みとプログラムへのデバッグロジックに便利なツールとして返さ Q# れます。</span><span class="sxs-lookup"><span data-stu-id="0603c-149">This behavior makes functions returning `()` (such as `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="0603c-150">単純な例を考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="0603c-150">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="0603c-151">ここで、キーワードは、 `fail` 計算が続行されないことを示し、プログラムを実行しているターゲットコンピューターで例外を発生させ Q# ます。</span><span class="sxs-lookup"><span data-stu-id="0603c-151">Here, the keyword `fail` indicates that the computation should not proceed, and raises an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="0603c-152">定義上、この種のエラーは、 Q# ターゲットコンピューターが Q# ステートメントに到達した後にコードを実行しなくなったため、内からは確認できません `fail` 。</span><span class="sxs-lookup"><span data-stu-id="0603c-152">By definition, a failure of this kind cannot be observed from within Q#, as the target machine no longer runs the Q# code after reaching a `fail` statement.</span></span>
<span data-ttu-id="0603c-153">したがって、への呼び出しを実行した後にを続行すると、入力が肯定的であることが `PositivityFact` 保証されます。</span><span class="sxs-lookup"><span data-stu-id="0603c-153">Thus, if we proceed past a call to `PositivityFact`, we can be assured that its input was positive.</span></span>

<span data-ttu-id="0603c-154">名前空間の関数を使用するのと同じ動作を実装できることに注意して `PositivityFact` [`Fact`](xref:microsoft.quantum.diagnostics.fact) <xref:microsoft.quantum.diagnostics> ください。</span><span class="sxs-lookup"><span data-stu-id="0603c-154">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:microsoft.quantum.diagnostics.fact) function from the <xref:microsoft.quantum.diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="0603c-155">一方、*アサーション*はファクトと同様に使用されますが、ターゲットコンピューターの状態によって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0603c-155">*Assertions*, on the other hand, are used similarly to facts but may depend on the state of the target machine.</span></span> <span data-ttu-id="0603c-156">それに応じて、これらは操作として定義されますが、ファクトは関数として定義されます (前の例のように)。</span><span class="sxs-lookup"><span data-stu-id="0603c-156">Correspondingly, they are defined as operations, whereas facts are defined as functions (as in the previous example).</span></span>
<span data-ttu-id="0603c-157">この違いを理解するには、アサーション内で次のファクトを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="0603c-157">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="0603c-158">ここでは、操作を使用して、 <xref:microsoft.quantum.environment.getqubitsavailabletouse> 使用可能な qubits の数を返します。</span><span class="sxs-lookup"><span data-stu-id="0603c-158">Here, we are using the operation <xref:microsoft.quantum.environment.getqubitsavailabletouse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="0603c-159">これは、プログラムとその実行環境のグローバルな状態によって異なりますが、の定義 `AssertQubitsAreAvailable` も操作である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0603c-159">As this depends on the global state of the program and its execution environment, our definition of `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="0603c-160">ただし、そのグローバル状態を使用し `Bool` て、関数への入力として単純な値を生成することができ `Fact` ます。</span><span class="sxs-lookup"><span data-stu-id="0603c-160">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="0603c-161">これらのアイデアを基にして構築さ[れた準備は](xref:microsoft.quantum.libraries.standard.prelude)、2つの便利なアサーションを提供 <xref:microsoft.quantum.diagnostics.assertmeasurement> し、 <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> 両方とも操作としてモデル化されて `()` います。</span><span class="sxs-lookup"><span data-stu-id="0603c-161">[The prelude](xref:microsoft.quantum.libraries.standard.prelude), building on these ideas, offers two especially useful assertions, <xref:microsoft.quantum.diagnostics.assertmeasurement> and <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> both modeled as operations onto `()`.</span></span> <span data-ttu-id="0603c-162">これらのアサーションは、特定の対象測定、測定が実行されるクォンタムレジスタ、および仮定の結果を記述する P# li オペレーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0603c-162">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="0603c-163">シミュレーションによって動作するターゲットコンピューターは、[複製なしの定理](https://en.wikipedia.org/wiki/No-cloning_theorem)によってバインドされないため、このようなアサーションに合格するレジスタに支障をきたすことなく、このような測定を実行できます。</span><span class="sxs-lookup"><span data-stu-id="0603c-163">Target machines which work by simulation are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register that passes to such assertions.</span></span>
<span data-ttu-id="0603c-164">次に、シミュレーターは、前の関数と同様に、 `PositivityFact` 仮定の結果が実際に観測されていない場合に計算を停止できます。</span><span class="sxs-lookup"><span data-stu-id="0603c-164">A simulator can then, similar to the `PositivityFact` function previous, stop computation if the hypothetical outcome is not observed in practice:</span></span>

```qsharp
using (register = Qubit()) 
{
    H(register);
    AssertMeasurement([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

<span data-ttu-id="0603c-165">物理クォンタムハードウェアでは、複製なしの定理がクォンタムの状態を検査できない場合 `AssertMeasurement` 、 `AssertMeasurementProbability` 操作と操作は単 `()` に他の効果なしでを返します。</span><span class="sxs-lookup"><span data-stu-id="0603c-165">On physical quantum hardware, where the no-cloning theorem prevents examination of a quantum state, the `AssertMeasurement` and `AssertMeasurementProbability` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="0603c-166">名前空間には、 <xref:microsoft.quantum.diagnostics> `Assert` さらに高度な条件を確認できるファミリの機能がいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="0603c-166">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family, with which you can check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="0603c-167">ダンプ関数</span><span class="sxs-lookup"><span data-stu-id="0603c-167">Dump Functions</span></span>

<span data-ttu-id="0603c-168">クォンタムプログラムのトラブルシューティングに役立つように、名前空間には、 <xref:microsoft.quantum.diagnostics> ターゲットコンピューターの現在の状態をファイルにダンプできる2つの関数 (および) が用意されて <xref:microsoft.quantum.diagnostics.dumpmachine> <xref:microsoft.quantum.diagnostics.dumpregister> います。</span><span class="sxs-lookup"><span data-stu-id="0603c-168">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="0603c-169">それぞれのの生成された出力は、ターゲットコンピューターによって異なります。</span><span class="sxs-lookup"><span data-stu-id="0603c-169">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="0603c-170">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="0603c-170">DumpMachine</span></span>

<span data-ttu-id="0603c-171">Quantum 開発キットの一部として配布された完全な状態のクォンタムシミュレーターは、クォンタムシステム全体の[wave 関数](https://en.wikipedia.org/wiki/Wave_function)を、1次元の複素数の配列としてファイルに書き込みます。各要素は、コンピューティングベースの状態を測定する確率の振幅 ($ \ket{n} = \ket{b_ {n-1}...) を表します。b_1b_0} $ (bits $ \{ b_i $ の場合) \} 。</span><span class="sxs-lookup"><span data-stu-id="0603c-171">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="0603c-172">たとえば、2つの qubits のみが割り当てられ、クォンタム状態が $ $ \begin{align} \ket{\psi} = \ frac {1} {\ sqrt {2} } \ket {00} -\frac{(1 + i)} \ket であるコンピューターでは、 {2} {10} \end{align} $ $ を呼び出すと、次の出力が生成され <xref:microsoft.quantum.diagnostics.dumpmachine> ます。</span><span class="sxs-lookup"><span data-stu-id="0603c-172">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="0603c-173">最初の行は、対応する qubits の id を持つコメントを有意な順序で提供します。</span><span class="sxs-lookup"><span data-stu-id="0603c-173">The first row provides a comment with the ids of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="0603c-174">残りの行は、デカルト形式と極座標形式の両方で、basis 状態ベクター $ \ket{n} $ を測定する確率の振幅を示しています。</span><span class="sxs-lookup"><span data-stu-id="0603c-174">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="0603c-175">最初の行の詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0603c-175">In detail for the first row:</span></span>

* <span data-ttu-id="0603c-176">**`∣0❭:`** この行は、計算基礎の状態に対応します。 `0`</span><span class="sxs-lookup"><span data-stu-id="0603c-176">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="0603c-177">**`0.707107 +  0.000000 i`**: デカルト形式の確率の振幅。</span><span class="sxs-lookup"><span data-stu-id="0603c-177">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="0603c-178">**` == `**: 符号は、 `equal` 両方の同等の表現を分離します。</span><span class="sxs-lookup"><span data-stu-id="0603c-178">**` == `**: the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="0603c-179">**`**********  `**: 大きさをグラフィカルに表示します。の数は、 `*` この状態ベクターを測定する確率に比例します。</span><span class="sxs-lookup"><span data-stu-id="0603c-179">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="0603c-180">**`[ 0.500000 ]`**: マグニチュードの数値</span><span class="sxs-lookup"><span data-stu-id="0603c-180">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="0603c-181">**`    ---`**: 振幅のフェーズをグラフィカルに表示します (次の出力を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="0603c-181">**`    ---`**: A graphical representation of the amplitude's phase (see the following output).</span></span>
* <span data-ttu-id="0603c-182">**`[ 0.0000 rad ]`**: フェーズの数値 (ラジアン)。</span><span class="sxs-lookup"><span data-stu-id="0603c-182">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="0603c-183">大きさとフェーズの両方がグラフィック表示で表示されます。</span><span class="sxs-lookup"><span data-stu-id="0603c-183">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="0603c-184">マグニチュード表現は、水平方向です。の棒が大きいほど、 `*` 棒が大きくなる確率が大きくなります。</span><span class="sxs-lookup"><span data-stu-id="0603c-184">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="0603c-185">フェーズでは、次の記号を使用して範囲に基づく角度を表します。</span><span class="sxs-lookup"><span data-stu-id="0603c-185">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="0603c-186">次の例は、 `DumpMachine` いくつかの一般的な状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="0603c-186">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="0603c-187">Qubit の id は実行時に割り当てられ、必ずしも qubit が割り当てられた順序、または qubit レジスタ内の位置に一致するとは限りません。</span><span class="sxs-lookup"><span data-stu-id="0603c-187">The id of a qubit is assigned at runtime and is not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="0603c-188">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="0603c-188">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="0603c-189">コードにブレークポイントを配置し、qubit 変数の値を調べることで、Visual Studio で qubit id を見つけることができます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0603c-189">You can locate a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![Visual Studio での qubit id の表示](~/media/qubit_id.png)
  >
  > <span data-ttu-id="0603c-191">インデックスがである qubit の `0` `register2` id = `3` 、qubit with index `1` は id = `2` です。</span><span class="sxs-lookup"><span data-stu-id="0603c-191">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="0603c-192">コマンドライン/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="0603c-192">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="0603c-193">関数を使用し、メッセージに qubit 変数を渡すことによって、qubit id を見つけることができ <xref:microsoft.quantum.intrinsic.message> ます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0603c-193">You can locate a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="0603c-194">次のような出力が生成できます。</span><span class="sxs-lookup"><span data-stu-id="0603c-194">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="0603c-195">これは、インデックスを持つ qubit の id がであることを意味します。これは、 `0` `register2` `3` インデックスを持つ qubit `1` が id = であることを意味し `2` ます。</span><span class="sxs-lookup"><span data-stu-id="0603c-195">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="0603c-196"><xref:microsoft.quantum.diagnostics.dumpmachine>は名前空間の一部 <xref:microsoft.quantum.diagnostics> であるため、 `open` それにアクセスするためのステートメントを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0603c-196">Since <xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, you must add an `open` statement to access it:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="0603c-197">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="0603c-197">DumpRegister</span></span>

<span data-ttu-id="0603c-198"><xref:microsoft.quantum.diagnostics.dumpregister>はと同じように動作し <xref:microsoft.quantum.diagnostics.dumpmachine> ますが、情報の量を対応する qubits に限定するために、qubits の配列も取得する点が異なります。</span><span class="sxs-lookup"><span data-stu-id="0603c-198"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except that it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="0603c-199">と同様に <xref:microsoft.quantum.diagnostics.dumpmachine> 、によって生成される情報は <xref:microsoft.quantum.diagnostics.dumpregister> ターゲットコンピューターによって異なります。</span><span class="sxs-lookup"><span data-stu-id="0603c-199">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="0603c-200">完全な状態のクォンタムシミュレーターでは、と同じ形式で指定された qubits によって生成されるクォンタムサブシステムのグローバルフェーズまで、wave 関数がファイルに書き込まれ <xref:microsoft.quantum.diagnostics.dumpmachine> ます。</span><span class="sxs-lookup"><span data-stu-id="0603c-200">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="0603c-201">たとえば、2つの qubits のみが割り当てられ、クォンタム状態が $ $ \begin{align} \ket{\psi} = \ frac {1} {\ sqrt {2} } \ket {00} -\frac{(1 + i)} \ket =-e ^ {であるマシンをもう一度実行します。 {2} {10} -i \ pi/4} ((\ frac {1} {\ sqrt {2} } \ket {0} -\frac{(1 + i)} {2} \ket {1} ) \ otimes \frac{-(1 + i)} {\ sqrt {2} } \ket {0} )、\end{align} $ $ を呼び出すと <xref:microsoft.quantum.diagnostics.dumpregister> 、次の出力が生成され `qubit[0]` ます。</span><span class="sxs-lookup"><span data-stu-id="0603c-201">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="0603c-202">とを呼び出すと、次 <xref:microsoft.quantum.diagnostics.dumpregister> の出力が生成され `qubit[1]` ます。</span><span class="sxs-lookup"><span data-stu-id="0603c-202">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="0603c-203">一般に、別のレジスタによって使用されるレジスタの状態は、純粋な状態ではなく混合状態になります。</span><span class="sxs-lookup"><span data-stu-id="0603c-203">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="0603c-204">この場合、は <xref:microsoft.quantum.diagnostics.dumpregister> 次のメッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="0603c-204">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="0603c-205">次の例は、 <xref:microsoft.quantum.diagnostics.dumpregister> コード内でとの両方を使用する方法を示してい <xref:microsoft.quantum.diagnostics.dumpmachine> Q# ます。</span><span class="sxs-lookup"><span data-stu-id="0603c-205">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="0603c-206">デバッグ</span><span class="sxs-lookup"><span data-stu-id="0603c-206">Debugging</span></span>

<span data-ttu-id="0603c-207">`Assert`およびの `Dump` 関数と操作の上で、は、 Q# 標準の Visual Studio デバッグ機能のサブセットをサポートしています。[行ブレークポイントの設定](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)、 [F10 を使用したコードのステップ](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)実行、および[クラシック変数の値の検査](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)は、シミュレーターでのコードの実行中に可能です。</span><span class="sxs-lookup"><span data-stu-id="0603c-207">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger), and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="0603c-208">Visual Studio Code でのデバッグでは、OmniSharp によって強化された Visual Studio Code 拡張機能のために C# によって提供されるデバッグ機能を利用し、[最新バージョン](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0603c-208">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 
