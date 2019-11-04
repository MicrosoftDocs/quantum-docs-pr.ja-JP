---
title: Microsoft Quantum Development Kit を更新する方法 (QDK) について説明します。
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: fc430a77f88878437e662c5b54507f70f3c6e020
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185853"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="ab451-102">Microsoft Quantum Development Kit の更新 (QDK)</span><span class="sxs-lookup"><span data-stu-id="ab451-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="ab451-103">Microsoft Quantum Development Kit (QDK) を最新バージョンに更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ab451-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="ab451-104">この記事では、QDK が既にインストールされていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="ab451-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="ab451-105">を初めてインストールする場合は、[インストールガイド](xref:microsoft.quantum.install)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab451-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="ab451-106">更新手順は、開発環境によって異なります。</span><span class="sxs-lookup"><span data-stu-id="ab451-106">The update steps depend on your development environment.</span></span> <span data-ttu-id="ab451-107">次のセクションから環境を選択します。</span><span class="sxs-lookup"><span data-stu-id="ab451-107">Choose your environment from the following sections.</span></span>

## <a name="python"></a><span data-ttu-id="ab451-108">Python</span><span class="sxs-lookup"><span data-stu-id="ab451-108">Python</span></span>

1. <span data-ttu-id="ab451-109">`iqsharp` カーネルを更新する</span><span class="sxs-lookup"><span data-stu-id="ab451-109">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="ab451-110">`iqsharp` のバージョンを確認する</span><span class="sxs-lookup"><span data-stu-id="ab451-110">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="ab451-111">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab451-111">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. <span data-ttu-id="ab451-112">`qsharp` パッケージを更新する</span><span class="sxs-lookup"><span data-stu-id="ab451-112">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="ab451-113">`qsharp` のバージョンを確認する</span><span class="sxs-lookup"><span data-stu-id="ab451-113">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="ab451-114">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab451-114">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.9.1909.3002
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. <span data-ttu-id="ab451-115">更新された QDK バージョンを使用して、既存の quantum プログラムを実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ab451-115">You can now use the updated QDK version to run your existing quantum programs.</span></span>

## <a name="jupyter-notebooks"></a><span data-ttu-id="ab451-116">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="ab451-116">Jupyter notebooks</span></span>

1. <span data-ttu-id="ab451-117">`iqsharp` カーネルを更新する</span><span class="sxs-lookup"><span data-stu-id="ab451-117">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="ab451-118">`iqsharp` のバージョンを確認する</span><span class="sxs-lookup"><span data-stu-id="ab451-118">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="ab451-119">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab451-119">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. <span data-ttu-id="ab451-120">これで、既存の Jupyter notebook を開いて、更新された QDK で実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ab451-120">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

## <a name="c-on-windows-using-visual-studio"></a><span data-ttu-id="ab451-121">C#Windows の場合、Visual Studio の使用</span><span class="sxs-lookup"><span data-stu-id="ab451-121">C# on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="ab451-122">Q # Visual Studio 拡張機能を更新する</span><span class="sxs-lookup"><span data-stu-id="ab451-122">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="ab451-123">Visual Studio によって、 [Quantum Visual studio 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)の更新を受け入れるように求められます</span><span class="sxs-lookup"><span data-stu-id="ab451-123">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="ab451-124">更新プログラムを受け入れる</span><span class="sxs-lookup"><span data-stu-id="ab451-124">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="ab451-125">プロジェクトテンプレートは、拡張機能を使用して更新されます。</span><span class="sxs-lookup"><span data-stu-id="ab451-125">The project templates are updated with the extension.</span></span> <span data-ttu-id="ab451-126">更新されたテンプレートは、新しく作成されたプロジェクトにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="ab451-126">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="ab451-127">拡張機能が更新されても、既存のプロジェクトのコードは更新されません。</span><span class="sxs-lookup"><span data-stu-id="ab451-127">The code for your existing projects is not updated when the extension is updated.</span></span>

1. <span data-ttu-id="ab451-128">QDK パッケージを更新する</span><span class="sxs-lookup"><span data-stu-id="ab451-128">Update the QDK packages</span></span>

    - <span data-ttu-id="ab451-129">既存のアプリケーションを開く</span><span class="sxs-lookup"><span data-stu-id="ab451-129">Open an existing application</span></span>
    - <span data-ttu-id="ab451-130">ソリューションエクスプローラーでの**依存関係**の選択</span><span class="sxs-lookup"><span data-stu-id="ab451-130">Select **Dependencies** in the Solution Explorer</span></span>
    - <span data-ttu-id="ab451-131">**[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ab451-131">Select **Manage NuGet Packages**</span></span>
    - <span data-ttu-id="ab451-132">Microsoft の Quantum パッケージを最新バージョンに更新し**ます。**</span><span class="sxs-lookup"><span data-stu-id="ab451-132">Update the **Microsoft.Quantum** packages to the latest version</span></span>

1. <span data-ttu-id="ab451-133">これで、最新の QDK でアプリケーションを実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ab451-133">You can now run your application with the latest QDK.</span></span>

## <a name="c-using-vs-code"></a><span data-ttu-id="ab451-134">C#、VS Code の使用</span><span class="sxs-lookup"><span data-stu-id="ab451-134">C#, using VS Code</span></span>

1. <span data-ttu-id="ab451-135">クォンタム VS Code 拡張機能を更新する</span><span class="sxs-lookup"><span data-stu-id="ab451-135">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="ab451-136">再起動 VS Code</span><span class="sxs-lookup"><span data-stu-id="ab451-136">Restart VS Code</span></span>
    - <span data-ttu-id="ab451-137">**[拡張]** タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="ab451-137">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="ab451-138">Visual Studio Code 拡張機能**の Microsoft Quantum Development Kit**を選択します</span><span class="sxs-lookup"><span data-stu-id="ab451-138">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="ab451-139">拡張機能の再読み込み</span><span class="sxs-lookup"><span data-stu-id="ab451-139">Reload the extension</span></span>

1. <span data-ttu-id="ab451-140">クォンタムプロジェクトテンプレートを更新します。</span><span class="sxs-lookup"><span data-stu-id="ab451-140">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="ab451-141">**ビュー** -> **コマンドパレット**にアクセス</span><span class="sxs-lookup"><span data-stu-id="ab451-141">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="ab451-142">**[Q #: プロジェクトテンプレートのインストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ab451-142">Select **Q#: Install project templates**</span></span>

1. <span data-ttu-id="ab451-143">VS Code で既存のアプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="ab451-143">Open an existing application in VS Code</span></span>

   - <span data-ttu-id="ab451-144">.Csproj ファイルを編集して、新しいバージョンのパッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="ab451-144">Edit the .csproj file to add the new package versions</span></span>

    ```xml
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.9.1909.3002" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.9.1909.3002" />
    </ItemGroup>
    ```

    <span data-ttu-id="ab451-145">他の `Microsoft.Quantum` パッケージを使用する場合は、これらも更新します。</span><span class="sxs-lookup"><span data-stu-id="ab451-145">If you use other `Microsoft.Quantum` packages, update these too.</span></span>

1. <span data-ttu-id="ab451-146">更新された QDK でアプリケーションを実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ab451-146">You can now run your application with the updated QDK</span></span>

## <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="ab451-147">C#、`dotnet` コマンドラインツールの使用</span><span class="sxs-lookup"><span data-stu-id="ab451-147">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="ab451-148">.NET 用の Quantum プロジェクトテンプレートを更新する</span><span class="sxs-lookup"><span data-stu-id="ab451-148">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="ab451-149">既存のアプリケーションを更新して実行する</span><span class="sxs-lookup"><span data-stu-id="ab451-149">Update and run an existing application</span></span>

    - <span data-ttu-id="ab451-150">アプリケーションで QDK パッケージのバージョンを更新する</span><span class="sxs-lookup"><span data-stu-id="ab451-150">Update the QDK package versions in your application</span></span>

        ```bash
        dotnet add package Microsoft.Quantum.Development.Kit
        dotnet add package Microsoft.Quantum.Standard
        ```

        <span data-ttu-id="ab451-151">アプリケーションで他の `Microsoft.Quantum` パッケージを使用する場合は、これらも更新します。</span><span class="sxs-lookup"><span data-stu-id="ab451-151">If your application uses any other `Microsoft.Quantum` packages, update these too.</span></span>

    - <span data-ttu-id="ab451-152">アプリケーションを実行する</span><span class="sxs-lookup"><span data-stu-id="ab451-152">Run the application</span></span>

        ```bash
        dotnet run
        ```

    - <span data-ttu-id="ab451-153">新しいパッケージバージョンでアプリケーションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="ab451-153">Your application will run with the new package versions</span></span>

## <a name="whats-next"></a><span data-ttu-id="ab451-154">次に、</span><span class="sxs-lookup"><span data-stu-id="ab451-154">What's next?</span></span>

<span data-ttu-id="ab451-155">お好みの環境で Quantum 開発キットを更新したので、引き続き quantum プログラムの開発と実行を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ab451-155">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="ab451-156">プログラムをまだ作成していない場合は、[最初のクォンタムプログラム](xref:microsoft.quantum.write-program)を開始することができます。</span><span class="sxs-lookup"><span data-stu-id="ab451-156">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
