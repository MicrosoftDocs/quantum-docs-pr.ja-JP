---
title: Microsoft Quantum Development Kit を更新する方法 (QDK) について説明します。
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ebf1f15d65a12c921cd3f04e4111d463d1060f8e
ms.sourcegitcommit: c93fea5980d1d46fbda1e7c7153831b9337134bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2019
ms.locfileid: "73463283"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="2d400-102">Microsoft Quantum Development Kit の更新 (QDK)</span><span class="sxs-lookup"><span data-stu-id="2d400-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="2d400-103">Microsoft Quantum Development Kit (QDK) を最新バージョンに更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2d400-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="2d400-104">この記事では、QDK が既にインストールされていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="2d400-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="2d400-105">を初めてインストールする場合は、[インストールガイド](xref:microsoft.quantum.install)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d400-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>


## <a name="updating-q-projects"></a><span data-ttu-id="2d400-106">Q # プロジェクトを更新しています</span><span class="sxs-lookup"><span data-stu-id="2d400-106">Updating Q# Projects</span></span> 

1. <span data-ttu-id="2d400-107">まず、 [.NET Core SDK 3.0](https://dotnet.microsoft.com/download)の最新バージョンをインストールし、コマンドプロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d400-107">First, install the latest version of the [.NET Core SDK 3.0](https://dotnet.microsoft.com/download) and run the following command in the command prompt:</span></span>
```bash
dotnet --version
```
 <span data-ttu-id="2d400-108">出力が3.0.100 以上であることを確認してから、セットアップに応じて次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2d400-108">Verify the output is 3.0.100 or higher, then follow the instructions below depending on your setup.</span></span>

### <a name="in-visual-studio"></a><span data-ttu-id="2d400-109">Visual Studio で使用する</span><span class="sxs-lookup"><span data-stu-id="2d400-109">In Visual Studio</span></span>
 
 1. <span data-ttu-id="2d400-110">最新バージョンの Visual Studio 2019 に更新する方法について[は、こちら](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d400-110">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
 2. <span data-ttu-id="2d400-111">Visual Studio でソリューションを開く</span><span class="sxs-lookup"><span data-stu-id="2d400-111">Open your solution in Visual Studio</span></span>
 3. <span data-ttu-id="2d400-112">メニューから [ビルド > クリーンソリューション] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2d400-112">From the menu, select Build > Clean Solution</span></span> 
 4. <span data-ttu-id="2d400-113">各 .csproj ファイルの[ターゲットフレームワーク](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework)を netcoreapp 3.0 (または、ライブラリプロジェクトの場合は netstandard 2.1) に更新します。</span><span class="sxs-lookup"><span data-stu-id="2d400-113">[Update the target framework](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) in each of your .csproj files to netcoreapp3.0 (or netstandard2.1 if it is a library project)</span></span>
 5. <span data-ttu-id="2d400-114">ソリューション内のすべてのファイルを保存して閉じる</span><span class="sxs-lookup"><span data-stu-id="2d400-114">Save and close all files in your solution</span></span>
 6. <span data-ttu-id="2d400-115">ツール > コマンドライン > を選択し開発者コマンドプロンプト</span><span class="sxs-lookup"><span data-stu-id="2d400-115">Select Tools > Command Line > Developer Command Prompt</span></span>
 7. <span data-ttu-id="2d400-116">ソリューション内の各プロジェクトに対して、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d400-116">For each project in the solution, run the following command:</span></span>
 ```bash
 dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
 ```
<span data-ttu-id="2d400-117">プロジェクトで他の Microsoft の Quantum パッケージが使用されている場合は、コマンドも実行します。</span><span class="sxs-lookup"><span data-stu-id="2d400-117">If your projects use any other Microsoft.Quantum packages, run the command for these too.</span></span> 
 8. <span data-ttu-id="2d400-118">コマンドプロンプトを閉じ、[ビルド > ビルド] を選択します (リビルドは最初に失敗するため、[ソリューションのリビルド] を選択しない*でください)* 。</span><span class="sxs-lookup"><span data-stu-id="2d400-118">Close the command prompt and select Build > Build Solution (do *not* select Rebuild Solution, as rebuilding will initially fail)</span></span>

### <a name="in-visual-studio-code"></a><span data-ttu-id="2d400-119">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="2d400-119">In Visual Studio Code</span></span>

1. <span data-ttu-id="2d400-120">Visual Studio Code で、更新するプロジェクトが格納されているフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="2d400-120">In Visual Studio Code, open the folder containing the project to update</span></span>
1. <span data-ttu-id="2d400-121">ターミナル > [新しいターミナル] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2d400-121">Select Terminal > New Terminal</span></span>
1. <span data-ttu-id="2d400-122">コマンドラインを使用して更新するための手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2d400-122">Follow the instructions for updating using the command line</span></span>

### <a name="using-the-command-line"></a><span data-ttu-id="2d400-123">コマンドラインの使用</span><span class="sxs-lookup"><span data-stu-id="2d400-123">Using the command line</span></span>

1. <span data-ttu-id="2d400-124">プロジェクトファイルが格納されているフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="2d400-124">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="2d400-125">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d400-125">Run the following command:</span></span>
```bash
dotnet clean [project_name].csproj
```

3. <span data-ttu-id="2d400-126">各 .csproj ファイルの[ターゲットフレームワーク](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)を netcoreapp 3.0 (または、ライブラリプロジェクトの場合は netstandard 2.1) に更新します。</span><span class="sxs-lookup"><span data-stu-id="2d400-126">[Update the target framework](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) in each of your .csproj files to netcoreapp3.0 (or netstandard2.1 if it is a library project)</span></span>
4. <span data-ttu-id="2d400-127">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d400-127">Run the following command:</span></span>
```bash
dotnet add package Microsoft.Quantum.Development.Kit
```
<span data-ttu-id="2d400-128">プロジェクトで他の Microsoft の Quantum パッケージが使用されている場合は、コマンドも実行します。</span><span class="sxs-lookup"><span data-stu-id="2d400-128">if your project uses any other Microsoft.Quantum packages, run the command for these too.</span></span>

5. <span data-ttu-id="2d400-129">すべてのファイルを保存して閉じる</span><span class="sxs-lookup"><span data-stu-id="2d400-129">Save and close all files</span></span>
6. <span data-ttu-id="2d400-130">プロジェクトの依存関係ごとに1-4 を繰り返し、メインプロジェクトが含まれているフォルダーに戻り、を実行します。</span><span class="sxs-lookup"><span data-stu-id="2d400-130">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>
```bash
dotnet build [project_name].csproj
```

## <a name="update-iq-for-python"></a><span data-ttu-id="2d400-131">Python 用の IQ # の更新</span><span class="sxs-lookup"><span data-stu-id="2d400-131">Update IQ# for Python</span></span>

1. <span data-ttu-id="2d400-132">`iqsharp` カーネルを更新する</span><span class="sxs-lookup"><span data-stu-id="2d400-132">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="2d400-133">`iqsharp` のバージョンを確認する</span><span class="sxs-lookup"><span data-stu-id="2d400-133">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="2d400-134">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d400-134">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```

1. <span data-ttu-id="2d400-135">`qsharp` パッケージを更新する</span><span class="sxs-lookup"><span data-stu-id="2d400-135">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="2d400-136">`qsharp` のバージョンを確認する</span><span class="sxs-lookup"><span data-stu-id="2d400-136">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="2d400-137">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d400-137">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1911.307
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
1. <span data-ttu-id="2d400-138">`.qs` ファイルの場所から次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d400-138">Run the following command from the location of your `.qs` files</span></span>
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

1. <span data-ttu-id="2d400-139">更新された QDK バージョンを使用して、既存の quantum プログラムを実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2d400-139">You can now use the updated QDK version to run your existing quantum programs.</span></span>

## <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="2d400-140">Jupyter notebook の IQ # を更新する</span><span class="sxs-lookup"><span data-stu-id="2d400-140">Update IQ# for Jupyter notebooks</span></span>

1. <span data-ttu-id="2d400-141">`iqsharp` カーネルを更新する</span><span class="sxs-lookup"><span data-stu-id="2d400-141">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="2d400-142">`iqsharp` のバージョンを確認する</span><span class="sxs-lookup"><span data-stu-id="2d400-142">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="2d400-143">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d400-143">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```
1. <span data-ttu-id="2d400-144">Jupyter Notebook 内のセルから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d400-144">Run the following command from a cell in your Jupyter Notebook:</span></span>
    ```
    %workspace reload
    ```

1. <span data-ttu-id="2d400-145">これで、既存の Jupyter notebook を開いて、更新された QDK で実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2d400-145">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

## <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="2d400-146">Visual Studio QDK 拡張機能の更新</span><span class="sxs-lookup"><span data-stu-id="2d400-146">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="2d400-147">Q # Visual Studio 拡張機能を更新する</span><span class="sxs-lookup"><span data-stu-id="2d400-147">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="2d400-148">Visual Studio によって、 [Quantum Visual studio 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)の更新を受け入れるように求められます</span><span class="sxs-lookup"><span data-stu-id="2d400-148">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="2d400-149">更新プログラムを受け入れる</span><span class="sxs-lookup"><span data-stu-id="2d400-149">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="2d400-150">プロジェクトテンプレートは、拡張機能を使用して更新されます。</span><span class="sxs-lookup"><span data-stu-id="2d400-150">The project templates are updated with the extension.</span></span> <span data-ttu-id="2d400-151">更新されたテンプレートは、新しく作成されたプロジェクトにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="2d400-151">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="2d400-152">拡張機能が更新されても、既存のプロジェクトのコードは更新されません。</span><span class="sxs-lookup"><span data-stu-id="2d400-152">The code for your existing projects is not updated when the extension is updated.</span></span>

## <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="2d400-153">QDK 拡張機能を更新 VS Code</span><span class="sxs-lookup"><span data-stu-id="2d400-153">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="2d400-154">クォンタム VS Code 拡張機能を更新する</span><span class="sxs-lookup"><span data-stu-id="2d400-154">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="2d400-155">再起動 VS Code</span><span class="sxs-lookup"><span data-stu-id="2d400-155">Restart VS Code</span></span>
    - <span data-ttu-id="2d400-156">**[拡張]** タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="2d400-156">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="2d400-157">Visual Studio Code 拡張機能**の Microsoft Quantum Development Kit**を選択します</span><span class="sxs-lookup"><span data-stu-id="2d400-157">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="2d400-158">拡張機能の再読み込み</span><span class="sxs-lookup"><span data-stu-id="2d400-158">Reload the extension</span></span>

1. <span data-ttu-id="2d400-159">クォンタムプロジェクトテンプレートを更新します。</span><span class="sxs-lookup"><span data-stu-id="2d400-159">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="2d400-160">**[表示]**  ->  **[コマンド パレット]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="2d400-160">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="2d400-161">**[Q #: プロジェクトテンプレートのインストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2d400-161">Select **Q#: Install project templates**</span></span>

## <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="2d400-162">C#、`dotnet` コマンドラインツールの使用</span><span class="sxs-lookup"><span data-stu-id="2d400-162">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="2d400-163">.NET 用の Quantum プロジェクトテンプレートを更新する</span><span class="sxs-lookup"><span data-stu-id="2d400-163">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="2d400-164">次に、</span><span class="sxs-lookup"><span data-stu-id="2d400-164">What's next?</span></span>

<span data-ttu-id="2d400-165">お好みの環境で Quantum 開発キットを更新したので、引き続き quantum プログラムの開発と実行を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2d400-165">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="2d400-166">プログラムをまだ作成していない場合は、[最初のクォンタムプログラム](xref:microsoft.quantum.write-program)を開始することができます。</span><span class="sxs-lookup"><span data-stu-id="2d400-166">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
