---
title: Quantum Development Kit (QDK) を更新する
description: 'Q # プロジェクトと Microsoft Quantum Development Kit を現在のバージョンに更新する方法について説明します。'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 3245f587493ce12cfec15c8f932fd092d85f688e
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327572"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="1a240-103">Microsoft Quantum Development Kit の更新 (QDK)</span><span class="sxs-lookup"><span data-stu-id="1a240-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="1a240-104">Microsoft Quantum Development Kit (QDK) を最新バージョンに更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a240-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="1a240-105">この記事では、QDK が既にインストールされていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="1a240-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="1a240-106">を初めてインストールする場合は、[インストールガイド](xref:microsoft.quantum.install)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a240-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="1a240-107">最新の QDK リリースを常に最新の状態に保つことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1a240-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="1a240-108">最新の QDK バージョンにアップグレードするには、この更新ガイドに従ってください。</span><span class="sxs-lookup"><span data-stu-id="1a240-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="1a240-109">このプロセスは、次の2つの部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="1a240-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="1a240-110">既存の Q # ファイルとプロジェクトを更新して、コードを更新された構文でアラインします。</span><span class="sxs-lookup"><span data-stu-id="1a240-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="1a240-111">選択した開発環境の QDK 自体を更新しています。</span><span class="sxs-lookup"><span data-stu-id="1a240-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-q-projects"></a><span data-ttu-id="1a240-112">Q # プロジェクトを更新しています</span><span class="sxs-lookup"><span data-stu-id="1a240-112">Updating Q# Projects</span></span> 

<span data-ttu-id="1a240-113">Q # 操作をホストするために C# と Python のどちらを使用しているかにかかわらず、次の手順に従って Q # プロジェクトを更新します。</span><span class="sxs-lookup"><span data-stu-id="1a240-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="1a240-114">まず、 [.NET Core SDK 3.1](https://dotnet.microsoft.com/download)の最新バージョンがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1a240-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="1a240-115">コマンドプロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1a240-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="1a240-116">出力が以上であることを確認し `3.1.100` ます。</span><span class="sxs-lookup"><span data-stu-id="1a240-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="1a240-117">インストールされていない場合は、[最新バージョン](https://dotnet.microsoft.com/download)をインストールして、もう一度確認します。</span><span class="sxs-lookup"><span data-stu-id="1a240-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="1a240-118">次に、セットアップに応じて、次の手順に従います (Visual Studio、Visual Studio Code、またはコマンドラインから直接)。</span><span class="sxs-lookup"><span data-stu-id="1a240-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="1a240-119">Visual Studio での Q # プロジェクトの更新</span><span class="sxs-lookup"><span data-stu-id="1a240-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="1a240-120">最新バージョンの Visual Studio 2019 に更新する方法について[は、こちら](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a240-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions.</span></span>
2. <span data-ttu-id="1a240-121">Visual Studio でソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="1a240-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="1a240-122">メニューから、[ソリューションのクリーン**ビルド**] を選択し  ->  **Clean Solution**ます。</span><span class="sxs-lookup"><span data-stu-id="1a240-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="1a240-123">各 .csproj ファイルで、ターゲットフレームワークを `netcoreapp3.1` (または `netstandard2.1` ライブラリプロジェクトの場合は) に更新します。</span><span class="sxs-lookup"><span data-stu-id="1a240-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="1a240-124">つまり、次のような形式の行を編集します。</span><span class="sxs-lookup"><span data-stu-id="1a240-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="1a240-125">ターゲットフレームワークの指定の詳細については、[こちら](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a240-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="1a240-126">各 .csproj ファイルで、 `Microsoft.Quantum.Sdk` 次の行に示されているように、SDK をに設定します。</span><span class="sxs-lookup"><span data-stu-id="1a240-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="1a240-127">バージョン番号は使用可能な最新のものである必要があり、[リリースノート](https://docs.microsoft.com/quantum/relnotes/)を確認することによって確認できます。</span><span class="sxs-lookup"><span data-stu-id="1a240-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. <span data-ttu-id="1a240-128">ソリューション内のすべてのファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="1a240-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="1a240-129">[**ツール**  ->  **] [コマンドライン**開発者コマンドプロンプト] を選択し  ->  **Developer Command Prompt**ます。</span><span class="sxs-lookup"><span data-stu-id="1a240-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="1a240-130">または、Visual Studio のパッケージ管理コンソールを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="1a240-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="1a240-131">ソリューション内のプロジェクトごとに、次のコマンドを実行してこのパッケージを**削除**します。</span><span class="sxs-lookup"><span data-stu-id="1a240-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="1a240-132">プロジェクト**で他**の Microsoft の quantum パッケージや microsoft.....................................................</span><span class="sxs-lookup"><span data-stu-id="1a240-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="1a240-133">コマンドプロンプトを閉じ、[**ビルド**  ->  **ビルドソリューション**] を*not*選択します ([ソリューションのリビルド] は選択しないでください)。</span><span class="sxs-lookup"><span data-stu-id="1a240-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="1a240-134">これで[、Visual Studio QDK 拡張機能を更新](#update-visual-studio-qdk-extension)することができます。</span><span class="sxs-lookup"><span data-stu-id="1a240-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="1a240-135">Visual Studio Code で Q # プロジェクトを更新する</span><span class="sxs-lookup"><span data-stu-id="1a240-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="1a240-136">Visual Studio Code で、更新するプロジェクトが格納されているフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="1a240-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="1a240-137">[**ターミナル**  ->  の**新しいターミナル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a240-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="1a240-138">コマンドラインを使用して更新するための指示に従います (すぐ下)。</span><span class="sxs-lookup"><span data-stu-id="1a240-138">Follow the instructions for updating using the command line (directly below).</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="1a240-139">コマンドラインを使用して Q # プロジェクトを更新する</span><span class="sxs-lookup"><span data-stu-id="1a240-139">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="1a240-140">メインプロジェクトファイルが格納されているフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="1a240-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="1a240-141">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1a240-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="1a240-142">QDK の現在のバージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="1a240-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="1a240-143">これを見つけるには、[リリースノート](https://docs.microsoft.com/quantum/relnotes/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a240-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="1a240-144">バージョンは、のような形式になり `0.11.2006.207` ます。</span><span class="sxs-lookup"><span data-stu-id="1a240-144">The version will be in a format similar to `0.11.2006.207`.</span></span>

4. <span data-ttu-id="1a240-145">各 `.csproj` ファイルで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a240-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="1a240-146">ターゲットフレームワークをに更新 `netcoreapp3.1` `netstandard2.1` します (ライブラリプロジェクトの場合)。</span><span class="sxs-lookup"><span data-stu-id="1a240-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="1a240-147">つまり、次のような形式の行を編集します。</span><span class="sxs-lookup"><span data-stu-id="1a240-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="1a240-148">ターゲットフレームワークの指定の詳細については、[こちら](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a240-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="1a240-149">プロジェクト定義の SDK への参照を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="1a240-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="1a240-150">バージョン番号が、**手順 3**. で決定した値に対応していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1a240-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - <span data-ttu-id="1a240-151">パッケージへの参照を削除し `Microsoft.Quantum.Development.Kit` ます (存在する場合)。これは、次のエントリに指定されます。</span><span class="sxs-lookup"><span data-stu-id="1a240-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="1a240-152">すべての Microsoft クォンタムパッケージのバージョンを、QDK の最新リリースバージョン (**手順 3**で確認) に更新します。</span><span class="sxs-lookup"><span data-stu-id="1a240-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="1a240-153">これらのパッケージには、次のパターンの名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="1a240-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="1a240-154">パッケージへの参照の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1a240-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - <span data-ttu-id="1a240-155">更新したファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="1a240-155">Save the updated file.</span></span>

    - <span data-ttu-id="1a240-156">次の手順を実行して、プロジェクトの依存関係を復元します。</span><span class="sxs-lookup"><span data-stu-id="1a240-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="1a240-157">メインプロジェクトが含まれているフォルダーに戻り、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="1a240-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="1a240-158">Q # プロジェクトを更新したので、次の手順に従って QDK 自体を更新します。</span><span class="sxs-lookup"><span data-stu-id="1a240-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="1a240-159">QDK を更新しています</span><span class="sxs-lookup"><span data-stu-id="1a240-159">Updating the QDK</span></span>

<span data-ttu-id="1a240-160">QDK を更新するプロセスは、開発言語と環境によって異なります。</span><span class="sxs-lookup"><span data-stu-id="1a240-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="1a240-161">以下の開発環境を選択してください。</span><span class="sxs-lookup"><span data-stu-id="1a240-161">Select your development environment below.</span></span>

* [<span data-ttu-id="1a240-162">Python: IQ # extension を更新する</span><span class="sxs-lookup"><span data-stu-id="1a240-162">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="1a240-163">Jupyter Notebook: IQ # extension を更新する</span><span class="sxs-lookup"><span data-stu-id="1a240-163">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="1a240-164">Visual Studio: QDK 拡張機能を更新する</span><span class="sxs-lookup"><span data-stu-id="1a240-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="1a240-165">VS Code: QDK 拡張機能を更新する</span><span class="sxs-lookup"><span data-stu-id="1a240-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="1a240-166">コマンドラインと C#: プロジェクトテンプレートの更新</span><span class="sxs-lookup"><span data-stu-id="1a240-166">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="1a240-167">Python 用の IQ # の更新</span><span class="sxs-lookup"><span data-stu-id="1a240-167">Update IQ# for Python</span></span>

1. <span data-ttu-id="1a240-168">カーネルを更新する `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="1a240-168">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="1a240-169">バージョンを確認する `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="1a240-169">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="1a240-170">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a240-170">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="1a240-171">`iqsharp`バージョンが高い場合は、[最新のリリース](xref:microsoft.quantum.relnotes)と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a240-171">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="1a240-172">パッケージを更新する `qsharp`</span><span class="sxs-lookup"><span data-stu-id="1a240-172">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="1a240-173">バージョンを確認する `qsharp`</span><span class="sxs-lookup"><span data-stu-id="1a240-173">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="1a240-174">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a240-174">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="1a240-175">ファイルの場所から次のコマンドを実行します。 `.qs`</span><span class="sxs-lookup"><span data-stu-id="1a240-175">Run the following command from the location of your `.qs` files</span></span>

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="1a240-176">更新された QDK バージョンを使用して、既存の quantum プログラムを実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1a240-176">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="1a240-177">Jupyter Notebook の IQ # を更新する</span><span class="sxs-lookup"><span data-stu-id="1a240-177">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="1a240-178">カーネルを更新する `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="1a240-178">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="1a240-179">バージョンを確認する `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="1a240-179">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="1a240-180">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1a240-180">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="1a240-181">`iqsharp`バージョンが高い場合は、[最新のリリース](xref:microsoft.quantum.relnotes)と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a240-181">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="1a240-182">Jupyter Notebook 内のセルから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1a240-182">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="1a240-183">これで、既存の Jupyter notebook を開いて、更新された QDK で実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1a240-183">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="1a240-184">Visual Studio QDK 拡張機能の更新</span><span class="sxs-lookup"><span data-stu-id="1a240-184">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="1a240-185">Q # Visual Studio 拡張機能を更新する</span><span class="sxs-lookup"><span data-stu-id="1a240-185">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="1a240-186">Visual Studio によって、 [Quantum Visual studio 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)の更新を受け入れるように求められます</span><span class="sxs-lookup"><span data-stu-id="1a240-186">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="1a240-187">更新プログラムを受け入れる</span><span class="sxs-lookup"><span data-stu-id="1a240-187">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="1a240-188">プロジェクトテンプレートは、拡張機能を使用して更新されます。</span><span class="sxs-lookup"><span data-stu-id="1a240-188">The project templates are updated with the extension.</span></span> <span data-ttu-id="1a240-189">更新されたテンプレートは、新しく作成されたプロジェクトにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="1a240-189">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="1a240-190">拡張機能が更新されても、既存のプロジェクトのコードは更新されません。</span><span class="sxs-lookup"><span data-stu-id="1a240-190">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="1a240-191">QDK 拡張機能を更新 VS Code</span><span class="sxs-lookup"><span data-stu-id="1a240-191">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="1a240-192">クォンタム VS Code 拡張機能を更新する</span><span class="sxs-lookup"><span data-stu-id="1a240-192">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="1a240-193">再起動 VS Code</span><span class="sxs-lookup"><span data-stu-id="1a240-193">Restart VS Code</span></span>
    - <span data-ttu-id="1a240-194">[**拡張**] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="1a240-194">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="1a240-195">Visual Studio Code 拡張機能**の Microsoft Quantum Development Kit**を選択します</span><span class="sxs-lookup"><span data-stu-id="1a240-195">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="1a240-196">拡張機能の再読み込み</span><span class="sxs-lookup"><span data-stu-id="1a240-196">Reload the extension</span></span>

2. <span data-ttu-id="1a240-197">クォンタムプロジェクトテンプレートを更新します。</span><span class="sxs-lookup"><span data-stu-id="1a240-197">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="1a240-198">**ビュー**  ->  **コマンドパレット**にアクセス</span><span class="sxs-lookup"><span data-stu-id="1a240-198">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="1a240-199">[ **Q #: プロジェクトテンプレートのインストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a240-199">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="1a240-200">数秒後に、"プロジェクトテンプレートが正常にインストールされました" というポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a240-200">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="1a240-201">C#、 `dotnet` コマンドラインツールの使用</span><span class="sxs-lookup"><span data-stu-id="1a240-201">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="1a240-202">.NET 用の Quantum プロジェクトテンプレートを更新する</span><span class="sxs-lookup"><span data-stu-id="1a240-202">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
