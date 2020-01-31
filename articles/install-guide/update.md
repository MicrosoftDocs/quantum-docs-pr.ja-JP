---
title: Microsoft Quantum Development Kit を更新する方法 (QDK) について説明します。
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ed2a90749bbe245dde97424fc3191682f995d85b
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819741"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="dbfde-102">Microsoft Quantum Development Kit の更新 (QDK)</span><span class="sxs-lookup"><span data-stu-id="dbfde-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="dbfde-103">Microsoft Quantum Development Kit (QDK) を最新バージョンに更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dbfde-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="dbfde-104">この記事では、QDK が既にインストールされていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="dbfde-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="dbfde-105">を初めてインストールする場合は、[インストールガイド](xref:microsoft.quantum.install)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbfde-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="dbfde-106">最新の QDK リリースを常に最新の状態に保つことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dbfde-106">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="dbfde-107">最新の QDK バージョンにアップグレードするには、この更新ガイドに従ってください。</span><span class="sxs-lookup"><span data-stu-id="dbfde-107">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="dbfde-108">このプロセスは、次の2つの部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="dbfde-108">The process consists of two parts:</span></span>
1. <span data-ttu-id="dbfde-109">既存の Q # ファイルとプロジェクトを更新して、コードを更新された構文に合わせる</span><span class="sxs-lookup"><span data-stu-id="dbfde-109">updating your existing Q# files and projects to align your code with any updated syntax</span></span>
2. <span data-ttu-id="dbfde-110">選択した開発環境の QDK 自体を更新しています</span><span class="sxs-lookup"><span data-stu-id="dbfde-110">updating the QDK itself for your chosen development environment</span></span> 

## <a name="updating-q-projects"></a><span data-ttu-id="dbfde-111">Q # プロジェクトを更新しています</span><span class="sxs-lookup"><span data-stu-id="dbfde-111">Updating Q# Projects</span></span> 

<span data-ttu-id="dbfde-112">Q # 操作をホストするC#ためにまたは Python のどちらを使用しているかにかかわらず、次の手順に従って q # プロジェクトを更新します。</span><span class="sxs-lookup"><span data-stu-id="dbfde-112">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="dbfde-113">まず、 [.NET Core SDK 3.1](https://dotnet.microsoft.com/download)の最新バージョンがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbfde-113">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="dbfde-114">コマンドプロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dbfde-114">Run the following command in the command prompt:</span></span>
    ```bash
    dotnet --version
    ```
<span data-ttu-id="dbfde-115">出力が `3.1.100` 以上であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbfde-115">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="dbfde-116">インストールされていない場合は、[最新バージョン](https://dotnet.microsoft.com/download)をインストールして、もう一度確認します。</span><span class="sxs-lookup"><span data-stu-id="dbfde-116">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="dbfde-117">次に、セットアップに応じて、次の手順に従います (Visual Studio、Visual Studio Code、またはコマンドラインから直接)。</span><span class="sxs-lookup"><span data-stu-id="dbfde-117">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="dbfde-118">Visual Studio での Q # プロジェクトの更新</span><span class="sxs-lookup"><span data-stu-id="dbfde-118">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="dbfde-119">最新バージョンの Visual Studio 2019 に更新する方法について[は、こちら](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbfde-119">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
2. <span data-ttu-id="dbfde-120">Visual Studio でソリューションを開く</span><span class="sxs-lookup"><span data-stu-id="dbfde-120">Open your solution in Visual Studio</span></span>
3. <span data-ttu-id="dbfde-121">メニューから [**ビルド** -> **クリーンソリューション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbfde-121">From the menu, select **Build** -> **Clean Solution**</span></span>
4. <span data-ttu-id="dbfde-122">各 .csproj ファイルで、ターゲットフレームワークを `netcoreapp3.0` に更新します (または、ライブラリプロジェクトの場合は `netstandard2.1` ます)。</span><span class="sxs-lookup"><span data-stu-id="dbfde-122">In each of your .csproj files, update the target framework to `netcoreapp3.0` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="dbfde-123">つまり、次のような形式の行を編集します。</span><span class="sxs-lookup"><span data-stu-id="dbfde-123">That is, edit lines of the form:</span></span>
    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```
    <span data-ttu-id="dbfde-124">ターゲットフレームワークの指定の詳細については、[こちら](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbfde-124">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
5. <span data-ttu-id="dbfde-125">ソリューション内のすべてのファイルを保存して閉じる</span><span class="sxs-lookup"><span data-stu-id="dbfde-125">Save and close all files in your solution</span></span>
6. <span data-ttu-id="dbfde-126">**ツール** -> **コマンドライン** -> を選択し**開発者コマンドプロンプト**</span><span class="sxs-lookup"><span data-stu-id="dbfde-126">Select **Tools** -> **Command Line** -> **Developer Command Prompt**</span></span>
7. <span data-ttu-id="dbfde-127">ソリューション内の各プロジェクトに対して、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dbfde-127">For each project in the solution, run the following command:</span></span>
    ```bash
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```
    <span data-ttu-id="dbfde-128">プロジェクトで他の Microsoft の Quantum パッケージ (たとえば、Microsoft の Quantum) を使用している場合は、コマンドも実行します。</span><span class="sxs-lookup"><span data-stu-id="dbfde-128">If your projects use any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
8. <span data-ttu-id="dbfde-129">コマンドプロンプトを閉じ、[**ビルド** -> **ビルド**] を選択します (リビルドは最初に失敗するため、[ソリューションのリビルド] を選択しない*でください)* 。</span><span class="sxs-lookup"><span data-stu-id="dbfde-129">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution, as rebuilding will initially fail)</span></span>

<span data-ttu-id="dbfde-130">これで[、Visual Studio QDK 拡張機能を更新](#update-visual-studio-qdk-extension)することができます。</span><span class="sxs-lookup"><span data-stu-id="dbfde-130">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="dbfde-131">Visual Studio Code で Q # プロジェクトを更新する</span><span class="sxs-lookup"><span data-stu-id="dbfde-131">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="dbfde-132">Visual Studio Code で、更新するプロジェクトが格納されているフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="dbfde-132">In Visual Studio Code, open the folder containing the project to update</span></span>
2. <span data-ttu-id="dbfde-133">**ターミナル** ->  **[新しいターミナル]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbfde-133">Select **Terminal** -> **New Terminal**</span></span>
3. <span data-ttu-id="dbfde-134">コマンドラインを使用して更新するための指示に従います (すぐ下)。</span><span class="sxs-lookup"><span data-stu-id="dbfde-134">Follow the instructions for updating using the command line (directly below)</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="dbfde-135">コマンドラインを使用して Q # プロジェクトを更新する</span><span class="sxs-lookup"><span data-stu-id="dbfde-135">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="dbfde-136">プロジェクトファイルが格納されているフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="dbfde-136">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="dbfde-137">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dbfde-137">Run the following command:</span></span>
    ```bash
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="dbfde-138">各 .csproj ファイルで、ターゲットフレームワークを `netcoreapp3.0` に更新します (または、ライブラリプロジェクトの場合は `netstandard2.1` ます)。</span><span class="sxs-lookup"><span data-stu-id="dbfde-138">In each of your .csproj files, update the target framework to `netcoreapp3.0` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="dbfde-139">つまり、次のような形式の行を編集します。</span><span class="sxs-lookup"><span data-stu-id="dbfde-139">That is, edit lines of the form:</span></span>
    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```
    <span data-ttu-id="dbfde-140">ターゲットフレームワークの指定の詳細については、[こちら](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbfde-140">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
4. <span data-ttu-id="dbfde-141">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dbfde-141">Run the following command:</span></span>
    ```bash
    dotnet add package Microsoft.Quantum.Development.Kit
    ```
    <span data-ttu-id="dbfde-142">プロジェクトで他の Microsoft の Quantum パッケージ (たとえば、Microsoft の Quantum) を使用している場合は、コマンドも実行します。</span><span class="sxs-lookup"><span data-stu-id="dbfde-142">If your project uses any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
5. <span data-ttu-id="dbfde-143">すべてのファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="dbfde-143">Save and close all files.</span></span>
6. <span data-ttu-id="dbfde-144">プロジェクトの依存関係ごとに1-4 を繰り返し、メインプロジェクトが含まれているフォルダーに戻り、を実行します。</span><span class="sxs-lookup"><span data-stu-id="dbfde-144">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>
    ```bash
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="dbfde-145">Q # プロジェクトを更新したので、次の手順に従って QDK 自体を更新します。</span><span class="sxs-lookup"><span data-stu-id="dbfde-145">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="dbfde-146">QDK を更新しています</span><span class="sxs-lookup"><span data-stu-id="dbfde-146">Updating the QDK</span></span>

<span data-ttu-id="dbfde-147">QDK を更新するプロセスは、開発言語と環境によって異なります。</span><span class="sxs-lookup"><span data-stu-id="dbfde-147">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="dbfde-148">以下の開発環境を選択してください。</span><span class="sxs-lookup"><span data-stu-id="dbfde-148">Select your development environment below.</span></span>

* [<span data-ttu-id="dbfde-149">Python: IQ # extension を更新する</span><span class="sxs-lookup"><span data-stu-id="dbfde-149">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="dbfde-150">Jupyter Notebook: IQ # extension を更新する</span><span class="sxs-lookup"><span data-stu-id="dbfde-150">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="dbfde-151">Visual Studio: QDK 拡張機能を更新する</span><span class="sxs-lookup"><span data-stu-id="dbfde-151">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="dbfde-152">VS Code: QDK 拡張機能を更新する</span><span class="sxs-lookup"><span data-stu-id="dbfde-152">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="dbfde-153">コマンドラインと: C#プロジェクトテンプレートの更新</span><span class="sxs-lookup"><span data-stu-id="dbfde-153">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="dbfde-154">Python 用の IQ # の更新</span><span class="sxs-lookup"><span data-stu-id="dbfde-154">Update IQ# for Python</span></span>

1. <span data-ttu-id="dbfde-155">`iqsharp` カーネルを更新する</span><span class="sxs-lookup"><span data-stu-id="dbfde-155">Update the `iqsharp` kernel</span></span> 

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="dbfde-156">`iqsharp` のバージョンを確認する</span><span class="sxs-lookup"><span data-stu-id="dbfde-156">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="dbfde-157">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dbfde-157">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```
    <span data-ttu-id="dbfde-158">`iqsharp` のバージョンが高い場合は心配しないでください。[最新のリリース](xref:microsoft.quantum.relnotes)と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbfde-158">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="dbfde-159">`qsharp` パッケージを更新する</span><span class="sxs-lookup"><span data-stu-id="dbfde-159">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="dbfde-160">`qsharp` のバージョンを確認する</span><span class="sxs-lookup"><span data-stu-id="dbfde-160">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="dbfde-161">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dbfde-161">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
5. <span data-ttu-id="dbfde-162">`.qs` ファイルの場所から次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dbfde-162">Run the following command from the location of your `.qs` files</span></span>
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="dbfde-163">更新された QDK バージョンを使用して、既存の quantum プログラムを実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="dbfde-163">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="dbfde-164">Jupyter Notebook の IQ # を更新する</span><span class="sxs-lookup"><span data-stu-id="dbfde-164">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="dbfde-165">`iqsharp` カーネルを更新する</span><span class="sxs-lookup"><span data-stu-id="dbfde-165">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="dbfde-166">`iqsharp` のバージョンを確認する</span><span class="sxs-lookup"><span data-stu-id="dbfde-166">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="dbfde-167">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="dbfde-167">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```
    <span data-ttu-id="dbfde-168">`iqsharp` のバージョンが高い場合は心配しないでください。[最新のリリース](xref:microsoft.quantum.relnotes)と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbfde-168">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="dbfde-169">Jupyter Notebook 内のセルから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dbfde-169">Run the following command from a cell in your Jupyter Notebook:</span></span>
    ```
    %workspace reload
    ```

4. <span data-ttu-id="dbfde-170">これで、既存の Jupyter notebook を開いて、更新された QDK で実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="dbfde-170">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="dbfde-171">Visual Studio QDK 拡張機能の更新</span><span class="sxs-lookup"><span data-stu-id="dbfde-171">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="dbfde-172">Q # Visual Studio 拡張機能を更新する</span><span class="sxs-lookup"><span data-stu-id="dbfde-172">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="dbfde-173">Visual Studio によって、 [Quantum Visual studio 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)の更新を受け入れるように求められます</span><span class="sxs-lookup"><span data-stu-id="dbfde-173">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="dbfde-174">更新プログラムを受け入れる</span><span class="sxs-lookup"><span data-stu-id="dbfde-174">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="dbfde-175">プロジェクトテンプレートは、拡張機能を使用して更新されます。</span><span class="sxs-lookup"><span data-stu-id="dbfde-175">The project templates are updated with the extension.</span></span> <span data-ttu-id="dbfde-176">更新されたテンプレートは、新しく作成されたプロジェクトにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="dbfde-176">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="dbfde-177">拡張機能が更新されても、既存のプロジェクトのコードは更新されません。</span><span class="sxs-lookup"><span data-stu-id="dbfde-177">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="dbfde-178">QDK 拡張機能を更新 VS Code</span><span class="sxs-lookup"><span data-stu-id="dbfde-178">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="dbfde-179">クォンタム VS Code 拡張機能を更新する</span><span class="sxs-lookup"><span data-stu-id="dbfde-179">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="dbfde-180">再起動 VS Code</span><span class="sxs-lookup"><span data-stu-id="dbfde-180">Restart VS Code</span></span>
    - <span data-ttu-id="dbfde-181">**[拡張]** タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="dbfde-181">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="dbfde-182">Visual Studio Code 拡張機能**の Microsoft Quantum Development Kit**を選択します</span><span class="sxs-lookup"><span data-stu-id="dbfde-182">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="dbfde-183">拡張機能の再読み込み</span><span class="sxs-lookup"><span data-stu-id="dbfde-183">Reload the extension</span></span>

2. <span data-ttu-id="dbfde-184">クォンタムプロジェクトテンプレートを更新します。</span><span class="sxs-lookup"><span data-stu-id="dbfde-184">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="dbfde-185">**[表示]**  ->  **[コマンド パレット]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="dbfde-185">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="dbfde-186">**[Q #: プロジェクトテンプレートのインストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbfde-186">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="dbfde-187">数秒後に、"プロジェクトテンプレートが正常にインストールされました" というポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dbfde-187">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="dbfde-188">C#、`dotnet` コマンドラインツールの使用</span><span class="sxs-lookup"><span data-stu-id="dbfde-188">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="dbfde-189">.NET 用の Quantum プロジェクトテンプレートを更新する</span><span class="sxs-lookup"><span data-stu-id="dbfde-189">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="dbfde-190">次に、</span><span class="sxs-lookup"><span data-stu-id="dbfde-190">What's next?</span></span>

<span data-ttu-id="dbfde-191">お好みの環境で Quantum 開発キットを更新したので、引き続き quantum プログラムの開発と実行を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="dbfde-191">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="dbfde-192">プログラムをまだ作成していない場合は、[最初のクォンタムプログラム](xref:microsoft.quantum.write-program)を開始することができます。</span><span class="sxs-lookup"><span data-stu-id="dbfde-192">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
