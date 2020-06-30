---
title: Quantum 開発キット (QDK) を更新する
description: Q# プロジェクトと Microsoft Quantum 開発キットを現在のバージョンに更新する方法を説明します。
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 8d39716c4d4c96ad87862b4b185895aab66cd210
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274079"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="c7e96-103">Microsoft Quantum 開発キット (QDK) を更新する</span><span class="sxs-lookup"><span data-stu-id="c7e96-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="c7e96-104">Microsoft Quantum 開発キット (QDK) を、最新のバージョンに更新する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="c7e96-105">この記事では、QDK が既にインストールされていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c7e96-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="c7e96-106">初めてインストールしようとしている場合は、[インストール ガイド](xref:microsoft.quantum.install)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c7e96-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="c7e96-107">常に最新の QDK リリースを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c7e96-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="c7e96-108">この更新ガイドに従って、最新の QDK バージョンにアップグレードしましょう。</span><span class="sxs-lookup"><span data-stu-id="c7e96-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="c7e96-109">このプロセスは 2 つの部分から成っています。</span><span class="sxs-lookup"><span data-stu-id="c7e96-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="c7e96-110">既存の Q# ファイルとプロジェクトを更新して、更新された構文にコードが合致するようにします。</span><span class="sxs-lookup"><span data-stu-id="c7e96-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="c7e96-111">選択した開発環境に対して、QDK そのものを更新します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-q-projects"></a><span data-ttu-id="c7e96-112">Q# プロジェクトの更新</span><span class="sxs-lookup"><span data-stu-id="c7e96-112">Updating Q# Projects</span></span> 

<span data-ttu-id="c7e96-113">Q# の演算をホストするために C# と Python のどちらを使用しているかに関わらず、次の手順に従って Q# プロジェクトを更新してください。</span><span class="sxs-lookup"><span data-stu-id="c7e96-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="c7e96-114">最初に、最新バージョンの [.NET Core SDK 3.1](https://dotnet.microsoft.com/download) を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="c7e96-115">コマンド プロンプトで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="c7e96-116">出力が `3.1.100` 以上であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="c7e96-117">そうでない場合、[最新バージョン](https://dotnet.microsoft.com/download)をインストールして、もう一度確認します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="c7e96-118">その後、自分の設定 (Visual Studio、Visual Studio Code、または直接コマンド ラインで) に応じて次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c7e96-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="c7e96-119">Visual Studio で Q# プロジェクトを更新する</span><span class="sxs-lookup"><span data-stu-id="c7e96-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="c7e96-120">[こちら](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019)の手順を参照して、Visual Studio 2019 の最新バージョンに更新します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions.</span></span>
2. <span data-ttu-id="c7e96-121">Visual Studio でソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="c7e96-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="c7e96-122">メニューから、 **[ビルド]**  ->  **[ソリューションのクリーン]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="c7e96-123">それぞれの .csproj ファイルで、ターゲット フレームワークを `netcoreapp3.1` (ライブラリ プロジェクトの場合は `netstandard2.1`) に更新します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="c7e96-124">つまり、フォームの行を次のように編集します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="c7e96-125">ターゲット フレームワークの指定の詳細については、[ここ](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7e96-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="c7e96-126">それぞれの .csproj ファイルで、次の行で示されているように SDK を `Microsoft.Quantum.Sdk` に設定します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="c7e96-127">バージョン番号は利用可能な最新のものにする必要がありますので、ご注意ください。[リリース ノート](https://docs.microsoft.com/quantum/relnotes/)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="c7e96-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. <span data-ttu-id="c7e96-128">ソリューションのすべてのファイルを保存し、閉じます。</span><span class="sxs-lookup"><span data-stu-id="c7e96-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="c7e96-129">**[ツール]**  ->  **[コマンド ライン]**  ->  **[開発者コマンド プロンプト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="c7e96-130">または、Visual Studio のパッケージ管理コンソールを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c7e96-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="c7e96-131">ソリューションの各プロジェクトに対して、次のコマンドを実行してこのパッケージを**削除**します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="c7e96-132">プロジェクトで他の Microsoft.Quantum または Microsoft.Azure.Quantum パッケージ (Microsoft.Quantum.Numerics) を使用している場合、これらに対して **add** コマンドを実行して使用しているバージョンを更新してください。</span><span class="sxs-lookup"><span data-stu-id="c7e96-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="c7e96-133">コマンド プロンプトを閉じて、 **[ビルド]**  ->  **[ソリューションのビルド]** を選択します ([ソリューションのリビルド] は選択 "*しない*" でください)。</span><span class="sxs-lookup"><span data-stu-id="c7e96-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="c7e96-134">これで、[Visual Studio の QDK 拡張機能の更新](#update-visual-studio-qdk-extension)に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="c7e96-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="c7e96-135">Visual Studio Code で Q# プロジェクトを更新する</span><span class="sxs-lookup"><span data-stu-id="c7e96-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="c7e96-136">Visual Studio Code で、更新するプロジェクトが含まれるフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="c7e96-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="c7e96-137">**[ターミナル]**  ->  **[新しいターミナル]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="c7e96-138">コマンド ラインを使用する更新の手順に従います (すぐ下にあります)。</span><span class="sxs-lookup"><span data-stu-id="c7e96-138">Follow the instructions for updating using the command line (directly below).</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="c7e96-139">コマンド ラインを使用して Q# プロジェクトを更新する</span><span class="sxs-lookup"><span data-stu-id="c7e96-139">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="c7e96-140">メイン プロジェクト ファイルが含まれているフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="c7e96-141">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="c7e96-142">QDK の現在のバージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="c7e96-143">そのためには、[リリース ノート](https://docs.microsoft.com/quantum/relnotes/)を確認します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="c7e96-144">バージョンの形式は、`0.11.2006.207` のようになっています。</span><span class="sxs-lookup"><span data-stu-id="c7e96-144">The version will be in a format similar to `0.11.2006.207`.</span></span>

4. <span data-ttu-id="c7e96-145">それぞれの `.csproj` ファイルで、次のステップを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="c7e96-146">ターゲット フレームワークを `netcoreapp3.1` (ライブラリ プロジェクトの場合は `netstandard2.1`) に更新します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="c7e96-147">つまり、フォームの行を次のように編集します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="c7e96-148">ターゲット フレームワークの指定の詳細については、[こちら](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7e96-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="c7e96-149">プロジェクト定義で、SDK への参照を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c7e96-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="c7e96-150">バージョン番号が、**手順 3** で確認した値に対応していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - <span data-ttu-id="c7e96-151">もしある場合は、パッケージ `Microsoft.Quantum.Development.Kit` への参照を削除します。これは、次のエントリで指定されます。</span><span class="sxs-lookup"><span data-stu-id="c7e96-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="c7e96-152">すべての Microsoft Quantum パッケージのバージョンを、QDK の最新のリリース バージョン (**手順 3** で確認済み) に更新します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="c7e96-153">これらのパッケージの名称は、次のようなパターンになっています。</span><span class="sxs-lookup"><span data-stu-id="c7e96-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="c7e96-154">パッケージへの参照は、次のような形式になっています。</span><span class="sxs-lookup"><span data-stu-id="c7e96-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - <span data-ttu-id="c7e96-155">更新したファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-155">Save the updated file.</span></span>

    - <span data-ttu-id="c7e96-156">次を実行して、プロジェクトの依存関係を復元します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="c7e96-157">メイン プロジェクトが含まれるフォルダーに戻り、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="c7e96-158">Q# プロジェクトが更新されたので、次の手順に従って QDK そのものを更新します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="c7e96-159">QDK の更新</span><span class="sxs-lookup"><span data-stu-id="c7e96-159">Updating the QDK</span></span>

<span data-ttu-id="c7e96-160">QDK を更新するプロセスは、開発の言語と環境に応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="c7e96-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="c7e96-161">自分の開発環境を次から選択します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-161">Select your development environment below.</span></span>

* [<span data-ttu-id="c7e96-162">Python: IQ# 拡張機能を更新する</span><span class="sxs-lookup"><span data-stu-id="c7e96-162">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="c7e96-163">Jupyter Notebook: IQ# 拡張機能を更新する</span><span class="sxs-lookup"><span data-stu-id="c7e96-163">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="c7e96-164">Visual Studio: QDK 拡張機能を更新する</span><span class="sxs-lookup"><span data-stu-id="c7e96-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="c7e96-165">VS Code: QDK 拡張機能を更新する</span><span class="sxs-lookup"><span data-stu-id="c7e96-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="c7e96-166">コマンド ラインと C#: プロジェクト テンプレートを更新する</span><span class="sxs-lookup"><span data-stu-id="c7e96-166">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="c7e96-167">Python 用の IQ# を更新する</span><span class="sxs-lookup"><span data-stu-id="c7e96-167">Update IQ# for Python</span></span>

1. <span data-ttu-id="c7e96-168">`iqsharp` カーネルを更新します</span><span class="sxs-lookup"><span data-stu-id="c7e96-168">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="c7e96-169">`iqsharp` のバージョンを確認します</span><span class="sxs-lookup"><span data-stu-id="c7e96-169">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="c7e96-170">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7e96-170">You should see the following output:</span></span>

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="c7e96-171">`iqsharp` のバージョンがこれより大きくても問題ありません。[最新リリース](xref:microsoft.quantum.relnotes)と一致するはずです。</span><span class="sxs-lookup"><span data-stu-id="c7e96-171">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="c7e96-172">`qsharp` パッケージを更新します</span><span class="sxs-lookup"><span data-stu-id="c7e96-172">Update the `qsharp` package</span></span>

    ```
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="c7e96-173">`qsharp` のバージョンを確認します</span><span class="sxs-lookup"><span data-stu-id="c7e96-173">Verify the `qsharp` version</span></span>

    ```
    pip show qsharp
    ```

    <span data-ttu-id="c7e96-174">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7e96-174">You should see the following output:</span></span>

    ```
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="c7e96-175">`.qs` ファイルの場所から次のコマンドを実行します</span><span class="sxs-lookup"><span data-stu-id="c7e96-175">Run the following command from the location of your `.qs` files</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="c7e96-176">これで、更新されたバージョンの QDK を使用して既存の量子プログラムを実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c7e96-176">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="c7e96-177">Jupyter Notebook 用の IQ# を更新する</span><span class="sxs-lookup"><span data-stu-id="c7e96-177">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="c7e96-178">`iqsharp` カーネルを更新します</span><span class="sxs-lookup"><span data-stu-id="c7e96-178">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="c7e96-179">`iqsharp` のバージョンを確認します</span><span class="sxs-lookup"><span data-stu-id="c7e96-179">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="c7e96-180">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c7e96-180">Your output should be similar to the following:</span></span>

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="c7e96-181">`iqsharp` のバージョンがこれより大きくても問題ありません。[最新リリース](xref:microsoft.quantum.relnotes)と一致するはずです。</span><span class="sxs-lookup"><span data-stu-id="c7e96-181">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="c7e96-182">Jupyter Notebook のセルから、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-182">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="c7e96-183">これで、既存の Jupyter ノートブックを開き、更新された QDK を使用して実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c7e96-183">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="c7e96-184">Visual Studio の QDK 拡張機能を更新する</span><span class="sxs-lookup"><span data-stu-id="c7e96-184">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="c7e96-185">Q# Visual Studio 拡張機能を更新します</span><span class="sxs-lookup"><span data-stu-id="c7e96-185">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="c7e96-186">Visual Studio で、[Quantum Visual Studio 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)への更新を受け入れるように求められます</span><span class="sxs-lookup"><span data-stu-id="c7e96-186">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="c7e96-187">更新を受け入れます</span><span class="sxs-lookup"><span data-stu-id="c7e96-187">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="c7e96-188">プロジェクト テンプレートは、拡張機能とともに更新されます。</span><span class="sxs-lookup"><span data-stu-id="c7e96-188">The project templates are updated with the extension.</span></span> <span data-ttu-id="c7e96-189">更新されたテンプレートは、新たに作成されたプロジェクトにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c7e96-189">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="c7e96-190">拡張機能が更新される際に、既存のプロジェクトのコードは更新されません。</span><span class="sxs-lookup"><span data-stu-id="c7e96-190">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="c7e96-191">VS Code の QDK 拡張機能を更新する</span><span class="sxs-lookup"><span data-stu-id="c7e96-191">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="c7e96-192">Quantum VS Code 拡張機能を更新します</span><span class="sxs-lookup"><span data-stu-id="c7e96-192">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="c7e96-193">VS Code を再起動します</span><span class="sxs-lookup"><span data-stu-id="c7e96-193">Restart VS Code</span></span>
    - <span data-ttu-id="c7e96-194">**[拡張機能]** タブに移動します</span><span class="sxs-lookup"><span data-stu-id="c7e96-194">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="c7e96-195">**[Microsoft Quantum Development Kit for Visual Studio Code]\(Visual Studio Code 用 Microsoft Quantum 開発キット\)** を選択します</span><span class="sxs-lookup"><span data-stu-id="c7e96-195">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="c7e96-196">拡張機能を再度読み込みます</span><span class="sxs-lookup"><span data-stu-id="c7e96-196">Reload the extension</span></span>

2. <span data-ttu-id="c7e96-197">Quantum プロジェクト テンプレートを更新します</span><span class="sxs-lookup"><span data-stu-id="c7e96-197">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="c7e96-198">**[表示]**  ->  **[コマンド パレット]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-198">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="c7e96-199">**[Q#:Install project templates]\(Q#: プロジェクト テンプレートのインストール\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7e96-199">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="c7e96-200">数秒後に、[project templates installed successfully]\(プロジェクト テンプレートが正常にインストールされました\) というポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7e96-200">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="c7e96-201">C# で `dotnet` コマンド ライン ツールを使用する</span><span class="sxs-lookup"><span data-stu-id="c7e96-201">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="c7e96-202">.NET 用 Quantum プロジェクト テンプレートを更新します</span><span class="sxs-lookup"><span data-stu-id="c7e96-202">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
