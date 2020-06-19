---
title: Q# でのエンタングルメントの確認
description: Q# で量子プログラムを作成する方法について説明します。 Quantum Development Kit (QDK) を使用してベル状態アプリケーションを開発する
author: natke
ms.author: nakersha
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 271eb7f496835f152573be930d0fe24e59f2d15d
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630085"
---
# <a name="tutorial-explore-entanglement-with-q"></a><span data-ttu-id="9efeb-104">チュートリアル:Q\# でのもつれの確認</span><span class="sxs-lookup"><span data-stu-id="9efeb-104">Tutorial: Explore entanglement with Q\#</span></span>

<span data-ttu-id="9efeb-105">このチュートリアルでは、量子ビットの操作および測定を行い、重ね合わせともつれの効果を示す、Q# プログラムの作成方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-105">In this tutorial, we show you how to write a Q# program that manipulates and measures qubits and demonstrates the effects of superposition and entanglement.</span></span>
<span data-ttu-id="9efeb-106">このガイドでは、QDK をインストールし、プログラムをビルドして、そのプログラムを量子シミュレーターで実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-106">This guides you on installing the QDK, building the program and executing that program on a quantum simulator.</span></span>  

<span data-ttu-id="9efeb-107">量子のもつれを示すため、Bell というアプリケーションを記述します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-107">You will write an application called Bell to demonstrate quantum entanglement.</span></span>
<span data-ttu-id="9efeb-108">Bell という名前は、ベル状態を表しています。これは、量子の重ね合わせともつれの最も簡単な例を表すために使用される、2 つの量子ビットの特定の量子の状態です。</span><span class="sxs-lookup"><span data-stu-id="9efeb-108">The name Bell is in reference to Bell states, which are specific quantum states of two qubits that are used to represent the simplest examples of superposition and quantum entanglement.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9efeb-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="9efeb-109">Prerequisites</span></span>

<span data-ttu-id="9efeb-110">コーディングを開始する準備ができたら、続行する前に次の手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="9efeb-110">If you are ready to start coding, follow these steps before proceeding:</span></span> 

* <span data-ttu-id="9efeb-111">[Python](xref:microsoft.quantum.install.python) または [.NET](xref:microsoft.quantum.install.cs) 用の Quantum Development Kit をインストールします。</span><span class="sxs-lookup"><span data-stu-id="9efeb-111">Install the Quantum Development Kit for [Python](xref:microsoft.quantum.install.python) or [.NET](xref:microsoft.quantum.install.cs).</span></span>
* <span data-ttu-id="9efeb-112">既に QDK をインストールしている場合は、バージョンが[最新](xref:microsoft.quantum.update)であることを確認する</span><span class="sxs-lookup"><span data-stu-id="9efeb-112">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>

<span data-ttu-id="9efeb-113">QDK をインストールしなくても、説明を読み進めることで Q# プログラミング言語の概要と量子コンピューティングの最初の概念を理解することができます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-113">You can also follow along with the narrative without installing the QDK, reviewing the overviews of the Q# programming language and the first concepts of quantum computing.</span></span>

## <a name="demonstrating-qubit-behavior-with-q"></a><span data-ttu-id="9efeb-114">Q# を使った量子ビットの動作のデモ</span><span class="sxs-lookup"><span data-stu-id="9efeb-114">Demonstrating qubit behavior with Q#</span></span>

<span data-ttu-id="9efeb-115">簡単な[量子ビットの定義](xref:microsoft.quantum.overview.understanding)を思い出してください。</span><span class="sxs-lookup"><span data-stu-id="9efeb-115">Recall our simple [definition of a qubit](xref:microsoft.quantum.overview.understanding).</span></span>  <span data-ttu-id="9efeb-116">従来のビットでは単一のバイナリ値 (0、1 など) が保持されるのに対し、[量子ビット](xref:microsoft.quantum.glossary#qubit)の状態は 0 と 1 の**重ね合わせ**になることができます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-116">Where classical bits hold a single binary value such as a 0 or 1, the state of a [qubit](xref:microsoft.quantum.glossary#qubit) can be in a **superposition** of 0 and 1.</span></span>  <span data-ttu-id="9efeb-117">概念的には、量子ビットは空間内の方向 (ベクトルとも呼ばれます) と考えられます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-117">Conceptually, a qubit can be thought of as a direction in space (also known as a vector).</span></span>  <span data-ttu-id="9efeb-118">量子ビットは、任意の方向にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-118">A qubit can be in any of the possible directions.</span></span> <span data-ttu-id="9efeb-119">2 つの**従来の状態**とは、0 を測定する確率が 100% になる方向と、1 を測定する確率が 100% になる方向のことです。</span><span class="sxs-lookup"><span data-stu-id="9efeb-119">The two **classical states** are the two directions; representing 100% chance of measuring 0 and 100% chance of measuring 1.</span></span>  <span data-ttu-id="9efeb-120">この表現は、[ブロッホ球](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere)によってより正式に視覚化されます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-120">This representation is also more formally visualized by the [bloch sphere](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span></span>

<span data-ttu-id="9efeb-121">測定の動作により、2 進法の結果が生成され、量子ビットの状態が変わります。</span><span class="sxs-lookup"><span data-stu-id="9efeb-121">The act of measurement produces a binary result and changes a qubit state.</span></span> <span data-ttu-id="9efeb-122">測定では、0 または 1 のバイナリ値が生成されます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-122">Measurement produces a binary value, either 0 or 1.</span></span>  <span data-ttu-id="9efeb-123">量子ビットは重ね合わせ (あらゆる方向にある) の状態から古典的状態のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="9efeb-123">The qubit goes from being in superposition (any direction) to one of the classical states.</span></span>  <span data-ttu-id="9efeb-124">その後、介在する操作なしで同じ測定を繰り返すと、同じ 2 進数の結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-124">Thereafter, repeating the same measurement without any intervening operations produces the same binary result.</span></span>  

<span data-ttu-id="9efeb-125">複数の量子ビットは[**もつれさせる**](xref:microsoft.quantum.glossary#entanglement)ことができます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-125">Multiple qubits can be [**entangled**](xref:microsoft.quantum.glossary#entanglement).</span></span> <span data-ttu-id="9efeb-126">もつれのある 1 つの量子ビットを測定すると、もう一方の量子ビットの状態に関する知識も更新されます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-126">When we make a measurement of one entangled qubit, our knowledge of the state of the other(s) is updated as well.</span></span>

<span data-ttu-id="9efeb-127">これで、Q# がこの動作を表現する方法を説明できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9efeb-127">Now, we're ready to demonstrate how Q# expresses this behavior.</span></span>  <span data-ttu-id="9efeb-128">考えられる最も単純なプログラムから始め、量子の重ね合わせと量子のもつれを表すように構築します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-128">You start with the simplest program possible and build it up to demonstrate quantum superposition and quantum entanglement.</span></span>

## <a name="setup"></a><span data-ttu-id="9efeb-129">セットアップ</span><span class="sxs-lookup"><span data-stu-id="9efeb-129">Setup</span></span>

<span data-ttu-id="9efeb-130">このチュートリアルでは、ホスト プログラムを使用し、次の 2 つの部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-130">This tutorial uses a host programs and consists of two parts:</span></span>

1. <span data-ttu-id="9efeb-131">一連の量子アルゴリズム。Q# 量子プログラミング言語を使用して実装します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-131">A series of quantum algorithms, implemented using the Q# quantum programming language.</span></span>
1. <span data-ttu-id="9efeb-132">Python または C# で実装するホスト プログラム。メイン エントリ ポイントとして機能し、Q# 操作を呼び出して量子アルゴリズムを実行します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-132">A host program, implemented in either Python or C#, that serves as the main entry point and invokes Q# operations to execute the quantum algorithms.</span></span>

#### <a name="python"></a>[<span data-ttu-id="9efeb-133">Python</span><span class="sxs-lookup"><span data-stu-id="9efeb-133">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="9efeb-134">アプリケーションを格納する場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-134">Choose a location for your application</span></span>

1. <span data-ttu-id="9efeb-135">`Bell.qs`という名前でファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-135">Create a file called `Bell.qs`.</span></span> <span data-ttu-id="9efeb-136">このファイルには、Q# コードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-136">This file will contain your Q# code.</span></span>

1. <span data-ttu-id="9efeb-137">`host.py`という名前でファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-137">Create a file called `host.py`.</span></span> <span data-ttu-id="9efeb-138">このファイルには、Python ホスト コードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-138">This file will contain your Python host code.</span></span>

#### <a name="c-command-line"></a>[<span data-ttu-id="9efeb-139">C# コマンド ライン</span><span class="sxs-lookup"><span data-stu-id="9efeb-139">C# Command Line</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="9efeb-140">新しい Q# プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="9efeb-140">Create a new Q# project:</span></span>

    ```
    dotnet new console -lang Q# --output Bell
    cd Bell
    ```

    <span data-ttu-id="9efeb-141">`.csproj` ファイル、`Operations.qs` という名前の Q# ファイル、および `Driver.cs` という名前のホスト プログラム ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-141">You should see a `.csproj` file, a Q# file called `Operations.qs`, and a host program file called `Driver.cs`</span></span>

1. <span data-ttu-id="9efeb-142">Q# ファイルの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="9efeb-142">Rename the Q# file</span></span>

    ```
    mv Operation.qs Bell.qs
    ```

#### <a name="visual-studio"></a>[<span data-ttu-id="9efeb-143">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9efeb-143">Visual Studio</span></span>](#tab/tabid-vs2019)

1. <span data-ttu-id="9efeb-144">新しいプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="9efeb-144">Create a new project</span></span>

   * <span data-ttu-id="9efeb-145">Visual Studio を開きます</span><span class="sxs-lookup"><span data-stu-id="9efeb-145">Open Visual Studio</span></span>
   * <span data-ttu-id="9efeb-146">**[ファイル]** メニューで、 **[新規作成]**  ->  **[プロジェクト...]** の順に選択します</span><span class="sxs-lookup"><span data-stu-id="9efeb-146">Go to the **File** menu and select **New** -> **Project...**</span></span>
   * <span data-ttu-id="9efeb-147">プロジェクト テンプレート エクスプローラーの検索フィールドに「`Q#`」と入力し、`Q# Application` のテンプレートを選択します</span><span class="sxs-lookup"><span data-stu-id="9efeb-147">In the project template explorer, type `Q#` into the search field and select the `Q# Application` template</span></span>
   * <span data-ttu-id="9efeb-148">プロジェクトに `Bell` という名前を付けます</span><span class="sxs-lookup"><span data-stu-id="9efeb-148">Give your project the name `Bell`</span></span>

1. <span data-ttu-id="9efeb-149">Q# ファイルの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="9efeb-149">Rename the Q# file</span></span>

   * <span data-ttu-id="9efeb-150">**ソリューション エクスプローラー**に移動します</span><span class="sxs-lookup"><span data-stu-id="9efeb-150">Navigate to the **Solution Explorer**</span></span>
   * <span data-ttu-id="9efeb-151">`Operations.qs` ファイルを右クリックします</span><span class="sxs-lookup"><span data-stu-id="9efeb-151">Right click on the `Operations.qs` file</span></span>
   * <span data-ttu-id="9efeb-152">名前を `Bell.qs` に変更します</span><span class="sxs-lookup"><span data-stu-id="9efeb-152">Rename it to `Bell.qs`</span></span>

* * *

## <a name="write-a-q-operation"></a><span data-ttu-id="9efeb-153">Q# 操作を記述する</span><span class="sxs-lookup"><span data-stu-id="9efeb-153">Write a Q# operation</span></span>

<span data-ttu-id="9efeb-154">私たちの目標は、Q# を使って量子ビットを操作してその状態を変更するための、特定の量子の状態にある 2 つの量子ビットを準備し、重ね合わせともつれの効果を示すことです。</span><span class="sxs-lookup"><span data-stu-id="9efeb-154">Our goal is to prepare two qubits in a specific quantum state, demonstrating how to operate on qubits with Q# to change their state and demonstrate the effects of superposition and entanglement.</span></span> <span data-ttu-id="9efeb-155">ここでは、量子ビットの状態や操作、測定について示しつつ、少しずつ構築していきます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-155">We will build this up piece by piece to demonstrate qubit states, operations, and measurement.</span></span>

<span data-ttu-id="9efeb-156">**概要:** 以下に示す最初のコードは、Q# で量子ビットを操作する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9efeb-156">**Overview:**  In the first code below, we show you how to work with qubits in Q#.</span></span>  <span data-ttu-id="9efeb-157">ここでは、量子ビットの状態を変換する 2 つの操作、`M` と `X` を紹介します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-157">We’ll introduce two operations, `M` and `X` that transform the state of a qubit.</span></span> 

<span data-ttu-id="9efeb-158">このコード スニペットでは、量子ビットをパラメーターと見なす操作 `Set` が定義されています。もう 1 つのパラメーター `desired` は量子ビットが目的とする状態を表しています。</span><span class="sxs-lookup"><span data-stu-id="9efeb-158">In this code snippet, an operation `Set` is defined that takes as a parameter a qubit and another parameter, `desired`, representing the state that we would like the qubit to be in.</span></span>  <span data-ttu-id="9efeb-159">操作 `Set` は、操作 `M` を使用して、量子ビットに対する測定を実行します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-159">The operation `Set` performs a measurement on the qubit using the operation `M`.</span></span>  <span data-ttu-id="9efeb-160">Q# では量子ビットの測定では常に `Zero` または `One` のどちらかが返されます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-160">In Q#, a qubit measurement always returns either  `Zero` or `One`.</span></span>  <span data-ttu-id="9efeb-161">測定値が目的の値と等しくない値を返す場合は、量子ビットを "反転" させます。つまり、`X` 操作を実行します。これにより、量子ビットの状態は、測定で `Zero` と `One` を返す確率が逆になる新しい状態に変更されます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-161">If the measurement returns a value not equal to a desired value, Set “flips” the qubit; that is, it executes an `X` operation, which changes the qubit state to a new state in which the probabilities of a measurement returning `Zero` and `One` are reversed.</span></span>  <span data-ttu-id="9efeb-162">`Set` 操作の効果を示すため、`TestBellState` 操作を追加します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-162">To demonstrate the effect of the `Set` operation, a `TestBellState` operation is then added.</span></span>  <span data-ttu-id="9efeb-163">この操作では、`Zero` または `One` を入力として受け取り、その入力で `Set` 操作を何回か呼び出して、`Zero` が量子ビットの測定から返された回数と `One` が返された回数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="9efeb-163">This operation takes as input a `Zero` or `One`, and calls the `Set` operation some number of times with that input, and counts the number of times that `Zero` was returned from the measurement of the qubit and the number of times that `One` was returned.</span></span> <span data-ttu-id="9efeb-164">当然ながら、`TestBellState` 操作のこの最初のシミュレーションでは、`Zero` がパラメーターとして設定された量子ビットのすべての測定で `Zero` を返し、`One` がパラメーターとして設定された量子ビットのすべての測定で `One` を返すことが想定されます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-164">Of course, in this first simulation of the `TestBellState` operation, we expect that the output will show that all measurements of the qubit set with `Zero` as the parameter input will return `Zero`, and all measurements of a qubit set with `One` as the parameter input will return `One`.</span></span>  <span data-ttu-id="9efeb-165">さらに、重ね合わせともつれを示すコードを `TestBellState` に追加します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-165">Further on, we’ll add code to `TestBellState` to demonstrating superposition and entanglement.</span></span>


### <a name="q-operation-code"></a><span data-ttu-id="9efeb-166">Q# 操作コード</span><span class="sxs-lookup"><span data-stu-id="9efeb-166">Q# operation code</span></span>

1. <span data-ttu-id="9efeb-167">Bell.qs ファイルの内容を次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-167">Replace the contents of the Bell.qs file with the following code:</span></span>

    ```qsharp
    namespace Quantum.Bell {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation Set(desired : Result, q1 : Qubit) : Unit {
            if (desired != M(q1)) {
                X(q1);
            }
        }
    }
    ```

    <span data-ttu-id="9efeb-168">この操作により、量子ビットが従来の状態に設定されます。つまり、`Zero` が 100% 返されるか、`One` が 100% 返されるかのどちらかです。</span><span class="sxs-lookup"><span data-stu-id="9efeb-168">This operation may now be called to set a qubit to a classical state, either returning `Zero` 100% of the time or returning `One` 100% of the time.</span></span>  <span data-ttu-id="9efeb-169">`Zero` および `One` は、量子ビットの測定結果として考えられる 2 とおりの結果を表す定数です。</span><span class="sxs-lookup"><span data-stu-id="9efeb-169">`Zero` and `One` are constants that represent the only two possible results of a measurement of a qubit.</span></span>

    <span data-ttu-id="9efeb-170">`Set` 操作で量子ビットが測定されます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-170">The operation `Set` measures the qubit.</span></span>
    <span data-ttu-id="9efeb-171">量子ビットが目的の状態にある場合は、`Set` をそのままにしておきます。それ以外の場合は、`X` 操作を実行することで量子ビットの状態が目的の状態に変更されます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-171">If the qubit is in the state we want, `Set` leaves it alone; otherwise, by executing the `X` operation, we change the qubit state to the desired state.</span></span>

### <a name="about-q-operations"></a><span data-ttu-id="9efeb-172">Q# 操作について</span><span class="sxs-lookup"><span data-stu-id="9efeb-172">About Q# operations</span></span>

<span data-ttu-id="9efeb-173">Q# 操作は、量子のサブルーチンです。</span><span class="sxs-lookup"><span data-stu-id="9efeb-173">A Q# operation is a quantum subroutine.</span></span> <span data-ttu-id="9efeb-174">つまり、量子操作を含む呼び出し可能なルーチンです。</span><span class="sxs-lookup"><span data-stu-id="9efeb-174">That is, it is a callable routine that contains quantum operations.</span></span>

<span data-ttu-id="9efeb-175">操作の引数は、かっこ内にタプルとして指定します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-175">The arguments to an operation are specified as a tuple, within parentheses.</span></span>

<span data-ttu-id="9efeb-176">操作の戻り値の型は、コロンの後に指定します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-176">The return type of the operation is specified after a colon.</span></span> <span data-ttu-id="9efeb-177">この場合、`Set` 操作には戻り値がないため、`Unit` を返すように設定されています。</span><span class="sxs-lookup"><span data-stu-id="9efeb-177">In this case, the `Set` operation has no return, so it is marked as returning `Unit`.</span></span> <span data-ttu-id="9efeb-178">これは、F# における `unit` の Q# 版にあたります。C# では `void`、Python では空のタプル (`Tuple[()]`) とほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="9efeb-178">This is the Q# equivalent of `unit` in F#, which is roughly analogous to `void` in C#, and an empty tuple (`Tuple[()]`) in Python.</span></span>

<span data-ttu-id="9efeb-179">最初の Q# 操作では、次の 2 つの量子操作を使用しました。</span><span class="sxs-lookup"><span data-stu-id="9efeb-179">You have used two quantum operations in your first Q# operation:</span></span>

* <span data-ttu-id="9efeb-180">量子ビットの状態を測定する [M](xref:microsoft.quantum.intrinsic.m) 操作</span><span class="sxs-lookup"><span data-stu-id="9efeb-180">The [M](xref:microsoft.quantum.intrinsic.m) operation, which measures the state of the qubit</span></span>
* <span data-ttu-id="9efeb-181">量子ビットの状態を反転させる [X](xref:microsoft.quantum.intrinsic.x) 操作</span><span class="sxs-lookup"><span data-stu-id="9efeb-181">The [X](xref:microsoft.quantum.intrinsic.x) operation, which flips the state of a qubit</span></span>

<span data-ttu-id="9efeb-182">量子操作により、量子ビットの状態が変換されます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-182">A quantum operation transforms the state of a qubit.</span></span> <span data-ttu-id="9efeb-183">従来の論理ゲートの類義語として、量子操作の代わりに、量子ゲートが話題になることがあります。</span><span class="sxs-lookup"><span data-stu-id="9efeb-183">Sometime people talk about quantum gates instead of operations, in analogy to classical logic gates.</span></span> <span data-ttu-id="9efeb-184">これは初期の量子コンピューティングでは、アルゴリズムが単なる理論上の構成要素であり、古典コンピューティングの回路図に似た図で視覚化されていたことに端を発します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-184">This is rooted in the early days of quantum computing when algorithms were merely a theoretical construct and visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>

### <a name="add-q-test-code"></a><span data-ttu-id="9efeb-185">Q# テスト コードの追加</span><span class="sxs-lookup"><span data-stu-id="9efeb-185">Add Q# test code</span></span>

1. <span data-ttu-id="9efeb-186">`Bell.qs` ファイルの名前空間内、`Set` 操作の終了後に次の操作を追加します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-186">Add the following operation to the `Bell.qs` file, inside the namespace, after the end of the `Set` operation:</span></span>

    ```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                Set(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            Set(Zero, qubit);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
    ```

    <span data-ttu-id="9efeb-187">この操作 (`TestBellState`) では、`count` 回ループし、指定された `initial` 値を量子ビットに設定して、結果を測定 (`M`) します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-187">This operation (`TestBellState`) will loop for `count` iterations, set a specified `initial` value on a qubit and then measure (`M`) the result.</span></span> <span data-ttu-id="9efeb-188">これにより、測定した 0 と 1 の数がいくつあるかの統計情報が収集され、呼び出し元に返されます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-188">It will gather statistics on how many zeros and ones we've measured and return them to the caller.</span></span> <span data-ttu-id="9efeb-189">ここでは、もう 1 つの必要な操作を実行しています。</span><span class="sxs-lookup"><span data-stu-id="9efeb-189">It performs one other necessary operation.</span></span> <span data-ttu-id="9efeb-190">他のユーザーがこの量子ビットに既知の状態を割り当てることができるよう、終了する前にこの量子ビットを既知の状態 (`Zero`) にリセットします。</span><span class="sxs-lookup"><span data-stu-id="9efeb-190">It resets the qubit to a known state (`Zero`) before returning it allowing others to allocate this qubit in a known state.</span></span> <span data-ttu-id="9efeb-191">この操作は、`using` ステートメントに必須です。</span><span class="sxs-lookup"><span data-stu-id="9efeb-191">This is required by the `using` statement.</span></span>

### <a name="about-variables-in-q"></a><span data-ttu-id="9efeb-192">Q# の変数について</span><span class="sxs-lookup"><span data-stu-id="9efeb-192">About variables in Q#</span></span>

<span data-ttu-id="9efeb-193">既定では、Q# の変数は不変です。バインド後に変数の値を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="9efeb-193">By default, variables in Q# are immutable; their value may not be changed after they are bound.</span></span> <span data-ttu-id="9efeb-194">`let` キーワードは、不変変数のバインドを示すために使用します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-194">The `let` keyword is used to indicate the binding of an immutable variable.</span></span> <span data-ttu-id="9efeb-195">操作の引数は常に不変です。</span><span class="sxs-lookup"><span data-stu-id="9efeb-195">Operation arguments are always immutable.</span></span>

<span data-ttu-id="9efeb-196">先ほどの例の `numOnes` のように、値を変更できる変数が必要な場合は、`mutable` キーワードを使用して変数を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-196">If you need a variable whose value can change, such as `numOnes` in the example, you can declare the variable with the `mutable` keyword.</span></span> <span data-ttu-id="9efeb-197">可変変数の値は、`set` ステートメントを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-197">A mutable variable's value may be changed using a `set` statement.</span></span>

<span data-ttu-id="9efeb-198">どちらの場合も、変数の型はコンパイラによって推論されます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-198">In both cases, the type of a variable is inferred by the compiler.</span></span> <span data-ttu-id="9efeb-199">Q# では、変数に型の注釈は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="9efeb-199">Q# doesn't require any type annotations for variables.</span></span>

### <a name="about-using-statements-in-q"></a><span data-ttu-id="9efeb-200">Q# の `using` ステートメントについて</span><span class="sxs-lookup"><span data-stu-id="9efeb-200">About `using` statements in Q#</span></span>

<span data-ttu-id="9efeb-201">`using` ステートメントも Q# に特有です。</span><span class="sxs-lookup"><span data-stu-id="9efeb-201">The `using` statement is also special to Q#.</span></span> <span data-ttu-id="9efeb-202">これは、コードのブロックで使用するために量子ビットを割り当てる場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-202">It is used to allocate qubits for use in a block of code.</span></span> <span data-ttu-id="9efeb-203">Q# では、複雑なアルゴリズムの有効期間全体にわたってリソースが固定されるのではなく、すべての量子ビットが動的に割り当てられ、解放されます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-203">In Q#, all qubits are dynamically allocated and released, rather than being fixed resources that are there for the entire lifetime of a complex algorithm.</span></span> <span data-ttu-id="9efeb-204">`using` ステートメントは、ブロックの最初で一連の量子ビットを割り当て、ブロックの最後でその量子ビットを解放します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-204">A `using` statement allocates a set of qubits at the start, and releases those qubits at the end of the block.</span></span>

## <a name="create-the-host-application-code"></a><span data-ttu-id="9efeb-205">ホスト アプリケーション コードの作成</span><span class="sxs-lookup"><span data-stu-id="9efeb-205">Create the host application code</span></span>

#### <a name="python"></a>[<span data-ttu-id="9efeb-206">Python</span><span class="sxs-lookup"><span data-stu-id="9efeb-206">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="9efeb-207">`host.py` ファイルを開き、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-207">Open the `host.py` file and add the following code:</span></span>

    ```python
    import qsharp

    from qsharp import Result
    from Quantum.Bell import TestBellState

    initials = (Result.Zero, Result.One)

    for i in initials:
      res = TestBellState.simulate(count=1000, initial=i)
      (num_zeros, num_ones) = res
      print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4}')
    ```

#### <a name="c"></a>[<span data-ttu-id="9efeb-208">C#</span><span class="sxs-lookup"><span data-stu-id="9efeb-208">C#</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="9efeb-209">`Driver.cs` ファイルの内容を次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-209">Replace the contents of the `Driver.cs` file with the following code:</span></span>

    ```csharp
    using System;

    using Microsoft.Quantum.Simulation.Core;
    using Microsoft.Quantum.Simulation.Simulators;

    namespace Quantum.Bell
    {
        class Driver
        {
            static void Main(string[] args)
            {
                using (var qsim = new QuantumSimulator())
                {
                    // Try initial values
                    Result[] initials = new Result[] { Result.Zero, Result.One };
                    foreach (Result initial in initials)
                    {
                        var res = TestBellState.Run(qsim, 1000, initial).Result;
                        var (numZeros, numOnes) = res;
                        System.Console.WriteLine(
                            $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4}");
                    }
                }

                System.Console.WriteLine("Press any key to continue...");
                Console.ReadKey();
            }
        }
    }
    ```

#### [](#tab/tabid-vs2019)

* * *

### <a name="about-the-host-application-code"></a><span data-ttu-id="9efeb-210">ホスト アプリケーション コードについて</span><span class="sxs-lookup"><span data-stu-id="9efeb-210">About the host application code</span></span>

#### <a name="python"></a>[<span data-ttu-id="9efeb-211">Python</span><span class="sxs-lookup"><span data-stu-id="9efeb-211">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="9efeb-212">Python ホスト アプリケーションには、次の 3 つの部分があります。</span><span class="sxs-lookup"><span data-stu-id="9efeb-212">The Python host application has three parts:</span></span>

* <span data-ttu-id="9efeb-213">量子アルゴリズムに必要な引数を計算します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-213">Compute any arguments required for the quantum algorithm.</span></span> <span data-ttu-id="9efeb-214">この例では、`count` は 1000 に固定され、`initial` が量子ビットの初期値になっています。</span><span class="sxs-lookup"><span data-stu-id="9efeb-214">In the example, `count` is fixed at a 1000 and `initial` is the initial value of the qubit.</span></span>
* <span data-ttu-id="9efeb-215">インポートした Q# 操作の `simulate()` メソッドを呼び出し、量子アルゴリズムを実行します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-215">Run the quantum algorithm by calling the `simulate()` method of the imported Q# operation.</span></span>
* <span data-ttu-id="9efeb-216">操作の結果を処理します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-216">Process the result of the operation.</span></span> <span data-ttu-id="9efeb-217">この例では、`res` が操作の結果を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="9efeb-217">In the example, `res` receives the result of the operation.</span></span> <span data-ttu-id="9efeb-218">ここでの結果は、シミュレーターが測定した 0 の数 (`num_zeros`) と 1 の数 (`num_ones`) のタプルになります。</span><span class="sxs-lookup"><span data-stu-id="9efeb-218">Here the result is a tuple of the number of zeros (`num_zeros`) and number of ones (`num_ones`) measured by the simulator.</span></span> <span data-ttu-id="9efeb-219">2 つのフィールドを取得するためにタプルを分解し、結果を出力します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-219">We deconstruct the tuple to get the two fields, and print the results.</span></span>

#### <a name="c"></a>[<span data-ttu-id="9efeb-220">C#</span><span class="sxs-lookup"><span data-stu-id="9efeb-220">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="9efeb-221">C# ホスト アプリケーションには、次の 4 つの部分があります。</span><span class="sxs-lookup"><span data-stu-id="9efeb-221">The C# host application has four parts:</span></span>

* <span data-ttu-id="9efeb-222">量子シミュレーターを構築します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-222">Construct a quantum simulator.</span></span> <span data-ttu-id="9efeb-223">この例では、`qsim` がシミュレーターです。</span><span class="sxs-lookup"><span data-stu-id="9efeb-223">In the example, `qsim` is the simulator.</span></span>
* <span data-ttu-id="9efeb-224">量子アルゴリズムに必要な引数を計算します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-224">Compute any arguments required for the quantum algorithm.</span></span> <span data-ttu-id="9efeb-225">この例では、`count` は 1000 に固定され、`initial` が量子ビットの初期値になっています。</span><span class="sxs-lookup"><span data-stu-id="9efeb-225">In the example, `count` is fixed at a 1000 and `initial` is the initial value of the qubit.</span></span>
* <span data-ttu-id="9efeb-226">量子アルゴリズムを実行します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-226">Run the quantum algorithm.</span></span> <span data-ttu-id="9efeb-227">各 Q# 操作によって、同じ名前の C# クラスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-227">Each Q# operation generates a C# class with the same name.</span></span> <span data-ttu-id="9efeb-228">このクラスには、操作を**非同期に**実行する `Run` メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="9efeb-228">This class has a `Run` method that **asynchronously** executes the operation.</span></span> <span data-ttu-id="9efeb-229">実行が非同期とは、実際のハードウェアでの実行が非同期になるということです。</span><span class="sxs-lookup"><span data-stu-id="9efeb-229">The execution is asynchronous because execution on actual hardware will be asynchronous.</span></span> <span data-ttu-id="9efeb-230">`Run` メソッドは非同期であるため、`Result` プロパティを取得しています。これにより、タスクが完了して結果を同期的に返すまで実行がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-230">Because the `Run` method is asynchronous, we fetch the `Result` property; this blocks execution until the task completes and returns the result synchronously.</span></span>
* <span data-ttu-id="9efeb-231">操作の結果を処理します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-231">Process the result of the operation.</span></span> <span data-ttu-id="9efeb-232">この例では、`res` が操作の結果を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="9efeb-232">In the example, `res` receives the result of the operation.</span></span> <span data-ttu-id="9efeb-233">ここでの結果は、シミュレーターが測定した 0 の数 (`numZeros`) と 1 の数 (`numOnes`) のタプルになります。</span><span class="sxs-lookup"><span data-stu-id="9efeb-233">Here the result is a tuple of the number of zeros (`numZeros`) and number of ones (`numOnes`) measured by the simulator.</span></span> <span data-ttu-id="9efeb-234">これが C# の ValueTuple として返されます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-234">This is returned as a ValueTuple in C#.</span></span> <span data-ttu-id="9efeb-235">2 つのフィールドを取得するためにタプルを分解し、結果を出力し、キーが押されるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-235">We deconstruct the tuple to get the two fields, print the results, and wait for a keypress.</span></span>

#### [](#tab/tabid-vs2019)

* * *

## <a name="build-and-run"></a><span data-ttu-id="9efeb-236">ビルドおよび実行</span><span class="sxs-lookup"><span data-stu-id="9efeb-236">Build and run</span></span>

#### <a name="python"></a>[<span data-ttu-id="9efeb-237">Python</span><span class="sxs-lookup"><span data-stu-id="9efeb-237">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="9efeb-238">ターミナルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-238">Run the following command at your terminal:</span></span>

    ```
    python host.py
    ```

    <span data-ttu-id="9efeb-239">このコマンドは、Q# 操作をシミュレートするホスト アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-239">This command runs the host application, which simulates the Q# operation.</span></span>

<span data-ttu-id="9efeb-240">結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9efeb-240">The results should be:</span></span>

```Output
Init:0    0s=1000 1s=0   
Init:1    0s=0    1s=1000
```

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="9efeb-241">コマンドライン/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="9efeb-241">Command Line / Visual Studio Code</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="9efeb-242">ターミナルで次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-242">Run the following at your terminal:</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="9efeb-243">このコマンドは、必要なすべてのパッケージを自動的にダウンロードし、アプリケーションをビルドしてから、それをコマンド ラインで実行します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-243">This command will automatically download all required packages, build the application, then run it at the command line.</span></span>

1. <span data-ttu-id="9efeb-244">または、**F1** キーを押してコマンド パレットを開き、 **[デバッグ]、[デバッグなしで開始]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-244">Alternatively, press **F1** to open the Command Palette and select **Debug: Start Without Debugging.**</span></span>
<span data-ttu-id="9efeb-245">プログラムを起動する方法を記述した新しい ``launch.json`` ファイルを作成するように求められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9efeb-245">You may be prompted to create a new ``launch.json`` file describing how to start the program.</span></span>
<span data-ttu-id="9efeb-246">既定の ``launch.json`` は、ほとんどのアプリケーションで適切に動作します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-246">The default ``launch.json`` should work well for most applications.</span></span>

<span data-ttu-id="9efeb-247">結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9efeb-247">The results should be:</span></span>

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

#### <a name="visual-studio"></a>[<span data-ttu-id="9efeb-248">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9efeb-248">Visual Studio</span></span>](#tab/tabid-vs2019)

1. <span data-ttu-id="9efeb-249">`F5` を押すだけで、プログラムがビルドされて実行されます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-249">Just hit `F5`, and your program should build and run!</span></span>

<span data-ttu-id="9efeb-250">結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9efeb-250">The results should be:</span></span>

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

<span data-ttu-id="9efeb-251">プログラムは、キーを押した後に終了します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-251">The program will exit after you press a key.</span></span>

* * *

## <a name="prepare-superposition"></a><span data-ttu-id="9efeb-252">重ね合わせ状態を作成する</span><span class="sxs-lookup"><span data-stu-id="9efeb-252">Prepare superposition</span></span>

<span data-ttu-id="9efeb-253">**概要** では、Q# が重ね合わせで量子ビットをどのように配置するかを見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="9efeb-253">**Overview** Now let’s look at how Q# expresses ways to put qubits in superposition.</span></span>  <span data-ttu-id="9efeb-254">量子ビットの状態は、0 と 1 の重ね合わせにできることを思い出してください。</span><span class="sxs-lookup"><span data-stu-id="9efeb-254">Recall that the state of a qubit can be in a superposition of 0 and 1.</span></span>  <span data-ttu-id="9efeb-255">これを行うには、`Hadamard` 操作を使用します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-255">We’ll use the `Hadamard` operation to accomplish this.</span></span> <span data-ttu-id="9efeb-256">量子ビットが従来の状態のいずれか (測定で常に `One` または `Zero` を返す) である場合、`Hadamard` (`H`) 操作によって、量子ビットの測定で 50% の `Zero` および 50% の `One` を返す状態に量子ビットが配置されます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-256">If the qubit is in either of the classical states (where a measurement returns `Zero` always or `One` always), then the `Hadamard` or `H` operation will put the qubit in a state where a measurement of the qubit will return `Zero` 50% of the time and return `One` 50% of the time.</span></span>  <span data-ttu-id="9efeb-257">概念上、量子ビットは `Zero` と `One` の中間にあると考えることができます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-257">Conceputually, the qubit can be thought of as halfway between the `Zero` and `One`.</span></span>  <span data-ttu-id="9efeb-258">ここで、`TestBellState` 操作をシミュレートすると、測定後の結果は、ほぼ同数の `Zero` と `One` を返します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-258">Now, when we simulate the `TestBellState` operation, we will see the results will return roughly an equal number of `Zero` and `One` after measurement.</span></span>  

<span data-ttu-id="9efeb-259">まず、量子ビットを反転してみます (量子ビットが `Zero` の状態にある場合は `One` になり、その逆も同様になります)。</span><span class="sxs-lookup"><span data-stu-id="9efeb-259">First we'll just try to flip the qubit (if the qubit is in `Zero` state will flip to `One` and vice versa).</span></span> <span data-ttu-id="9efeb-260">これは、`TestBellState` で測定する前に `X` 操作を実行することで実現されます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-260">This is accomplished by performing an `X` operation before we measure it in `TestBellState`:</span></span>

```qsharp
X(qubit);
let res = M(qubit);
```

<span data-ttu-id="9efeb-261">これで結果 (`F5`を押した後) は逆転します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-261">Now the results (after pressing `F5`) are reversed:</span></span>

```Output
Init:Zero 0s=0    1s=1000
Init:One  0s=1000 1s=0
```

<span data-ttu-id="9efeb-262">ただし、これまでに説明したものはすべて従来型の操作です。</span><span class="sxs-lookup"><span data-stu-id="9efeb-262">However, everything we've seen so far is classical.</span></span> <span data-ttu-id="9efeb-263">量子的な結果を取得してみましょう。</span><span class="sxs-lookup"><span data-stu-id="9efeb-263">Let's get a quantum result.</span></span> <span data-ttu-id="9efeb-264">必要なのは、先ほどの実行の `X` 操作を `H` すなわち Hadamard 操作に置き換えることだけです。</span><span class="sxs-lookup"><span data-stu-id="9efeb-264">All we need to do is replace the `X` operation in the previous run with an `H` or Hadamard operation.</span></span> <span data-ttu-id="9efeb-265">これは、量子ビットを 0 から 1 まで完全に反転させるのではなく、半分だけ反転します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-265">Instead of flipping the qubit all the way from 0 to 1, we will only flip it halfway.</span></span> <span data-ttu-id="9efeb-266">`TestBellState` の行を置き換えると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9efeb-266">The replaced lines in `TestBellState` now look like:</span></span>

```qsharp
H(qubit);
let res = M(qubit);
```

<span data-ttu-id="9efeb-267">結果はさらに興味深いものになります。</span><span class="sxs-lookup"><span data-stu-id="9efeb-267">Now the results get more interesting:</span></span>

```Output
Init:Zero 0s=484  1s=516
Init:One  0s=522  1s=478
```

<span data-ttu-id="9efeb-268">測定するたびに、従来型の値が要求されますが、量子ビットは 0 と 1 の中間にあるため、(統計的に) 半分が 0、半分が 1 になります。</span><span class="sxs-lookup"><span data-stu-id="9efeb-268">Every time we measure, we ask for a classical value, but the qubit is halfway between 0 and 1, so we get (statistically) 0 half the time and 1 half the time.</span></span> <span data-ttu-id="9efeb-269">これは__重ね合わせ__と呼ばれる現象で、これによって初めて量子状態を実際に観測できます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-269">This is known as __superposition__ and gives us our first real view into a quantum state.</span></span>

## <a name="prepare-entanglement"></a><span data-ttu-id="9efeb-270">もつれ状態を作成する</span><span class="sxs-lookup"><span data-stu-id="9efeb-270">Prepare entanglement</span></span>

<span data-ttu-id="9efeb-271">**概要:** では、Q# がどのように量子ビットのもつれを表現するかを見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="9efeb-271">**Overview:**  Now let’s look at how Q# expresses ways to entangle qubits.</span></span>  <span data-ttu-id="9efeb-272">まず、最初の量子ビットを初期状態に設定してから、`H` 操作を使用してそれを重ね合わせに配置します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-272">First, we set the first qubit to the initial state and then use the `H` operation to put it into superposition.</span></span>  <span data-ttu-id="9efeb-273">次に、最初の量子ビットを測定する前に、Controlled-Not を表す新しい操作 (`CNOT`) を使用します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-273">Then, before we measure the first qubit, we use a new operation (`CNOT`), which stands for Controlled-Not.</span></span>  <span data-ttu-id="9efeb-274">2 つの量子ビットに対してこの操作を実行した結果、最初の量子ビットが `One` である場合には 2 番目の量子ビットが反転されます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-274">The result of executing this operation on two qubits is to flip the second qubit if the first qubit is `One`.</span></span>  <span data-ttu-id="9efeb-275">これで、2 つの量子ビットがもつれ状態になります。</span><span class="sxs-lookup"><span data-stu-id="9efeb-275">Now, the two qubits are entangled.</span></span>  <span data-ttu-id="9efeb-276">最初の量子ビットの統計情報は変わっていませんが (測定後、50-50 の確率で `Zero` または `One`)、2 番目の量子ビットを測定すると、最初の量子ビットを測定した結果と__常に__同じになります。</span><span class="sxs-lookup"><span data-stu-id="9efeb-276">Our statistics for the first qubit haven't changed (50-50 chance of a `Zero` or a `One` after measurement), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit.</span></span> <span data-ttu-id="9efeb-277">この `CNOT` が 2 つの量子ビットをもつれさせ、片方に何かが起きると、もう片方にも同じことが起こるようになっています。</span><span class="sxs-lookup"><span data-stu-id="9efeb-277">Our `CNOT` has entangled the two qubits, so that whatever happens to one of them, happens to the other.</span></span> <span data-ttu-id="9efeb-278">測定を反対にしても (最初の量子ビットの前に 2 番目の量子ビットを測定する)、同じことが起こります。</span><span class="sxs-lookup"><span data-stu-id="9efeb-278">If you reversed the measurements (did the second qubit before the first), the same thing would happen.</span></span> <span data-ttu-id="9efeb-279">最初の測定値はランダムであり、2 回目の測定値は最初に検出されたものと完全に一致します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-279">The first measurement would be random and the second would be in lock step with whatever was discovered for the first.</span></span>

<span data-ttu-id="9efeb-280">まず、`TestBellState` で 1 つではなく 2 つの量子ビットを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9efeb-280">The first thing we'll need to do is allocate 2 qubits instead of one in `TestBellState`:</span></span>

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

<span data-ttu-id="9efeb-281">これにより、`TestBellState` で測定 (`M`) する前に、新しい操作 (`CNOT`) を追加できます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-281">This will allow us to add a new operation (`CNOT`) before we measure  (`M`) in `TestBellState`:</span></span>

```qsharp
Set(initial, q0);
Set(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

<span data-ttu-id="9efeb-282">最初の量子ビットを初期化するために別の `Set` 操作を追加し、開始時に常に `Zero` 状態になるようにしました。</span><span class="sxs-lookup"><span data-stu-id="9efeb-282">We've added another `Set` operation to initialize the first qubit to make sure that it's always in the `Zero` state when we start.</span></span>

<span data-ttu-id="9efeb-283">また、2 番目の量子ビットを解放する前にリセットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9efeb-283">We also need to reset the second qubit before releasing it.</span></span>

```qsharp
Set(Zero, q0);
Set(Zero, q1);
```

<span data-ttu-id="9efeb-284">完全なルーチンは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9efeb-284">The full routine now looks like this:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set (initial, q0);
                Set (Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

<span data-ttu-id="9efeb-285">これを実行すると、以前とまったく同じ 50-50 の結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-285">If we run this, we'll get exactly the same 50-50 result we got before.</span></span> <span data-ttu-id="9efeb-286">しかし、ここで興味深いのは、2 番目の量子ビットが測定される最初の量子ビットに対してどのように反応するかです。</span><span class="sxs-lookup"><span data-stu-id="9efeb-286">However, what we're interested in is how the second qubit reacts to the first being measured.</span></span> <span data-ttu-id="9efeb-287">この統計情報は、新しいバージョンの `TestBellState` の操作で追加します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-287">We'll add this statistic with a new version of the `TestBellState` operation:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set(initial, q0);
                Set(Zero, q1);

                H(q0);
                CNOT(q0, q1);
                let res = M(q0);

                if (M(q1) == res) {
                    set agree += 1;
                }

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes, agree);
    }
```

<span data-ttu-id="9efeb-288">新しい戻り値 (`agree`) は、最初の量子ビットの測定値が 2 番目の量子ビットの測定値と一致した回数を追跡します。</span><span class="sxs-lookup"><span data-stu-id="9efeb-288">The new return value (`agree`) keeps track of every time the measurement from the first qubit matches the measurement of the second qubit.</span></span> <span data-ttu-id="9efeb-289">また、ホスト アプリケーションを適切に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9efeb-289">We also have to update the host application accordingly:</span></span>

#### <a name="python"></a>[<span data-ttu-id="9efeb-290">Python</span><span class="sxs-lookup"><span data-stu-id="9efeb-290">Python</span></span>](#tab/tabid-python)

```python
import qsharp

from qsharp import Result
from Quantum.Bell import TestBellState

initials = {Result.Zero, Result.One} 

for i in initials:
    res = TestBellState.simulate(count=1000, initial=i)
    (num_zeros, num_ones, agree) = res
    print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4} agree={agree: <4}')
```

#### <a name="c"></a>[<span data-ttu-id="9efeb-291">C#</span><span class="sxs-lookup"><span data-stu-id="9efeb-291">C#</span></span>](#tab/tabid-csharp)

```csharp
            using (var qsim = new QuantumSimulator())
            {
                // Try initial values
                Result[] initials = new Result[] { Result.Zero, Result.One };
                foreach (Result initial in initials)
                {
                    var res = TestBellState.Run(qsim, 1000, initial).Result;
                    var (numZeros, numOnes, agree) = res;
                    System.Console.WriteLine(
                        $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4} agree={agree,-4}");
                }
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
```

#### [](#tab/tabid-vs2019)

* * *

<span data-ttu-id="9efeb-292">これを実行すると、驚くような結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="9efeb-292">Now when we run, we get something pretty amazing:</span></span>

```Output
Init:Zero 0s=499  1s=501  agree=1000
Init:One  0s=490  1s=510  agree=1000
```

<span data-ttu-id="9efeb-293">概要で述べたように、最初の量子ビットの統計情報は変わっていませんが (50-50 の確率で 0 または 1)、2 番目の量子ビットを測定すると、最初の量子ビットを測定した結果と__常に__同じになります。これは、もつれ状態にあるからです。</span><span class="sxs-lookup"><span data-stu-id="9efeb-293">As stated in the overview, our statistics for the first qubit haven't changed (50-50 chance of a 0 or a 1), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit, because they are entangled!</span></span>

<span data-ttu-id="9efeb-294">これで、最初の量子プログラムが作成できました。</span><span class="sxs-lookup"><span data-stu-id="9efeb-294">Congratulations, you've written your first quantum program!</span></span>

## <a name="next-steps"></a><span data-ttu-id="9efeb-295">次のステップ</span><span class="sxs-lookup"><span data-stu-id="9efeb-295">Next steps</span></span>

<span data-ttu-id="9efeb-296">[グローバーの検索](xref:microsoft.quantum.quickstarts.search)のチュートリアルでは、最も人気のある量子コンピューティング アルゴリズムの 1 つである、グローバーの検索をビルドして実行する方法を示しています。また、量子コンピューティングに関する実際の問題を解決するために使用できる Q# プログラムの優れた例を紹介しています。</span><span class="sxs-lookup"><span data-stu-id="9efeb-296">The tutorial [Grover’s search](xref:microsoft.quantum.quickstarts.search) shows you how to build and run Grover search, one of the most popular quantum computing algorithms and offers a nice example of a Q# program that can be used to solve real problems with quantum computing.</span></span>  

<span data-ttu-id="9efeb-297">「[Get Started with the Quantum Development Kit](xref:microsoft.quantum.welcome)」(Quantum Development Kit の概要) では、Q# と量子コンピューティングのその他の学習方法も紹介しています。</span><span class="sxs-lookup"><span data-stu-id="9efeb-297">[Get Started with the Quantum Development Kit](xref:microsoft.quantum.welcome) recommends more ways to learn Q# and quantum programming.</span></span>
