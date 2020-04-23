---
title: Q# プログラムのテストとデバッグ
description: 単体テスト、ファクトとアサーション、およびダンプ関数を使用してクォンタム プログラムをテストおよびデバッグする方法について説明します。
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: caf15b7273b7efed1da87a2edd62c06cd4357593
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030584"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="5fd5e-103">テストとデバッグ</span><span class="sxs-lookup"><span data-stu-id="5fd5e-103">Testing and Debugging</span></span>

<span data-ttu-id="5fd5e-104">古典プログラミングと同様に、量子プログラムが意図したとおりに機能することを確認し、間違った量子プログラムを診断できることが不可欠です。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="5fd5e-105">このセクションでは、クォンタム プログラムのテストとデバッグに関する Q# のツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="5fd5e-106">単体テスト</span><span class="sxs-lookup"><span data-stu-id="5fd5e-106">Unit Tests</span></span>

<span data-ttu-id="5fd5e-107">古典的なプログラムをテストする一般的なアプローチの 1 つは、ライブラリでコードを実行し、その出力を予想される出力と比較する*単体テスト*と呼ばれる小さなプログラムを作成することです。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="5fd5e-108">たとえば、2^2 = 4$`4`という*事前設定*を知っているので、`Square(2)`必ず返すことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="5fd5e-109">Q# は、クォンタム プログラムの単体テストの作成をサポートしており[、xUnit](https://xunit.github.io/)単体テスト フレームワーク内でテストとして実行できます。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="5fd5e-110">テスト プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="5fd5e-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="5fd5e-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="5fd5e-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="5fd5e-112">Visual Studio 2019 を開きます。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="5fd5e-113">メニューに`File`移動し、`New` > `Project...`を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="5fd5e-114">右上隅で を検索`Q#`し、テンプレートを選択します。 `Q# Test Project`</span><span class="sxs-lookup"><span data-stu-id="5fd5e-114">In the upper right corner, search for `Q#`, and select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="5fd5e-115">コマンドライン/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5fd5e-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="5fd5e-116">好みのコマンド ラインから、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="5fd5e-117">新しいプロジェクトには単一のファイル`Tests.qs`が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-117">Your new project will have a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="5fd5e-118">最初にこのファイルには、新しく`AllocateQubit`割り当てられた qubit が $\ket{0}$ 状態であることを確認し、メッセージを出力する 1 つのサンプル単体テストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-118">Initially this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

:new: <span data-ttu-id="5fd5e-119">型`Unit`の引数を受け取り、戻り値`Unit`を持つ Q# の操作または`@Test("...")`関数は、属性を使用して単体テストとしてマークできます。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-119">Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="5fd5e-120">上記の属性の引数は`"QuantumSimulator"`、テストが実行されるターゲットを指定します。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-120">The argument to that attribute, `"QuantumSimulator"` above, specifies the target on which the test is executed.</span></span> <span data-ttu-id="5fd5e-121">複数のターゲットに対して 1 つのテストを実行できます。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-121">A single test can be executed on multiple targets.</span></span> <span data-ttu-id="5fd5e-122">たとえば、上`@Test("ResourcesEstimator")``AllocateQubit`に属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-122">For example, add an attribute `@Test("ResourcesEstimator")` above `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="5fd5e-123">ファイルを保存し、すべてのテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-123">Save the file and execute all tests.</span></span> <span data-ttu-id="5fd5e-124">次に、2 つの単体テストが必要です。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-124">There should now be two unit tests, one where AllocateQubit is executed on the QuantumSimulator, and one where it is executed in the ResourceEstimator.</span></span> 

<span data-ttu-id="5fd5e-125">Q# コンパイラは、組み込みのターゲット "QuantumSimulator"、"トフォリシミュレータ"、および "リソース推定子" を単体テストの有効な実行ターゲットとして認識します。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-125">The Q# compiler recognizes the built-in targets "QuantumSimulator", "ToffoliSimulator", and "ResourcesEstimator" as valid execution targets for unit tests.</span></span> <span data-ttu-id="5fd5e-126">また、任意の完全修飾名を指定して、カスタム実行ターゲットを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-126">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-q-unit-tests"></a><span data-ttu-id="5fd5e-127">Q# 単体テストの実行</span><span class="sxs-lookup"><span data-stu-id="5fd5e-127">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="5fd5e-128">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="5fd5e-128">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="5fd5e-129">ソリューションごとの 1 回限りのセットアップとして、メニューに`Test`移動し、`Test Settings` > `Default Processor Architecture` > `X64`を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-129">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="5fd5e-130">Visual Studio の既定のプロセッサ アーキテクチャ設定は、ソリューションごとに`.suo`ソリューション オプション ( ) ファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-130">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="5fd5e-131">このファイルを削除した場合は、プロセッサ アーキテクチャとして`X64`再度選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-131">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="5fd5e-132">プロジェクトをビルドし、メニューに`Test`移動して`Windows` > `Test Explorer`を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-132">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="5fd5e-133">`AllocateQubit`グループ内のテストのリストに表示されます`Not Run Tests`。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-133">`AllocateQubit` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="5fd5e-134">この`Run All`個々のテストを選択または実行すると、合格するはずです!</span><span class="sxs-lookup"><span data-stu-id="5fd5e-134">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="5fd5e-135">コマンドライン/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5fd5e-135">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="5fd5e-136">テストを実行するには、プロジェクト フォルダー (含まれている`Tests.csproj`フォルダー) に移動し、コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-136">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="5fd5e-137">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-137">You should get output similar to the following:</span></span>

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

<span data-ttu-id="5fd5e-138">単体テストは、名前や実行ターゲットに従ってフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-138">Unit tests can be filtered according to their name and/or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="5fd5e-139">組み込<xref:microsoft.quantum.intrinsic.message>み関数`(String -> Unit)`は型を持ち、診断メッセージの作成を可能にします。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-139">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="5fd5e-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="5fd5e-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="5fd5e-141">テスト エクスプローラーでテストを実行し、テストをクリックすると、テスト実行に関する情報がパネルに表示されます: 成功/失敗状態、経過時間、および 「出力」リンク。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-141">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="5fd5e-142">「出力」リンクをクリックすると、テスト出力が新しいウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-142">If you click the "Output" link, test output will open in a new window.</span></span>

![テスト出力](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="5fd5e-144">コマンドライン/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5fd5e-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="5fd5e-145">各テストの合格/不合格ステータスは、 によって`dotnet test`コンソールに出力されます。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="5fd5e-146">失敗したテストの場合、失敗の診断に役立つ出力もコンソールに出力されます。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="facts-and-assertions"></a><span data-ttu-id="5fd5e-147">事実とアサーション</span><span class="sxs-lookup"><span data-stu-id="5fd5e-147">Facts and Assertions</span></span>

<span data-ttu-id="5fd5e-148">Q# の関数には_論理的な_副作用がないため、出力型が空の組である関数を実行するその_他の種類_の効果は、Q# プログラム内からは観察`()`できません。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-148">Because functions in Q# have no _logical_ side effects, any _other kinds_ of effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="5fd5e-149">つまり、ターゲット マシンは、この省略が、次の Q# コードの動作を変更しないことを保証して戻る`()`関数を実行しないことを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-149">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="5fd5e-150">これにより、関数が`()`返される (つまり`Unit`) アサーションを埋め込み、ロジックを Q# プログラムにデバッグするための便利なツールになります。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-150">This makes functions returning `()` (i.e. `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="5fd5e-151">簡単な例を考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-151">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="5fd5e-152">このキーワード`fail`は、計算を進めないことを示し、Q# プログラムを実行しているターゲット マシンで例外を発生させます。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-152">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="5fd5e-153">定義上、この種のエラーは、`fail`ステートメントに到達した後にそれ以上の Q# コードが実行されないので、Q# 内からは観察できません。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-153">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="5fd5e-154">したがって、呼び出しを過ぎて`PositivityFact`進めば、その入力が正の値であったことが保証されます。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-154">Thus, if we proceed past a call to `PositivityFact`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="5fd5e-155">名前空間の関数を使用する場合と`PositivityFact`同じ動作[`Fact`](xref:microsoft.quantum.diagnostics.fact)を実装できること<xref:microsoft.quantum.diagnostics>に注意してください。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-155">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:microsoft.quantum.diagnostics.fact) function from the <xref:microsoft.quantum.diagnostics> namespace:</span></span>

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

<span data-ttu-id="5fd5e-156">一方 *、アサーション*はファクトと同様に使用されますが、ターゲット マシンの状態に依存する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-156">*Assertions*, on the other hand, are used similarly to facts, but may be dependent on the state of the target machine.</span></span> <span data-ttu-id="5fd5e-157">それに応じて、それらは操作として定義され、ファクトは(上記のように)関数として定義されます。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-157">Correspondingly, they are defined as operations, whereas facts are defined as functions (as above).</span></span>
<span data-ttu-id="5fd5e-158">この違いを理解するために、アサーション内でのファクトの次の使用を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-158">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="5fd5e-159">ここでは、使用できる量子ビットの<xref:microsoft.quantum.environment.getqubitsavailabletouse>数を返すために操作を使用しています。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-159">Here, we are using the operation <xref:microsoft.quantum.environment.getqubitsavailabletouse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="5fd5e-160">これは明らかにプログラムのグローバル状態とその実行環境に依存するので、私たちの定義は同様`AssertQubitsAreAvailable`に操作でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-160">As this clearly depends on the global state of the program and its execution environment, our definition of  `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="5fd5e-161">ただし、関数への入力として単純な`Bool`値を生成するために、そのグローバル状態を`Fact`使用できます。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-161">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="5fd5e-162">これらのアイデアに基づいて、[前奏曲は](xref:microsoft.quantum.libraries.standard.prelude)2つの特に有用な<xref:microsoft.quantum.intrinsic.assert>アサーション<xref:microsoft.quantum.intrinsic.assertprob>を`()`提供し、両方ともに操作としてモデル化されています.</span><span class="sxs-lookup"><span data-stu-id="5fd5e-162">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="5fd5e-163">これらのアサーションは、それぞれ、関心のある特定の測定、測定を実行する量子レジスタ、および仮説結果を記述するPauli演算子を取ります。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-163">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="5fd5e-164">シミュレーションで動作するターゲットマシンでは、[クローンなし定理](https://en.wikipedia.org/wiki/No-cloning_theorem)に縛られず、そのようなアサーションに渡されたレジスタを乱すことなく、そのような測定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-164">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="5fd5e-165">シミュレータは、上記の`PositivityFact`関数と同様に、実際には仮定の結果が観察されない場合に計算を中止することができます。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-165">A simulator can then, similar to the `PositivityFact` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

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

<span data-ttu-id="5fd5e-166">非クローニング定理が量子状態の検査を妨げる物理量子ハードウェアでは、および`Assert``AssertProb`操作は単に他の効果を`()`伴わなく戻ります。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-166">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="5fd5e-167">名前空間<xref:microsoft.quantum.diagnostics>は、より高度な条件を`Assert`チェックすることを可能にするファミリのいくつかのより多くの機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-167">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="5fd5e-168">ダンプ関数</span><span class="sxs-lookup"><span data-stu-id="5fd5e-168">Dump Functions</span></span>

<span data-ttu-id="5fd5e-169">クォンタム プログラムの<xref:microsoft.quantum.diagnostics>トラブルシューティングを支援するために、名前空間には、ターゲット マシンの現在の状態をファイルに<xref:microsoft.quantum.diagnostics.dumpmachine>ダンプ<xref:microsoft.quantum.diagnostics.dumpregister>できる 2 つの関数が用意されています。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-169">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="5fd5e-170">生成される出力は、ターゲット マシンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-170">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="5fd5e-171">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="5fd5e-171">DumpMachine</span></span>

<span data-ttu-id="5fd5e-172">量子開発キットの一部として配布されたフルステート量子シミュレータは、量子システム全体の[波動関数](https://en.wikipedia.org/wiki/Wave_function)を複素数の1次元配列としてファイルに書き込み、各要素は計算基準状態を測定する確率の振幅を表します。\ket{n}= \ket{b_{n-1}.ビット $b_i\}$\{のb_1b_0}$</span><span class="sxs-lookup"><span data-stu-id="5fd5e-172">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="5fd5e-173">たとえば、2 つの量子ビットのみが割り当てられ、量子状態のマシンでは、$$ \begin{align} \ket{\psi}{1}= \frac{2}{\sqrt} \ket{00} - \frac{(1 + i)}{2} \ケット{10}、\end{align} $$ 呼び出し<xref:microsoft.quantum.diagnostics.dumpmachine>は次の出力を生成します。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-173">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="5fd5e-174">最初の行は、対応する量子ビットの ID を重要な順序でコメントします。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-174">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="5fd5e-175">残りの行は、デカルト形式と極座標形式の両方で、基底状態ベクトル $\ket{n}$ を測定する確率振幅を表します。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-175">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="5fd5e-176">最初の行の詳細:</span><span class="sxs-lookup"><span data-stu-id="5fd5e-176">In detail for the first row:</span></span>

* <span data-ttu-id="5fd5e-177">**`∣0❭:`** この行は計算基準状態`0`に対応します</span><span class="sxs-lookup"><span data-stu-id="5fd5e-177">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="5fd5e-178">**`0.707107 +  0.000000 i`**: デカルト形式での確率振幅。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-178">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="5fd5e-179">**` == `**:`equal`符号は両方の等価表現を分け合います。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-179">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="5fd5e-180">**`**********  `**: 大きさをグラフィカルに表現した場合、`*`その数はこの状態ベクトルを測定する確率に比例します。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-180">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="5fd5e-181">**`[ 0.500000 ]`**: マグニチュードの数値</span><span class="sxs-lookup"><span data-stu-id="5fd5e-181">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="5fd5e-182">**`    ---`**: 振幅の位相をグラフィカルに表現します(下記参照)。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-182">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="5fd5e-183">**`[ 0.0000 rad ]`**: 位相の数値(ラジアン単位)。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-183">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="5fd5e-184">マグニチュードと位相の両方が、グラフィカルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-184">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="5fd5e-185">大きさ表現はまっすぐです:バーが表示され`*`、バーが大きくなる確率が大きくなります。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-185">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="5fd5e-186">フェーズでは、範囲に基づいて角度を表す次のシンボルを示します。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-186">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="5fd5e-187">次の例は`DumpMachine`、いくつかの一般的な状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-187">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="5fd5e-188">量子ビットの id は実行時に割り当てられ、必ずしも qubit が割り当てられた順序や qubit レジスタ内での位置と一致しません。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-188">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="5fd5e-189">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="5fd5e-189">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="5fd5e-190">Visual Studio で、コードにブレークポイントを設定し、qubit 変数の値を調べることによって、qubit id を把握できます。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-190">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![ビジュアルスタジオでクビット ID を表示する](~/media/qubit_id.png)
  >
  > <span data-ttu-id="5fd5e-192">`0`インデックスをオンに`register2`したクビットには`3`id= があり、インデックス`1`付きの`2`クビットは id= を持っています。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-192">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="5fd5e-193">コマンドライン/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5fd5e-193">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="5fd5e-194">関数を使用<xref:microsoft.quantum.intrinsic.message>して、メッセージに qubit 変数を渡すことによって、qubit id を把握できます。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-194">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="5fd5e-195">この出力を生成する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-195">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="5fd5e-196">`0`つまり、インデックスをオンに`register2`したクビットには id=`3`があり、インデックス`1`付きのク`2`ビットには id= があります。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-196">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="5fd5e-197"><xref:microsoft.quantum.diagnostics.dumpmachine>は名前空間の<xref:microsoft.quantum.diagnostics>一部であるため、これを使用するには、ステートメントを`open`追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-197"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="5fd5e-198">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="5fd5e-198">DumpRegister</span></span>

<span data-ttu-id="5fd5e-199"><xref:microsoft.quantum.diagnostics.dumpregister>同様<xref:microsoft.quantum.diagnostics.dumpmachine>に動作しますが、情報の量を対応する量子ビットに関連する情報のみに制限するために、量子ビットの配列を取ります。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-199"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="5fd5e-200">と同様<xref:microsoft.quantum.diagnostics.dumpmachine>に、によって<xref:microsoft.quantum.diagnostics.dumpregister>生成される情報はターゲット マシンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-200">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="5fd5e-201">フルステートクォンタム シミュレータの場合、ファイルに、指定された量子ビットによって生成される量子サブシステムのグローバルフェーズまで、波動関数を同じ形式で<xref:microsoft.quantum.diagnostics.dumpmachine>書き込みます。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-201">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="5fd5e-202">たとえば、 2 つの量子ビットのみが割り当てられ、量子状態のマシン $$ \begin{align} \ket{\psi} ={1}\frac{2}{\sqrt{00} } \ket - \frac{1 +{2} i)} \ket{10} = - e^{i\pi/4} ( (\frac{1}{\sqrt{1} {2}{0} <xref:microsoft.quantum.diagnostics.dumpregister> `qubit[0]` {2}} \ket{0} - \frac{(1 + i)}{2} \ケット ) \otimes \frac{-(1 + i)}{\sqrt } \ket) 、\end{align} 呼び出しを呼び出す $$ $$ この出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-202">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="5fd5e-203">を呼<xref:microsoft.quantum.diagnostics.dumpregister>`qubit[1]`び出すと、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-203">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="5fd5e-204">一般に、別のレジスタと絡み合うレジスタの状態は、純粋な状態ではなく混合状態です。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-204">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="5fd5e-205">この場合、<xref:microsoft.quantum.diagnostics.dumpregister>次のメッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-205">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="5fd5e-206">次の例は、Q# コード<xref:microsoft.quantum.diagnostics.dumpregister><xref:microsoft.quantum.diagnostics.dumpmachine>の両方を使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-206">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="5fd5e-207">デバッグ</span><span class="sxs-lookup"><span data-stu-id="5fd5e-207">Debugging</span></span>

<span data-ttu-id="5fd5e-208">関数と`Dump`操作`Assert`の上に、Q# は、標準的な Visual Studio デバッグ機能のサブセットをサポートしています:[行のブレークポイントを設定](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)する[、F10 を使用してコードをステップ実行](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)し、[クラシック変数の値を検査するすべての](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)シミュレータ上のコードの実行中に可能です。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-208">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="5fd5e-209">Visual Studio コードでのデバッグは、オムニシャープによって提供される Visual Studio コード拡張機能の C# によって提供されるデバッグ機能を活用し、[最新バージョン](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fd5e-209">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span> 
