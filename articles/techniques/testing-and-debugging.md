---
title: 'Q # の手法-テストとデバッグ |Microsoft Docs'
description: 'Q # の手法-テストとデバッグ'
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 25679331f1bed9f98b86c6eb20f511c891bac1af
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183490"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="e1c17-103">テストとデバッグ</span><span class="sxs-lookup"><span data-stu-id="e1c17-103">Testing and Debugging</span></span>

<span data-ttu-id="e1c17-104">従来のプログラミングと同様に、クォンタムプログラムが意図したとおりに動作することを確認し、正しくないクォンタムプログラムを診断できるようにすることが不可欠です。</span><span class="sxs-lookup"><span data-stu-id="e1c17-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="e1c17-105">このセクションでは、クォンタムプログラムをテストおよびデバッグするための Q # によって提供されるツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="e1c17-106">単体テスト</span><span class="sxs-lookup"><span data-stu-id="e1c17-106">Unit Tests</span></span>

<span data-ttu-id="e1c17-107">クラシックプログラムをテストする一般的な方法の1つは、ライブラリ内のコードを実行する*単体テスト*と呼ばれる小さなプログラムを記述し、その出力を予想される出力と比較することです。</span><span class="sxs-lookup"><span data-stu-id="e1c17-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="e1c17-108">たとえば、 *priori*が $ 2 ^ 2 = $4 であることがわかっているため、`Square(2)` が `4`を返すようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="e1c17-109">Q # は、クォンタムプログラムの単体テストの作成をサポートしています。これは、 [Xunit](https://xunit.github.io/)単体テストフレームワーク内でテストとして実行できます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="e1c17-110">テストプロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="e1c17-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="e1c17-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="e1c17-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="e1c17-112">Visual Studio 2019 を開きます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="e1c17-113">`File` メニューにアクセスし、[`New` > `Project...`] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="e1c17-114">プロジェクトテンプレートエクスプローラーの `Installed` > `Visual C#`で、`Q# Test Project` テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-114">In the project template explorer, under `Installed` > `Visual C#`, select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="e1c17-115">コマンドライン/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="e1c17-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="e1c17-116">お気に入りのコマンドラインから、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="e1c17-117">どちらの場合も、新しいプロジェクトに2つのファイルが開かれます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-117">In either case, your new project will have two files open.</span></span>
<span data-ttu-id="e1c17-118">最初のファイル `Tests.qs`は、新しい Q # の単体テストを定義するための便利な場所です。</span><span class="sxs-lookup"><span data-stu-id="e1c17-118">The first file, `Tests.qs`, provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="e1c17-119">初期状態では、このファイルには1つのサンプル単体テスト `AllocateQubitTest` が含まれています。これは、新しく割り当てられた qubit が $ \ket{0}$ 状態であることを確認し、メッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-119">Initially this file contains one sample unit test `AllocateQubitTest` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    operation AllocateQubitTest () : Unit {
        using (q = Qubit()) {
            Assert([PauliZ], [q], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="e1c17-120">`(Unit -> Unit)` と互換性のある型 `(Unit => Unit)` または関数と互換性のある Q # 操作は、単体テストとして実行できます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-120">Any Q# operation compatible with the type `(Unit => Unit)` or function compatible with `(Unit -> Unit)` can be executed as a unit test.</span></span> 

<span data-ttu-id="e1c17-121">2番目のファイル `TestSuiteRunner.cs` には、Q # の単体テストを検出して実行するメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e1c17-121">The second file, `TestSuiteRunner.cs` contains a method that discovers and runs Q# unit tests.</span></span> <span data-ttu-id="e1c17-122">これは `OperationDriver` 属性で注釈が付けられた `TestTarget` メソッドです。</span><span class="sxs-lookup"><span data-stu-id="e1c17-122">This is the method `TestTarget` annotated with `OperationDriver` attribute.</span></span>
<span data-ttu-id="e1c17-123">`OperationDriver` 属性は、Xunit 拡張機能ライブラリの一部であり、"、" です。</span><span class="sxs-lookup"><span data-stu-id="e1c17-123">The `OperationDriver` attribute is a part of the Xunit extension library Microsoft.Quantum.Simulation.Xunit.</span></span>
<span data-ttu-id="e1c17-124">単体テストフレームワークは、検出されたすべての Q # 単体テストに対して `TestTarget` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-124">The unit testing framework calls `TestTarget` method for every Q# unit test it has discovered.</span></span>
<span data-ttu-id="e1c17-125">フレームワークは `op` 引数を使用して、単体テストの説明をメソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-125">The framework passes the unit test description to the method through `op` argument.</span></span> <span data-ttu-id="e1c17-126">次のコード行を実行します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-126">The following line of code:</span></span>
```csharp
op.TestOperationRunner(sim);
```
<span data-ttu-id="e1c17-127">`QuantumSimulator`で単体テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-127">executes the unit test on `QuantumSimulator`.</span></span>

<span data-ttu-id="e1c17-128">既定では、単体テストの検出メカニズムは、次のプロパティを満たすすべての Q # 関数または互換性のある型の操作を検索します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-128">By default, the unit test discovery mechanism looks for all Q# functions or operations of compatible type that satisfy the following properties:</span></span>
* <span data-ttu-id="e1c17-129">`OperationDriver` 属性で注釈が付けられたメソッドと同じアセンブリ内にあります。</span><span class="sxs-lookup"><span data-stu-id="e1c17-129">Located in the same assembly as the method annotated with the `OperationDriver` attribute.</span></span>
* <span data-ttu-id="e1c17-130">`OperationDriver` 属性で注釈が付けられたメソッドと同じ名前空間にあります。</span><span class="sxs-lookup"><span data-stu-id="e1c17-130">Located in the same namespace as the method annotated with the `OperationDriver` attribute.</span></span>
* <span data-ttu-id="e1c17-131">には `Test`で終わる名前があります。</span><span class="sxs-lookup"><span data-stu-id="e1c17-131">Has a name ending with `Test`.</span></span>

<span data-ttu-id="e1c17-132">アセンブリ、名前空間、および単体テスト関数と操作のサフィックスは、`OperationDriver` 属性の省略可能なパラメーターを使用して設定できます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-132">An assembly, a namespace, and a suffix for unit test functions and operations can be set using optional parameters of the `OperationDriver` attribute:</span></span>
* <span data-ttu-id="e1c17-133">`AssemblyName` パラメーターは、テスト用に検索されるアセンブリの名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-133">`AssemblyName` parameter sets the name of the assembly which is being searched for tests.</span></span>
* <span data-ttu-id="e1c17-134">`TestNamespace` パラメーターは、テスト用に検索される名前空間の名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-134">`TestNamespace` parameter sets the name of the namespace which is being searched for tests.</span></span>
* <span data-ttu-id="e1c17-135">単体テストと見なされる操作名または関数名のサフィックスを `Suffix` 設定します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-135">`Suffix` sets the suffix of operation or function names that are considered to be unit tests.</span></span>

<span data-ttu-id="e1c17-136">また、`TestCasePrefix` 省略可能なパラメーターを使用すると、テストケースの名前のプレフィックスを設定できます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-136">In addition, the `TestCasePrefix` optional parameter lets you set a prefix for the name of the test case.</span></span> <span data-ttu-id="e1c17-137">操作名の前にあるプレフィックスが、テストケースの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-137">The prefix in front of the operation name will appear in the list of test cases.</span></span> <span data-ttu-id="e1c17-138">たとえば、`TestCasePrefix = "QSim:"` によって `AllocateQubitTest` が検出されたテストの一覧に `QSim:AllocateQubitTest` として表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-138">For example, `TestCasePrefix = "QSim:"` will cause `AllocateQubitTest` to appear as `QSim:AllocateQubitTest` in the list of found tests.</span></span> <span data-ttu-id="e1c17-139">これは、たとえば、テストの実行に使用されるシミュレーターを示すのに便利です。</span><span class="sxs-lookup"><span data-stu-id="e1c17-139">This can be useful to indicate, for instance, which simulator is used to run a test.</span></span>

### <a name="running-q-unit-tests"></a><span data-ttu-id="e1c17-140">Q # の単体テストの実行</span><span class="sxs-lookup"><span data-stu-id="e1c17-140">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="e1c17-141">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="e1c17-141">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="e1c17-142">ソリューションごとの1回限りの設定として、`Test` メニューにアクセスし、[`Test Settings` > `Default Processor Architecture` > `X64`] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-142">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="e1c17-143">Visual Studio の既定のプロセッサアーキテクチャ設定は、各ソリューションのソリューションオプション (`.suo`) ファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-143">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="e1c17-144">このファイルを削除する場合は、プロセッサのアーキテクチャとして [`X64`] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1c17-144">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="e1c17-145">プロジェクトをビルドし、[`Test`] メニューにアクセスして、[`Windows` > `Test Explorer`] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-145">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="e1c17-146">`Not Run Tests` グループ内のテストの一覧に `AllocateQubitTest` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-146">`AllocateQubitTest` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="e1c17-147">`Run All` を選択するか、この個別のテストを実行して、合格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1c17-147">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="e1c17-148">コマンドライン/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="e1c17-148">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="e1c17-149">テストを実行するには、プロジェクトフォルダー (`Tests.csproj`を含むフォルダー) に移動し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-149">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="e1c17-150">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-150">You should get output similar to the following:</span></span>

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

***

## <a name="logging-and-assertions"></a><span data-ttu-id="e1c17-151">ログとアサーション</span><span class="sxs-lookup"><span data-stu-id="e1c17-151">Logging and Assertions</span></span>

<span data-ttu-id="e1c17-152">Q # の関数には副作用がないという事実が1つあります。これは、出力の種類が空の `()` タプルである関数を実行した場合の影響は、Q # プログラム内からは確認できないということです。</span><span class="sxs-lookup"><span data-stu-id="e1c17-152">One important consequence of the fact that functions in Q# have no side effects is that any effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="e1c17-153">つまり、ターゲットコンピューターは、この省略によって次の Q # コードの動作が変更されないことを保証して `()` を返す関数を実行しないことを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-153">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="e1c17-154">これにより、アサーションを埋め込み、デバッグロジックを Q # プログラムに組み込むための便利なツール `()` を返す関数が作成されます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-154">This makes functions returning `()` a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

### <a name="logging"></a><span data-ttu-id="e1c17-155">ログ記録</span><span class="sxs-lookup"><span data-stu-id="e1c17-155">Logging</span></span>

<span data-ttu-id="e1c17-156">組み込み関数 <xref:microsoft.quantum.intrinsic.message> 型 `(String -> Unit)` で、診断メッセージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-156">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

<span data-ttu-id="e1c17-157">`QuantumSimulator` の `onLog` アクションを使用して、Q # コードが `Message`を呼び出すときに実行されるアクションを定義できます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-157">The `onLog` action of `QuantumSimulator` can be used to define actions performed when Q# code calls `Message`.</span></span> <span data-ttu-id="e1c17-158">既定では、ログに記録されたメッセージは標準出力に出力されます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-158">By default logged messages are printed to standard output.</span></span>

<span data-ttu-id="e1c17-159">単体テストスイートを定義する場合、ログに記録されたメッセージをテスト出力に送ることができます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-159">When defining a unit test suite, the logged messages can be directed to the test output.</span></span> <span data-ttu-id="e1c17-160">プロジェクトが Q # Test プロジェクトテンプレートから作成されると、このリダイレクトはスイート用に事前構成され、既定では次のように作成されます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-160">When a project is created from Q# Test Project template, this redirection is pre-configured for the suite and created by default as follows:</span></span>

```qsharp
using (var sim = new QuantumSimulator())
{
    // OnLog defines action(s) performed when Q# test calls operation Message
    sim.OnLog += (msg) => { output.WriteLine(msg); };
    op.TestOperationRunner(sim);
}
```

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="e1c17-161">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="e1c17-161">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="e1c17-162">テストエクスプローラーでテストを実行し、テストをクリックすると、テストの実行に関する情報がパネルに表示されます (成功/失敗の状態、経過時間、および "出力" リンク)。</span><span class="sxs-lookup"><span data-stu-id="e1c17-162">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="e1c17-163">[出力] リンクをクリックすると、新しいウィンドウでテスト出力が開きます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-163">If you click the "Output" link, test output will open in a new window.</span></span>

![テスト出力](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="e1c17-165">コマンドライン/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="e1c17-165">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="e1c17-166">各テストの成功/失敗の状態は、`dotnet test`によってコンソールに出力されます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-166">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="e1c17-167">失敗したテストについては、上記の `output.WriteLine(msg)` 呼び出しの結果として記録された出力もコンソールに出力され、エラーの診断に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-167">For failing tests, the outputs logged as a result of the `output.WriteLine(msg)` call above are also printed to the console to help diagnose the failure.</span></span>

***

### <a name="assertions"></a><span data-ttu-id="e1c17-168">表明</span><span class="sxs-lookup"><span data-stu-id="e1c17-168">Assertions</span></span>

<span data-ttu-id="e1c17-169">同じロジックを、アサーションの実装にも適用できます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-169">The same logic can be applied to implementing assertions.</span></span> <span data-ttu-id="e1c17-170">単純な例を考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="e1c17-170">Let's consider a simple example:</span></span>

```qsharp
function AssertPositive(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="e1c17-171">ここで、キーワード `fail` は、計算が続行されないことを示し、Q # プログラムを実行しているターゲットコンピューターで例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-171">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="e1c17-172">定義上、Q # 内では、この種のエラーを確認することはできません。これは、`fail` ステートメントに達した後に、それ以上の Q # コードが実行されないためです。</span><span class="sxs-lookup"><span data-stu-id="e1c17-172">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="e1c17-173">したがって、`AssertPositive`の呼び出しを続けて実行した場合は、入力が肯定的であることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-173">Thus, if we proceed past a call to `AssertPositive`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="e1c17-174">これらのアイデアを基にして、準備には、`()`に対する操作としてモデル化さ[れた](xref:microsoft.quantum.libraries.standard.prelude)、<xref:microsoft.quantum.intrinsic.assert> と <xref:microsoft.quantum.intrinsic.assertprob> の2つの便利なアサーションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="e1c17-174">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="e1c17-175">これらのアサーションは、特定の対象測定、測定を実行するクォンタムレジスタ、および仮定の結果を記述する P# li オペレーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e1c17-175">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="e1c17-176">シミュレーションによって動作するターゲットコンピューターでは、[複製なしの定理](https://en.wikipedia.org/wiki/No-cloning_theorem)によってバインドされていないため、このようなアサーションに渡されたレジスタに支障をきたすことなく、このような測定を実行できます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-176">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="e1c17-177">シミュレーターは、上記の `AssertPositive` 関数と同様に、実際の結果が実際に観察されない場合に計算を中止できます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-177">A simulator can then, similar to the `AssertPositive` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

```qsharp
using (register = Qubit()) 
{
    H(register);
    Assert([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

<span data-ttu-id="e1c17-178">物理的なクォンタムハードウェアでは、複製なしの定理がクォンタムの状態を検査できない場合、`Assert` 操作と `AssertProb` 操作は単に `()` を返します。これ以外の影響はありません。</span><span class="sxs-lookup"><span data-stu-id="e1c17-178">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="e1c17-179"><xref:microsoft.quantum.diagnostics> 名前空間には、より高度な条件をチェックできるようにする、`Assert` ファミリの機能がいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="e1c17-179">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="e1c17-180">ダンプ関数</span><span class="sxs-lookup"><span data-stu-id="e1c17-180">Dump Functions</span></span>

<span data-ttu-id="e1c17-181">クォンタムプログラムのトラブルシューティングに役立つように、<xref:microsoft.quantum.diagnostics> 名前空間には、ターゲットコンピューターの現在の状態をファイルにダンプできる2つの関数 (<xref:microsoft.quantum.diagnostics.dumpmachine> と <xref:microsoft.quantum.diagnostics.dumpregister>) が用意されています。</span><span class="sxs-lookup"><span data-stu-id="e1c17-181">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="e1c17-182">それぞれのの生成された出力は、ターゲットコンピューターによって異なります。</span><span class="sxs-lookup"><span data-stu-id="e1c17-182">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="e1c17-183">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="e1c17-183">DumpMachine</span></span>

<span data-ttu-id="e1c17-184">Quantum 開発キットの一部として配布された完全な状態のクォンタムシミュレーターは、ファセットの1次元配列として、クォンタムシステム全体の[wave 関数](https://en.wikipedia.org/wiki/Wave_function)をファイルに書き込みます。各要素は、計算基準の状態を測定する確率 $ \ket{n} $ ($ \ket{n} = \ket{b_{n-1}...)b_1b_0} $ for bits $\{b_i\}$。</span><span class="sxs-lookup"><span data-stu-id="e1c17-184">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="e1c17-185">たとえば、2つの qubits が割り当てられていて、クォンタム状態が $ $ \begin{align} \ket{\psi}{2}{1}= \ket{00}-\frac{(1 + i)}{2} \ket{10}であるコンピューターでは、\end{align} $ $ の呼び出し <xref:microsoft.quantum.diagnostics.dumpmachine> はこの出力を生成します:</span><span class="sxs-lookup"><span data-stu-id="e1c17-185">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="e1c17-186">最初の行は、対応する qubits の Id を持つコメントを有意な順序で提供します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-186">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="e1c17-187">残りの行は、デカルト形式と極座標形式の両方で、basis 状態ベクター $ \ket{n} $ を測定する確率の振幅を示しています。</span><span class="sxs-lookup"><span data-stu-id="e1c17-187">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="e1c17-188">最初の行の詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e1c17-188">In detail for the first row:</span></span>

* <span data-ttu-id="e1c17-189">この行 **`∣0❭:`** `0` の計算基準の状態に対応します</span><span class="sxs-lookup"><span data-stu-id="e1c17-189">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="e1c17-190">**`0.707107 +  0.000000 i`** : デカルト形式の確率の振幅。</span><span class="sxs-lookup"><span data-stu-id="e1c17-190">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="e1c17-191">**` == `** : `equal` sign は、両方の同等表現を seperates します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-191">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="e1c17-192">**`**********  `** : 大きさをグラフィカルに表現したもので、`*` の数は、この状態ベクターを測定する確率に比例します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-192">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="e1c17-193">**`[ 0.500000 ]`** : 大きさの数値</span><span class="sxs-lookup"><span data-stu-id="e1c17-193">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="e1c17-194">**`    ---`** : 振幅のフェーズをグラフィックで表現したもの (下記参照)。</span><span class="sxs-lookup"><span data-stu-id="e1c17-194">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="e1c17-195">**`[ 0.0000 rad ]`** : フェーズの数値 (ラジアン)。</span><span class="sxs-lookup"><span data-stu-id="e1c17-195">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="e1c17-196">大きさとフェーズの両方がグラフィック表示で表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-196">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="e1c17-197">マグニチュード表現は、水平方向であり、`*`の棒を示すので、棒が大きくなる確率が大きくなります。</span><span class="sxs-lookup"><span data-stu-id="e1c17-197">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="e1c17-198">フェーズでは、次の記号を使用して範囲に基づく角度を表します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-198">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="e1c17-199">次の例は、いくつかの一般的な状態の `DumpMachine` を示しています。</span><span class="sxs-lookup"><span data-stu-id="e1c17-199">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="e1c17-200">Qubit の id は実行時に割り当てられ、必ずしも qubit が割り当てられた順序、または qubit レジスタ内の位置に一致するとは限りません。</span><span class="sxs-lookup"><span data-stu-id="e1c17-200">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="e1c17-201">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="e1c17-201">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="e1c17-202">コードにブレークポイントを配置し、qubit 変数の値を調べることで、Visual Studio で qubit id を調べることができます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-202">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![Visual Studio での qubit id の表示](~/media/qubit_id.png)
  >
  > <span data-ttu-id="e1c17-204">`register2` のインデックス `0` を持つ qubit の id =`3`、インデックス `1` の qubit には id =`2`が使用されています。</span><span class="sxs-lookup"><span data-stu-id="e1c17-204">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[<span data-ttu-id="e1c17-205">コマンドライン/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="e1c17-205">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="e1c17-206"><xref:microsoft.quantum.intrinsic.message> 関数を使用し、メッセージに qubit 変数を渡すことによって、qubit id を確認できます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-206">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="e1c17-207">次のような出力が生成できます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-207">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="e1c17-208">これは、`register2` のインデックス `0` が指定された qubit に id =`3`があることを意味します。これは、インデックス `1` の qubit の id が`2`であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-208">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="e1c17-209"><xref:microsoft.quantum.diagnostics.dumpmachine> は <xref:microsoft.quantum.diagnostics> 名前空間の一部であるため、これを使用するには `open` ステートメントを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1c17-209"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="e1c17-210">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="e1c17-210">DumpRegister</span></span>

<span data-ttu-id="e1c17-211"><xref:microsoft.quantum.diagnostics.dumpregister> は <xref:microsoft.quantum.diagnostics.dumpmachine>のように機能しますが、情報の量を対応する qubits にのみ制限するために、qubits の配列を受け取る点が異なります。</span><span class="sxs-lookup"><span data-stu-id="e1c17-211"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="e1c17-212"><xref:microsoft.quantum.diagnostics.dumpmachine>と同様に、<xref:microsoft.quantum.diagnostics.dumpregister> によって生成される情報はターゲットコンピューターによって異なります。</span><span class="sxs-lookup"><span data-stu-id="e1c17-212">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="e1c17-213">完全な状態のクォンタムシミュレーターでは、ファイルに書き込みます。これは、指定された qubits によって生成されるクォンタムサブシステムのグローバルフェーズまで、wave 関数を <xref:microsoft.quantum.diagnostics.dumpmachine>と同じ形式で作成します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-213">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="e1c17-214">たとえば、2つの qubits が割り当てられ、クォンタム状態が $ $ \begin{align} \ket{\psi} = \ frac{1}{\ sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10} =-e ^ {-i \ pi/4} ((\ frac{1}{/sqrt{2}} \) のコンピューターを再度実行します。k{0}-\frac{(1 + i)}{2} \ket{1}) \ otimes \frac{-(1 + i)} {\ sqrt{2}} \ket{0})、\end{align} $ $ <xref:microsoft.quantum.diagnostics.dumpregister> を呼び出すと、この出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-214">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="e1c17-215">また、`qubit[1]` の <xref:microsoft.quantum.diagnostics.dumpregister> を呼び出すと、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e1c17-215">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="e1c17-216">一般に、別のレジスタによって使用されるレジスタの状態は、純粋な状態ではなく混合状態になります。</span><span class="sxs-lookup"><span data-stu-id="e1c17-216">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="e1c17-217">この場合、<xref:microsoft.quantum.diagnostics.dumpregister> は次のメッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-217">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="e1c17-218">次の例では、Q # コードで <xref:microsoft.quantum.diagnostics.dumpregister> と <xref:microsoft.quantum.diagnostics.dumpmachine> の両方を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1c17-218">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="e1c17-219">デバッグ</span><span class="sxs-lookup"><span data-stu-id="e1c17-219">Debugging</span></span>

<span data-ttu-id="e1c17-220">`Assert` と `Dump` の関数と操作の上で、Q # は標準の Visual Studio デバッグ機能のサブセットをサポートします。コードの[ブレークポイントの設定](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)、 [F10 を使用したコードのステップ実行](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)、および[クラシック変数の値の検査](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)は、シミュレーターでのコードの実行中に可能です。</span><span class="sxs-lookup"><span data-stu-id="e1c17-220">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="e1c17-221">Visual Studio Code でのデバッグはまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e1c17-221">Debugging in Visual Studio Code is not yet supported.</span></span>

