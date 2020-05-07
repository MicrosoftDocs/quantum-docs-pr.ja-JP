---
title: Microsoft Quantum Development Kit を更新する方法 (QDK) について説明します。
description: 'Q # プロジェクトと Microsoft Quantum Development Kit を現在のバージョンに更新する方法について説明します。'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: bf6d6d3d80af485b555429f25b125bfea685bebf
ms.sourcegitcommit: c57c271ab73f75f165401651fad2b5bc143e9c8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "82862209"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="998f6-103">Microsoft Quantum Development Kit の更新 (QDK)</span><span class="sxs-lookup"><span data-stu-id="998f6-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="998f6-104">Microsoft Quantum Development Kit (QDK) を最新バージョンに更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="998f6-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="998f6-105">この記事では、QDK が既にインストールされていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="998f6-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="998f6-106">を初めてインストールする場合は、[インストールガイド](xref:microsoft.quantum.install)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="998f6-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="998f6-107">最新の QDK リリースを常に最新の状態に保つことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="998f6-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="998f6-108">最新の QDK バージョンにアップグレードするには、この更新ガイドに従ってください。</span><span class="sxs-lookup"><span data-stu-id="998f6-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="998f6-109">このプロセスは、次の2つの部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="998f6-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="998f6-110">既存の Q # ファイルとプロジェクトを更新して、コードを更新された構文に合わせる</span><span class="sxs-lookup"><span data-stu-id="998f6-110">updating your existing Q# files and projects to align your code with any updated syntax</span></span>
2. <span data-ttu-id="998f6-111">選択した開発環境の QDK 自体を更新しています</span><span class="sxs-lookup"><span data-stu-id="998f6-111">updating the QDK itself for your chosen development environment</span></span> 

## <a name="updating-q-projects"></a><span data-ttu-id="998f6-112">Q # プロジェクトを更新しています</span><span class="sxs-lookup"><span data-stu-id="998f6-112">Updating Q# Projects</span></span> 

<span data-ttu-id="998f6-113">Q # 操作をホストするために C# と Python のどちらを使用しているかにかかわらず、次の手順に従って Q # プロジェクトを更新します。</span><span class="sxs-lookup"><span data-stu-id="998f6-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="998f6-114">まず、 [.NET Core SDK 3.1](https://dotnet.microsoft.com/download)の最新バージョンがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="998f6-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="998f6-115">コマンドプロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="998f6-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="998f6-116">出力が`3.1.100`以上であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="998f6-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="998f6-117">インストールされていない場合は、[最新バージョン](https://dotnet.microsoft.com/download)をインストールして、もう一度確認します。</span><span class="sxs-lookup"><span data-stu-id="998f6-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="998f6-118">次に、セットアップに応じて、次の手順に従います (Visual Studio、Visual Studio Code、またはコマンドラインから直接)。</span><span class="sxs-lookup"><span data-stu-id="998f6-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="998f6-119">Visual Studio での Q # プロジェクトの更新</span><span class="sxs-lookup"><span data-stu-id="998f6-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="998f6-120">最新バージョンの Visual Studio 2019 に更新する方法について[は、こちら](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="998f6-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
2. <span data-ttu-id="998f6-121">Visual Studio でソリューションを開く</span><span class="sxs-lookup"><span data-stu-id="998f6-121">Open your solution in Visual Studio</span></span>
3. <span data-ttu-id="998f6-122">メニューから、[**ソリューションのクリーン\*\*\*\*ビルド** -> ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="998f6-122">From the menu, select **Build** -> **Clean Solution**</span></span>
4. <span data-ttu-id="998f6-123">各 .csproj ファイルで、ターゲットフレームワークを (またはライブラリプロジェクト`netcoreapp3.1`の場合`netstandard2.1`は) に更新します。</span><span class="sxs-lookup"><span data-stu-id="998f6-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="998f6-124">つまり、次のような形式の行を編集します。</span><span class="sxs-lookup"><span data-stu-id="998f6-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="998f6-125">ターゲットフレームワークの指定の詳細については、[こちら](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="998f6-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
5. <span data-ttu-id="998f6-126">ソリューション内のすべてのファイルを保存して閉じる</span><span class="sxs-lookup"><span data-stu-id="998f6-126">Save and close all files in your solution</span></span>
6. <span data-ttu-id="998f6-127">**ツール** -> の**コマンドライン** -> を選択し**開発者コマンドプロンプト**</span><span class="sxs-lookup"><span data-stu-id="998f6-127">Select **Tools** -> **Command Line** -> **Developer Command Prompt**</span></span>
7. <span data-ttu-id="998f6-128">ソリューション内の各プロジェクトに対して、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="998f6-128">For each project in the solution, run the following command:</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="998f6-129">プロジェクトで他の Microsoft の Quantum パッケージ (たとえば、Microsoft の Quantum) を使用している場合は、コマンドも実行します。</span><span class="sxs-lookup"><span data-stu-id="998f6-129">If your projects use any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
8. <span data-ttu-id="998f6-130">コマンドプロンプトを閉じ、[**ビルド** -> **ビルドソリューション**] を選択します ([ソリューションのリビルド *] は選択しないでください)*</span><span class="sxs-lookup"><span data-stu-id="998f6-130">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution)</span></span>

<span data-ttu-id="998f6-131">これで[、Visual Studio QDK 拡張機能を更新](#update-visual-studio-qdk-extension)することができます。</span><span class="sxs-lookup"><span data-stu-id="998f6-131">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="998f6-132">Visual Studio Code で Q # プロジェクトを更新する</span><span class="sxs-lookup"><span data-stu-id="998f6-132">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="998f6-133">Visual Studio Code で、更新するプロジェクトが格納されているフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="998f6-133">In Visual Studio Code, open the folder containing the project to update</span></span>
2. <span data-ttu-id="998f6-134">**ターミナル** -> の**新しいターミナル**を選択する</span><span class="sxs-lookup"><span data-stu-id="998f6-134">Select **Terminal** -> **New Terminal**</span></span>
3. <span data-ttu-id="998f6-135">コマンドラインを使用して更新するための指示に従います (すぐ下)。</span><span class="sxs-lookup"><span data-stu-id="998f6-135">Follow the instructions for updating using the command line (directly below)</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="998f6-136">コマンドラインを使用して Q # プロジェクトを更新する</span><span class="sxs-lookup"><span data-stu-id="998f6-136">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="998f6-137">プロジェクトファイルが格納されているフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="998f6-137">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="998f6-138">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="998f6-138">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="998f6-139">各 .csproj ファイルで、ターゲットフレームワークを (またはライブラリプロジェクト`netcoreapp3.1`の場合`netstandard2.1`は) に更新します。</span><span class="sxs-lookup"><span data-stu-id="998f6-139">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="998f6-140">つまり、次のような形式の行を編集します。</span><span class="sxs-lookup"><span data-stu-id="998f6-140">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="998f6-141">ターゲットフレームワークの指定の詳細については、[こちら](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="998f6-141">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
4. <span data-ttu-id="998f6-142">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="998f6-142">Run the following command:</span></span>

    ```dotnetcli
    dotnet add package Microsoft.Quantum.Development.Kit
    ```

    <span data-ttu-id="998f6-143">プロジェクトで他の Microsoft の Quantum パッケージ (たとえば、Microsoft の Quantum) を使用している場合は、コマンドも実行します。</span><span class="sxs-lookup"><span data-stu-id="998f6-143">If your project uses any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
5. <span data-ttu-id="998f6-144">すべてのファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="998f6-144">Save and close all files.</span></span>
6. <span data-ttu-id="998f6-145">プロジェクトの依存関係ごとに1-4 を繰り返し、メインプロジェクトが含まれているフォルダーに戻り、を実行します。</span><span class="sxs-lookup"><span data-stu-id="998f6-145">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="998f6-146">Q # プロジェクトを更新したので、次の手順に従って QDK 自体を更新します。</span><span class="sxs-lookup"><span data-stu-id="998f6-146">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="998f6-147">QDK を更新しています</span><span class="sxs-lookup"><span data-stu-id="998f6-147">Updating the QDK</span></span>

<span data-ttu-id="998f6-148">QDK を更新するプロセスは、開発言語と環境によって異なります。</span><span class="sxs-lookup"><span data-stu-id="998f6-148">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="998f6-149">以下の開発環境を選択してください。</span><span class="sxs-lookup"><span data-stu-id="998f6-149">Select your development environment below.</span></span>

* [<span data-ttu-id="998f6-150">Python: IQ # extension を更新する</span><span class="sxs-lookup"><span data-stu-id="998f6-150">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="998f6-151">Jupyter Notebook: IQ # extension を更新する</span><span class="sxs-lookup"><span data-stu-id="998f6-151">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="998f6-152">Visual Studio: QDK 拡張機能を更新する</span><span class="sxs-lookup"><span data-stu-id="998f6-152">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="998f6-153">VS Code: QDK 拡張機能を更新する</span><span class="sxs-lookup"><span data-stu-id="998f6-153">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="998f6-154">コマンドラインと C#: プロジェクトテンプレートの更新</span><span class="sxs-lookup"><span data-stu-id="998f6-154">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="998f6-155">Python 用の IQ # の更新</span><span class="sxs-lookup"><span data-stu-id="998f6-155">Update IQ# for Python</span></span>

1. <span data-ttu-id="998f6-156">カーネルを`iqsharp`更新する</span><span class="sxs-lookup"><span data-stu-id="998f6-156">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="998f6-157">バージョンを`iqsharp`確認する</span><span class="sxs-lookup"><span data-stu-id="998f6-157">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="998f6-158">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="998f6-158">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="998f6-159">バージョンが高い場合は、最新のリリースと一致している必要があります。 [latest release](xref:microsoft.quantum.relnotes) `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="998f6-159">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="998f6-160">パッケージを`qsharp`更新する</span><span class="sxs-lookup"><span data-stu-id="998f6-160">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="998f6-161">バージョンを`qsharp`確認する</span><span class="sxs-lookup"><span data-stu-id="998f6-161">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="998f6-162">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="998f6-162">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="998f6-163">`.qs`ファイルの場所から次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="998f6-163">Run the following command from the location of your `.qs` files</span></span>

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="998f6-164">更新された QDK バージョンを使用して、既存の quantum プログラムを実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="998f6-164">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="998f6-165">Jupyter Notebook の IQ # を更新する</span><span class="sxs-lookup"><span data-stu-id="998f6-165">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="998f6-166">カーネルを`iqsharp`更新する</span><span class="sxs-lookup"><span data-stu-id="998f6-166">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="998f6-167">バージョンを`iqsharp`確認する</span><span class="sxs-lookup"><span data-stu-id="998f6-167">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="998f6-168">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="998f6-168">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="998f6-169">バージョンが高い場合は、最新のリリースと一致している必要があります。 [latest release](xref:microsoft.quantum.relnotes) `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="998f6-169">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="998f6-170">Jupyter Notebook 内のセルから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="998f6-170">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="998f6-171">これで、既存の Jupyter notebook を開いて、更新された QDK で実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="998f6-171">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="998f6-172">Visual Studio QDK 拡張機能の更新</span><span class="sxs-lookup"><span data-stu-id="998f6-172">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="998f6-173">Q # Visual Studio 拡張機能を更新する</span><span class="sxs-lookup"><span data-stu-id="998f6-173">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="998f6-174">Visual Studio によって、 [Quantum Visual studio 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)の更新を受け入れるように求められます</span><span class="sxs-lookup"><span data-stu-id="998f6-174">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="998f6-175">更新プログラムを受け入れる</span><span class="sxs-lookup"><span data-stu-id="998f6-175">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="998f6-176">プロジェクトテンプレートは、拡張機能を使用して更新されます。</span><span class="sxs-lookup"><span data-stu-id="998f6-176">The project templates are updated with the extension.</span></span> <span data-ttu-id="998f6-177">更新されたテンプレートは、新しく作成されたプロジェクトにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="998f6-177">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="998f6-178">拡張機能が更新されても、既存のプロジェクトのコードは更新されません。</span><span class="sxs-lookup"><span data-stu-id="998f6-178">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="998f6-179">QDK 拡張機能を更新 VS Code</span><span class="sxs-lookup"><span data-stu-id="998f6-179">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="998f6-180">クォンタム VS Code 拡張機能を更新する</span><span class="sxs-lookup"><span data-stu-id="998f6-180">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="998f6-181">再起動 VS Code</span><span class="sxs-lookup"><span data-stu-id="998f6-181">Restart VS Code</span></span>
    - <span data-ttu-id="998f6-182">[**拡張**] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="998f6-182">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="998f6-183">Visual Studio Code 拡張機能**の Microsoft Quantum Development Kit**を選択します</span><span class="sxs-lookup"><span data-stu-id="998f6-183">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="998f6-184">拡張機能の再読み込み</span><span class="sxs-lookup"><span data-stu-id="998f6-184">Reload the extension</span></span>

2. <span data-ttu-id="998f6-185">クォンタムプロジェクトテンプレートを更新します。</span><span class="sxs-lookup"><span data-stu-id="998f6-185">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="998f6-186">**ビュー** -> **コマンドパレット**にアクセス</span><span class="sxs-lookup"><span data-stu-id="998f6-186">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="998f6-187">[ **Q #: プロジェクトテンプレートのインストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="998f6-187">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="998f6-188">数秒後に、"プロジェクトテンプレートが正常にインストールされました" というポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="998f6-188">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="998f6-189">C#、コマンドライン`dotnet`ツールの使用</span><span class="sxs-lookup"><span data-stu-id="998f6-189">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="998f6-190">.NET 用の Quantum プロジェクトテンプレートを更新する</span><span class="sxs-lookup"><span data-stu-id="998f6-190">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="998f6-191">次の内容</span><span class="sxs-lookup"><span data-stu-id="998f6-191">What's next?</span></span>

<span data-ttu-id="998f6-192">お好みの環境で Quantum 開発キットを更新したので、引き続き quantum プログラムの開発と実行を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="998f6-192">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="998f6-193">プログラムをまだ作成していない場合は、[最初のクォンタムプログラム](xref:microsoft.quantum.write-program)を開始することができます。</span><span class="sxs-lookup"><span data-stu-id="998f6-193">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
