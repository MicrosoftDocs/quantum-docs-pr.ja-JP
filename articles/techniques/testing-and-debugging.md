---
title: 'Q # プログラムのテストとデバッグ'
description: 単体テスト、ファクトとアサーション、およびダンプ関数を使用して、クォンタムプログラムをテストおよびデバッグする方法について説明します。
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 3df8df8defabcc9cc87d59f543f425c882b001e0
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907683"
---
# <a name="testing-and-debugging"></a><span data-ttu-id="c06c1-103">テストとデバッグ</span><span class="sxs-lookup"><span data-stu-id="c06c1-103">Testing and Debugging</span></span>

<span data-ttu-id="c06c1-104">従来のプログラミングと同様に、クォンタムプログラムが意図したとおりに動作することを確認し、正しくないクォンタムプログラムを診断できるようにすることが不可欠です。</span><span class="sxs-lookup"><span data-stu-id="c06c1-104">As with classical programming, it is essential to be able to check that quantum programs act as intended, and to be able to diagnose a quantum program that is incorrect.</span></span>
<span data-ttu-id="c06c1-105">このセクションでは、クォンタムプログラムをテストおよびデバッグするための Q # によって提供されるツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-105">In this section, we cover the tools offered by Q# for testing and debugging quantum programs.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="c06c1-106">単体テスト</span><span class="sxs-lookup"><span data-stu-id="c06c1-106">Unit Tests</span></span>

<span data-ttu-id="c06c1-107">クラシックプログラムをテストする一般的な方法の1つは、ライブラリ内のコードを実行する*単体テスト*と呼ばれる小さなプログラムを記述し、その出力を予想される出力と比較することです。</span><span class="sxs-lookup"><span data-stu-id="c06c1-107">One common approach to testing classical programs is to write small programs called *unit tests* which run code in a library and compare its output to some expected output.</span></span>
<span data-ttu-id="c06c1-108">たとえば、 *priori*が $ 2 ^ 2 = $4 であることがわかっているため、`Square(2)` が `4`を返すようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="c06c1-108">For instance, we may want to ensure that `Square(2)` returns `4`, since we know *a priori* that $2^2 = 4$.</span></span>

<span data-ttu-id="c06c1-109">Q # は、クォンタムプログラムの単体テストの作成をサポートしています。これは、 [Xunit](https://xunit.github.io/)単体テストフレームワーク内でテストとして実行できます。</span><span class="sxs-lookup"><span data-stu-id="c06c1-109">Q# supports creating unit tests for quantum programs, and which can be executed as tests within the [xUnit](https://xunit.github.io/) unit testing framework.</span></span>

### <a name="creating-a-test-project"></a><span data-ttu-id="c06c1-110">テストプロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="c06c1-110">Creating a Test Project</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="c06c1-111">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="c06c1-111">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="c06c1-112">Visual Studio 2019 を開きます。</span><span class="sxs-lookup"><span data-stu-id="c06c1-112">Open Visual Studio 2019.</span></span> <span data-ttu-id="c06c1-113">`File` メニューにアクセスし、[`New` > `Project...`] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-113">Go to the `File` menu and select `New` > `Project...`.</span></span>
<span data-ttu-id="c06c1-114">右上隅にある `Q#`を検索し、`Q# Test Project` テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-114">In the upper right corner, search for `Q#`, and select the `Q# Test Project` template.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="c06c1-115">コマンドライン/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c06c1-115">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="c06c1-116">お気に入りのコマンドラインから、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-116">From your favorite command line, run the following command:</span></span>
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

<span data-ttu-id="c06c1-117">新しいプロジェクトには、新しい Q # の単体テストを定義するための便利な場所を提供する、1つのファイル `Tests.qs`があります。</span><span class="sxs-lookup"><span data-stu-id="c06c1-117">Your new project will have a single file `Tests.qs`, which provides a convenient place to define new Q# unit tests.</span></span>
<span data-ttu-id="c06c1-118">初期状態では、このファイルには1つのサンプル単体テスト `AllocateQubit` が含まれています。これは、新しく割り当てられた qubit が $ \ket{0}$ 状態であることを確認し、メッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-118">Initially this file contains one sample unit test `AllocateQubit` which checks that a newly allocated qubit is in the $\ket{0}$ state and prints a message:</span></span>

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

<span data-ttu-id="c06c1-119">: new: `Unit` 型の引数を受け取り、`Unit` を返すすべての Q # 操作または関数は、`@Test("...")` 属性を使用して単体テストとしてマークできます。</span><span class="sxs-lookup"><span data-stu-id="c06c1-119">:new: Any Q# operation or function that takes an argument of type `Unit` and returns `Unit` can be marked as a unit test via the `@Test("...")` attribute.</span></span> <span data-ttu-id="c06c1-120">上記の `"QuantumSimulator"` 属性の引数は、テストを実行するターゲットを指定します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-120">The argument to that attribute, `"QuantumSimulator"` above, specifies the target on which the test is executed.</span></span> <span data-ttu-id="c06c1-121">1つのテストを複数のターゲットで実行できます。</span><span class="sxs-lookup"><span data-stu-id="c06c1-121">A single test can be executed on multiple targets.</span></span> <span data-ttu-id="c06c1-122">たとえば、`AllocateQubit`の上に `@Test("ResourcesEstimator")` 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-122">For example, add an attribute `@Test("ResourcesEstimator")` above `AllocateQubit`.</span></span> 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
<span data-ttu-id="c06c1-123">ファイルを保存し、すべてのテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-123">Save the file and execute all tests.</span></span> <span data-ttu-id="c06c1-124">ここで、2つの単体テストがあります。1つは、QuantumSimulator で AllocateQubit が実行され、もう1つは ResourceEstimator で実行されます。</span><span class="sxs-lookup"><span data-stu-id="c06c1-124">There should now be two unit tests, one where AllocateQubit is executed on the QuantumSimulator, and one where it is executed in the ResourceEstimator.</span></span> 

<span data-ttu-id="c06c1-125">Q # コンパイラは、組み込みのターゲット "QuantumSimulator"、"ToffoliSimulator"、および "ResourcesEstimator" を単体テストの有効な実行ターゲットとして認識します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-125">The Q# compiler recognizes the built-in targets "QuantumSimulator", "ToffoliSimulator", and "ResourcesEstimator" as valid execution targets for unit tests.</span></span> <span data-ttu-id="c06c1-126">また、任意の完全修飾名を指定して、カスタム実行ターゲットを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="c06c1-126">It is also possible to specify any fully qualified name to define a custom execution target.</span></span> 

### <a name="running-q-unit-tests"></a><span data-ttu-id="c06c1-127">Q # の単体テストの実行</span><span class="sxs-lookup"><span data-stu-id="c06c1-127">Running Q# Unit Tests</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="c06c1-128">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="c06c1-128">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="c06c1-129">ソリューションごとの1回限りの設定として、`Test` メニューにアクセスし、[`Test Settings` > `Default Processor Architecture` > `X64`] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-129">As a one-time per-solution setup, go to `Test` menu and select `Test Settings` > `Default Processor Architecture` > `X64`.</span></span>

> [!TIP]
> <span data-ttu-id="c06c1-130">Visual Studio の既定のプロセッサアーキテクチャ設定は、各ソリューションのソリューションオプション (`.suo`) ファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="c06c1-130">The default processor architecture setting for Visual Studio is stored in the solution options (`.suo`) file for each solution.</span></span>
> <span data-ttu-id="c06c1-131">このファイルを削除する場合は、プロセッサのアーキテクチャとして [`X64`] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c06c1-131">If you delete this file, then you will need to select `X64` as your processor architecture again.</span></span>

<span data-ttu-id="c06c1-132">プロジェクトをビルドし、[`Test`] メニューにアクセスして、[`Windows` > `Test Explorer`] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-132">Build the project, go to the `Test` menu and select `Windows` > `Test Explorer`.</span></span> <span data-ttu-id="c06c1-133">`Not Run Tests` グループ内のテストの一覧に `AllocateQubit` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c06c1-133">`AllocateQubit` will show up in the list of tests in the `Not Run Tests` group.</span></span> <span data-ttu-id="c06c1-134">`Run All` を選択するか、この個別のテストを実行して、合格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c06c1-134">Select `Run All` or run this individual test, and it should pass!</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="c06c1-135">コマンドライン/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c06c1-135">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="c06c1-136">テストを実行するには、プロジェクトフォルダー (`Tests.csproj`を含むフォルダー) に移動し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-136">To run tests, navigate to the project folder (the folder which contains `Tests.csproj`), and execute the command:</span></span>

```bash
$ dotnet restore
$ dotnet test
```

<span data-ttu-id="c06c1-137">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c06c1-137">You should get output similar to the following:</span></span>

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

<span data-ttu-id="c06c1-138">単体テストは、名前や実行ターゲットに応じてフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="c06c1-138">Unit tests can be filtered according to their name and/or the execution target:</span></span>

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

<span data-ttu-id="c06c1-139">組み込み関数 <xref:microsoft.quantum.intrinsic.message> 型 `(String -> Unit)` で、診断メッセージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c06c1-139">The intrinsic function <xref:microsoft.quantum.intrinsic.message> has type `(String -> Unit)` and enables the creation of diagnostic messages.</span></span>

#### <a name="visual-studio-2019"></a>[<span data-ttu-id="c06c1-140">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="c06c1-140">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

<span data-ttu-id="c06c1-141">テストエクスプローラーでテストを実行し、テストをクリックすると、テストの実行に関する情報がパネルに表示されます (成功/失敗の状態、経過時間、および "出力" リンク)。</span><span class="sxs-lookup"><span data-stu-id="c06c1-141">After you execute a test in Test Explorer and click on the test, a panel will appear with information about test execution: Passed/Failed status, elapsed time and an "Output" link.</span></span> <span data-ttu-id="c06c1-142">[出力] リンクをクリックすると、新しいウィンドウでテスト出力が開きます。</span><span class="sxs-lookup"><span data-stu-id="c06c1-142">If you click the "Output" link, test output will open in a new window.</span></span>

![テスト出力](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="c06c1-144">コマンドライン/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c06c1-144">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="c06c1-145">各テストの成功/失敗の状態は、`dotnet test`によってコンソールに出力されます。</span><span class="sxs-lookup"><span data-stu-id="c06c1-145">The pass/fail status for each test is printed to the console by `dotnet test`.</span></span>
<span data-ttu-id="c06c1-146">失敗したテストの場合は、エラーの診断に役立つ出力もコンソールに出力されます。</span><span class="sxs-lookup"><span data-stu-id="c06c1-146">For failing tests, the outputs are also printed to the console to help diagnose the failure.</span></span>

***

## <a name="facts-and-assertions"></a><span data-ttu-id="c06c1-147">ファクトとアサーション</span><span class="sxs-lookup"><span data-stu-id="c06c1-147">Facts and Assertions</span></span>

<span data-ttu-id="c06c1-148">Q # の関数には_論理的_な副作用がないため、出力の種類が空のタプルである関数を実行した場合の_その他の種類_の効果は、q # プログラム内からは観察されません `()`。</span><span class="sxs-lookup"><span data-stu-id="c06c1-148">Because functions in Q# have no _logical_ side effects, any _other kinds_ of effects of executing a function whose output type is the empty tuple `()` can never be observed from within a Q# program.</span></span>
<span data-ttu-id="c06c1-149">つまり、ターゲットコンピューターは、この省略によって次の Q # コードの動作が変更されないことを保証して `()` を返す関数を実行しないことを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c06c1-149">That is, a target machine can choose not to execute any function which returns `()` with the guarantee that this omission will not modify the behavior of any following Q# code.</span></span>
<span data-ttu-id="c06c1-150">これにより、`()` (つまり `Unit`) を返す関数が、アサーションの埋め込みや、Q # プログラムへのデバッグロジックに便利なツールになります。</span><span class="sxs-lookup"><span data-stu-id="c06c1-150">This makes functions returning `()` (i.e. `Unit`) a useful tool for embedding assertions and debugging logic into Q# programs.</span></span> 

<span data-ttu-id="c06c1-151">単純な例を考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="c06c1-151">Let's consider a simple example:</span></span>

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

<span data-ttu-id="c06c1-152">ここで、キーワード `fail` は、計算が続行されないことを示し、Q # プログラムを実行しているターゲットコンピューターで例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-152">Here, the keyword `fail` indicates that the computation should not proceed, raising an exception in the target machine running the Q# program.</span></span>
<span data-ttu-id="c06c1-153">定義上、Q # 内では、この種のエラーを確認することはできません。これは、`fail` ステートメントに達した後に、それ以上の Q # コードが実行されないためです。</span><span class="sxs-lookup"><span data-stu-id="c06c1-153">By definition, a failure of this kind cannot be observed from within Q#, as no further Q# code is run after a `fail` statement is reached.</span></span>
<span data-ttu-id="c06c1-154">したがって、`PositivityFact`の呼び出しを続けて実行した場合は、入力が肯定的であることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="c06c1-154">Thus, if we proceed past a call to `PositivityFact`, we can be assured by that its input was positive.</span></span>

<span data-ttu-id="c06c1-155"><xref:microsoft.quantum.diagnostics> 名前空間の[`Fact`](xref:microsoft.quantum.diagnostics.fact)関数を使用して `PositivityFact` と同じ動作を実装できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c06c1-155">Note that we can implement the same behavior as `PositivityFact` using the [`Fact`](xref:microsoft.quantum.diagnostics.fact) function from the <xref:microsoft.quantum.diagnostics> namespace:</span></span>

```qsharp
    Fact(value <= 0, "Expected a positive number.");
```

<span data-ttu-id="c06c1-156">一方、*アサーション*はファクトと同様に使用されますが、ターゲットコンピューターの状態に依存する場合があります。</span><span class="sxs-lookup"><span data-stu-id="c06c1-156">*Assertions*, on the other hand, are used similarly to facts, but may be dependent on the state of the target machine.</span></span> <span data-ttu-id="c06c1-157">それに応じて、これらは操作として定義されますが、ファクトは関数として定義されます (上記のように)。</span><span class="sxs-lookup"><span data-stu-id="c06c1-157">Correspondingly, they are defined as operations, whereas facts are defined as functions (as above).</span></span>
<span data-ttu-id="c06c1-158">この違いを理解するには、アサーション内で次のファクトを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="c06c1-158">To understand the distinction, consider the following use of a fact within an assertion:</span></span>

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

<span data-ttu-id="c06c1-159">ここでは、操作 <xref:microsoft.quantum.environment.getqubitsavailabletouse> を使用して、使用可能な qubits の数を返します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-159">Here, we are using the operation <xref:microsoft.quantum.environment.getqubitsavailabletouse> to return the number of qubits available to use.</span></span>
<span data-ttu-id="c06c1-160">これは、プログラムとその実行環境のグローバルな状態によって明確に依存しますが、`AssertQubitsAreAvailable` の定義も操作である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c06c1-160">As this clearly depends on the global state of the program and its execution environment, our definition of  `AssertQubitsAreAvailable` must be an operation as well.</span></span>
<span data-ttu-id="c06c1-161">ただし、そのグローバル状態を使用して、`Fact` 関数への入力として単純な `Bool` 値を生成することができます。</span><span class="sxs-lookup"><span data-stu-id="c06c1-161">However, we can use that global state to yield a simple `Bool` value as input to the `Fact` function.</span></span>

<span data-ttu-id="c06c1-162">これらのアイデアを基にして、準備には、`()`に対する操作としてモデル化さ[れた](xref:microsoft.quantum.libraries.standard.prelude)、<xref:microsoft.quantum.intrinsic.assert> と <xref:microsoft.quantum.intrinsic.assertprob> の2つの便利なアサーションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c06c1-162">Building on these ideas, [the prelude](xref:microsoft.quantum.libraries.standard.prelude) offers two especially useful assertions, <xref:microsoft.quantum.intrinsic.assert> and <xref:microsoft.quantum.intrinsic.assertprob> both modeled as operations onto `()`.</span></span> <span data-ttu-id="c06c1-163">これらのアサーションは、特定の対象測定、測定を実行するクォンタムレジスタ、および仮定の結果を記述する P# li オペレーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c06c1-163">These assertions each take a Pauli operator describing a particular measurement of interest, a quantum register on which a measurement is to be performed, and a hypothetical outcome.</span></span>
<span data-ttu-id="c06c1-164">シミュレーションによって動作するターゲットコンピューターでは、[複製なしの定理](https://en.wikipedia.org/wiki/No-cloning_theorem)によってバインドされていないため、このようなアサーションに渡されたレジスタに支障をきたすことなく、このような測定を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c06c1-164">On target machines which work by simulation, we are not bound by [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem), and can perform such measurements without disturbing the register passed to such assertions.</span></span>
<span data-ttu-id="c06c1-165">シミュレーターは、上記の `PositivityFact` 関数と同様に、実際の結果が実際に観察されない場合に計算を中止できます。</span><span class="sxs-lookup"><span data-stu-id="c06c1-165">A simulator can then, similar to the `PositivityFact` function above, abort computation if the hypothetical outcome would not be observed in practice:</span></span>

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

<span data-ttu-id="c06c1-166">物理的なクォンタムハードウェアでは、複製なしの定理がクォンタムの状態を検査できない場合、`Assert` 操作と `AssertProb` 操作は単に `()` を返します。これ以外の影響はありません。</span><span class="sxs-lookup"><span data-stu-id="c06c1-166">On physical quantum hardware, where the no-cloning theorem prevents examination of quantum state, the `Assert` and `AssertProb` operations simply return `()` with no other effect.</span></span>

<span data-ttu-id="c06c1-167"><xref:microsoft.quantum.diagnostics> 名前空間には、より高度な条件をチェックできるようにする、`Assert` ファミリの機能がいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="c06c1-167">The <xref:microsoft.quantum.diagnostics> namespace provides several more functions of the `Assert` family which allow us to check more advanced conditions.</span></span> 

## <a name="dump-functions"></a><span data-ttu-id="c06c1-168">ダンプ関数</span><span class="sxs-lookup"><span data-stu-id="c06c1-168">Dump Functions</span></span>

<span data-ttu-id="c06c1-169">クォンタムプログラムのトラブルシューティングに役立つように、<xref:microsoft.quantum.diagnostics> 名前空間には、ターゲットコンピューターの現在の状態をファイルにダンプできる2つの関数 (<xref:microsoft.quantum.diagnostics.dumpmachine> と <xref:microsoft.quantum.diagnostics.dumpregister>) が用意されています。</span><span class="sxs-lookup"><span data-stu-id="c06c1-169">To help troubleshooting quantum programs, the <xref:microsoft.quantum.diagnostics> namespace offers two functions that can dump into a file the current status of the target machine: <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister>.</span></span> <span data-ttu-id="c06c1-170">それぞれのの生成された出力は、ターゲットコンピューターによって異なります。</span><span class="sxs-lookup"><span data-stu-id="c06c1-170">The generated output of each depends on the target machine.</span></span>

### <a name="dumpmachine"></a><span data-ttu-id="c06c1-171">DumpMachine</span><span class="sxs-lookup"><span data-stu-id="c06c1-171">DumpMachine</span></span>

<span data-ttu-id="c06c1-172">Quantum 開発キットの一部として配布された完全な状態のクォンタムシミュレーターは、クォンタムシステム全体の[wave 関数](https://en.wikipedia.org/wiki/Wave_function)を、1次元の複素数の配列としてファイルに書き込みます。各要素は、コンピューティングベースの状態を測定する確率の振幅 ($ \ket{n} = \ket{b_ {n-1}...) を表します。b_1b_0} $ for bits $\{b_i\}$。</span><span class="sxs-lookup"><span data-stu-id="c06c1-172">The full-state quantum simulator distributed as part of the Quantum Development Kit writes into the file the [wave function](https://en.wikipedia.org/wiki/Wave_function) of the entire quantum system, as a one-dimensional array of complex numbers, in which each element represents the amplitude of the probability of measuring the computational basis state $\ket{n}$, where $\ket{n} = \ket{b_{n-1}...b_1b_0}$ for bits $\{b_i\}$.</span></span> <span data-ttu-id="c06c1-173">たとえば、2つの qubits のみが割り当てられていて、クォンタム状態が $ $ \begin{align} \ket{\psi}{2}{1}= \ket{00}-\frac{(1 + i)}{2} \ket{10}であるコンピューターでは、\end{align} $ $ が <xref:microsoft.quantum.diagnostics.dumpmachine> を呼び出すと、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="c06c1-173">For example, on a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10}, \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpmachine> generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="c06c1-174">最初の行は、対応する qubits の Id を持つコメントを有意な順序で提供します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-174">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="c06c1-175">残りの行は、デカルト形式と極座標形式の両方で、basis 状態ベクター $ \ket{n} $ を測定する確率の振幅を示しています。</span><span class="sxs-lookup"><span data-stu-id="c06c1-175">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{n}$ in both Cartesian and polar formats.</span></span> <span data-ttu-id="c06c1-176">最初の行の詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c06c1-176">In detail for the first row:</span></span>

* <span data-ttu-id="c06c1-177">この行 **`∣0❭:`** `0` の計算基準の状態に対応します</span><span class="sxs-lookup"><span data-stu-id="c06c1-177">**`∣0❭:`** this row corresponds to the `0` computational basis state</span></span>
* <span data-ttu-id="c06c1-178">**`0.707107 +  0.000000 i`** : デカルト形式の確率の振幅。</span><span class="sxs-lookup"><span data-stu-id="c06c1-178">**`0.707107 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="c06c1-179">**` == `** : `equal` sign は、両方の同等表現を seperates します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-179">**` == `**: the `equal` sign seperates both equivalent representations.</span></span>
* <span data-ttu-id="c06c1-180">**`**********  `** : 大きさをグラフィカルに表現したもので、`*` の数は、この状態ベクターを測定する確率に比例します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-180">**`**********  `**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span>
* <span data-ttu-id="c06c1-181">**`[ 0.500000 ]`** : 大きさの数値</span><span class="sxs-lookup"><span data-stu-id="c06c1-181">**`[ 0.500000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="c06c1-182">**`    ---`** : 振幅のフェーズをグラフィックで表現したもの (下記参照)。</span><span class="sxs-lookup"><span data-stu-id="c06c1-182">**`    ---`**: A graphical representation of the amplitude's phase (see below).</span></span>
* <span data-ttu-id="c06c1-183">**`[ 0.0000 rad ]`** : フェーズの数値 (ラジアン)。</span><span class="sxs-lookup"><span data-stu-id="c06c1-183">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="c06c1-184">大きさとフェーズの両方がグラフィック表示で表示されます。</span><span class="sxs-lookup"><span data-stu-id="c06c1-184">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="c06c1-185">マグニチュード表現は、水平方向であり、`*`の棒を示すので、棒が大きくなる確率が大きくなります。</span><span class="sxs-lookup"><span data-stu-id="c06c1-185">The magnitude representation is straight-forward: it shows a bar of `*`, the bigger the probability the bigger the bar will be.</span></span> <span data-ttu-id="c06c1-186">フェーズでは、次の記号を使用して範囲に基づく角度を表します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-186">For the phase, we show the following symbols to represent the angle based on ranges:</span></span>

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

<span data-ttu-id="c06c1-187">次の例は、いくつかの一般的な状態の `DumpMachine` を示しています。</span><span class="sxs-lookup"><span data-stu-id="c06c1-187">The following examples show `DumpMachine` for some common states:</span></span>

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
  > <span data-ttu-id="c06c1-188">Qubit の id は実行時に割り当てられ、必ずしも qubit が割り当てられた順序、または qubit レジスタ内の位置に一致するとは限りません。</span><span class="sxs-lookup"><span data-stu-id="c06c1-188">The id of a qubit is assigned at runtime and it's not necessarily aligned with the order in which the qubit was allocated or its position within a qubit register.</span></span>


#### <a name="visual-studio-2019"></a>[<span data-ttu-id="c06c1-189">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="c06c1-189">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

  > [!TIP]
  > <span data-ttu-id="c06c1-190">コードにブレークポイントを配置し、qubit 変数の値を調べることで、Visual Studio で qubit id を調べることができます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-190">You can figure out a qubit id in Visual Studio by putting a breakpoint in your code and inspecting the value of a qubit variable, for example:</span></span>
  > 
  > ![Visual Studio での qubit id の表示](~/media/qubit_id.png)
  >
  > <span data-ttu-id="c06c1-192">`register2` のインデックス `0` を持つ qubit の id =`3`、インデックス `1` の qubit には id =`2`が使用されています。</span><span class="sxs-lookup"><span data-stu-id="c06c1-192">the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="c06c1-193">コマンドライン/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c06c1-193">Command Line / Visual Studio Code</span></span>](#tab/tabid-vscode)

  > [!TIP]
  > <span data-ttu-id="c06c1-194"><xref:microsoft.quantum.intrinsic.message> 関数を使用し、メッセージに qubit 変数を渡すことによって、qubit id を確認できます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-194">You can figure out a qubit id by using the <xref:microsoft.quantum.intrinsic.message> function and passing the qubit variable in the message, for example:</span></span>
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > <span data-ttu-id="c06c1-195">次のような出力が生成できます。</span><span class="sxs-lookup"><span data-stu-id="c06c1-195">which could generate this output:</span></span>
  >```
  > 0=q:3; 1=q:2
  >```
  > <span data-ttu-id="c06c1-196">これは、`register2` のインデックス `0` が指定された qubit に id =`3`があることを意味します。これは、インデックス `1` の qubit の id が`2`であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-196">which means that the qubit with index `0` on `register2` has id=`3`, the qubit with index `1` has id=`2`.</span></span>


***

<span data-ttu-id="c06c1-197"><xref:microsoft.quantum.diagnostics.dumpmachine> は <xref:microsoft.quantum.diagnostics> 名前空間の一部であるため、これを使用するには `open` ステートメントを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c06c1-197"><xref:microsoft.quantum.diagnostics.dumpmachine> is part of the  <xref:microsoft.quantum.diagnostics> namespace, so in order to use it you must add an `open` statement:</span></span>

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


### <a name="dumpregister"></a><span data-ttu-id="c06c1-198">DumpRegister</span><span class="sxs-lookup"><span data-stu-id="c06c1-198">DumpRegister</span></span>

<span data-ttu-id="c06c1-199"><xref:microsoft.quantum.diagnostics.dumpregister> は <xref:microsoft.quantum.diagnostics.dumpmachine>のように機能しますが、情報の量を対応する qubits にのみ制限するために、qubits の配列を受け取る点が異なります。</span><span class="sxs-lookup"><span data-stu-id="c06c1-199"><xref:microsoft.quantum.diagnostics.dumpregister> works like <xref:microsoft.quantum.diagnostics.dumpmachine>, except it also takes an array of qubits to limit the amount of information to only that relevant to the corresponding qubits.</span></span>

<span data-ttu-id="c06c1-200"><xref:microsoft.quantum.diagnostics.dumpmachine>と同様に、<xref:microsoft.quantum.diagnostics.dumpregister> によって生成される情報はターゲットコンピューターによって異なります。</span><span class="sxs-lookup"><span data-stu-id="c06c1-200">As with <xref:microsoft.quantum.diagnostics.dumpmachine>, the information generated by <xref:microsoft.quantum.diagnostics.dumpregister> depends on the target machine.</span></span> <span data-ttu-id="c06c1-201">完全な状態のクォンタムシミュレーターでは、ファイルに書き込みます。これは、指定された qubits によって生成されるクォンタムサブシステムのグローバルフェーズまで、wave 関数を <xref:microsoft.quantum.diagnostics.dumpmachine>と同じ形式で作成します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-201">For the full-state quantum simulator it writes into the file the wave function up to a global phase of the quantum sub-system generated by the provided qubits in the same format as <xref:microsoft.quantum.diagnostics.dumpmachine>.</span></span>  <span data-ttu-id="c06c1-202">たとえば、2つの qubits のみが割り当てられ、クォンタム状態が $ $ \begin{align} \ket{\psi} = \ frac{1}{\ sqrt{2}} \ket{00}-\frac{(1 + i)}{2} \ket{10} =-e ^ {-であるマシンをもう一度実行します。 i \ pi/4} ((\ket{0}-\frac{(1 + i)}{2} \ket{1})、otimes \frac{-(1 + i)} {\ sqrt{2}} \ket{0})、、およびです。{2}{1}\end{align} $ $ `qubit[0]` の <xref:microsoft.quantum.diagnostics.dumpregister> を呼び出すと、この出力が生成されます:</span><span class="sxs-lookup"><span data-stu-id="c06c1-202">For example, take again a machine with only two qubits allocated and in the quantum state $$ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00} - \frac{(1 + i)}{2} \ket{10} = - e^{-i\pi/4} ( (\frac{1}{\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket{0} ) , \end{align} $$ calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[0]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<span data-ttu-id="c06c1-203">また、`qubit[1]` の <xref:microsoft.quantum.diagnostics.dumpregister> を呼び出すと、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="c06c1-203">and calling <xref:microsoft.quantum.diagnostics.dumpregister> for `qubit[1]` generates this output:</span></span>

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

<span data-ttu-id="c06c1-204">一般に、別のレジスタによって使用されるレジスタの状態は、純粋な状態ではなく混合状態になります。</span><span class="sxs-lookup"><span data-stu-id="c06c1-204">In general, the state of a register that is entangled with another register is a mixed state rather than a pure state.</span></span> <span data-ttu-id="c06c1-205">この場合、<xref:microsoft.quantum.diagnostics.dumpregister> は次のメッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-205">In this case, <xref:microsoft.quantum.diagnostics.dumpregister> outputs the following message:</span></span>

```
Qubits provided (0;) are entangled with some other qubit.
```

<span data-ttu-id="c06c1-206">次の例では、Q # コードで <xref:microsoft.quantum.diagnostics.dumpregister> と <xref:microsoft.quantum.diagnostics.dumpmachine> の両方を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c06c1-206">The following example shows you how you can use both <xref:microsoft.quantum.diagnostics.dumpregister> and <xref:microsoft.quantum.diagnostics.dumpmachine> in your Q# code:</span></span>

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

## <a name="debugging"></a><span data-ttu-id="c06c1-207">デバッグ</span><span class="sxs-lookup"><span data-stu-id="c06c1-207">Debugging</span></span>

<span data-ttu-id="c06c1-208">`Assert` および `Dump` 関数と操作の上で、Q # は標準の Visual Studio デバッグ機能のサブセットをサポートしています。[行のブレークポイントの設定](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)、 [F10 を使用](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)したコードのステップ実行、および[クラシック変数の値の検査](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)は、シミュレーターでのコードの実行中に可能です。</span><span class="sxs-lookup"><span data-stu-id="c06c1-208">On top of `Assert` and `Dump` functions and operations, Q# supports a subset of standard Visual Studio debugging capabilities: [setting line breakpoints](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [stepping through code using F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) and [inspecting values of classic variables](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) are all possible during code execution on the simulator.</span></span>

<span data-ttu-id="c06c1-209">Visual Studio Code でのデバッグでは、 C# OmniSharp による Visual Studio Code 拡張機能によって提供されるデバッグ機能を活用し、[最新バージョン](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c06c1-209">Debugging in Visual Studio Code leverages the debugging capabilities provided by the C# for Visual Studio Code extension powered by OmniSharp and requires installing the [latest version](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span> 
