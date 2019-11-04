---
title: 化学ライブラリのインストールと検証 |Microsoft Docs
description: 化学ライブラリのインストールと検証
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: fd43c783fa82c7219e143a57759919606fdd197f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184204"
---
# <a name="chemistry-library-installation-and-validation"></a><span data-ttu-id="78cef-103">化学ライブラリのインストールと検証</span><span class="sxs-lookup"><span data-stu-id="78cef-103">Chemistry Library Installation and Validation</span></span>

<span data-ttu-id="78cef-104">Quantum Development Kit は、 [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) NuGet パッケージを使用した、量子化学アプリケーションのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="78cef-104">The Quantum Development Kit provides support for quantum chemistry applications through the [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) NuGet package.</span></span>
<span data-ttu-id="78cef-105">他の NuGet パッケージと同様に、プロジェクトに化学ライブラリを簡単に追加できます。</span><span class="sxs-lookup"><span data-stu-id="78cef-105">As with other NuGet packages, it's straightforward to add the chemistry library to your project.</span></span>

<span data-ttu-id="78cef-106">**Visual Studio 2019:** Visual Studio 2019 を使用している場合は、NuGet パッケージマネージャーを使用して、quantum の化学パッケージを追加できます。</span><span class="sxs-lookup"><span data-stu-id="78cef-106">**Visual Studio 2019:** If you are using Visual Studio 2019, you can add the quantum chemistry packages by using the NuGet Package Manager.</span></span>
<span data-ttu-id="78cef-107">パッケージマネージャーを開くには、次のスクリーンショットのように、化学ライブラリを追加するプロジェクトを右クリックし、[NuGet パッケージの管理...] を選択します。</span><span class="sxs-lookup"><span data-stu-id="78cef-107">To open the Package Manager, right-click on the project you'd like to add the chemistry library to and select "Manage NuGet Packages...," as in the screenshot below.</span></span>

![](~/media/vs2017-nuget-manage-packages.png)

<span data-ttu-id="78cef-108">[参照] タブで、パッケージ名 "Microsoft. Quantum." を検索します。</span><span class="sxs-lookup"><span data-stu-id="78cef-108">From the Browse tab, search for the package name "Microsoft.Quantum.Chemistry."</span></span>

> [!NOTE]
> <span data-ttu-id="78cef-109">必ず [プレリリース版を含める] をオンにしてください。</span><span class="sxs-lookup"><span data-stu-id="78cef-109">Make sure to tick "Include prerelease."</span></span>

![](~/media/vs2017-nuget-package-search.png)

<span data-ttu-id="78cef-110">これにより、ダウンロード可能なパッケージが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="78cef-110">This will list the packages available for download.</span></span>
<span data-ttu-id="78cef-111">左側のウィンドウで [Microsoft. Quantum. 化学] をクリックし、右側のウィンドウで最新のプレリリースバージョンを選択し、[インストール] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78cef-111">Click on the "Microsoft.Quantum.Chemistry on the left-hand pane, select the latest pre-release version on the right-hand pane, and click "Install":</span></span>

![](~/media/vs2017-nuget-select-chem.png)

<span data-ttu-id="78cef-112">詳細については、「[パッケージマネージャー UI ガイド](https://docs.microsoft.com/nuget/tools/package-manager-ui)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78cef-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="78cef-113">または、パッケージマネージャーコンソールを使用して、コマンドラインインターフェイスを使用して、プロジェクトに量子化学ライブラリを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="78cef-113">Alternatively, you can use the Package Manager Console to add the quantum chemistry library to your project with a command line interface.</span></span>

![](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="78cef-114">パッケージマネージャーコンソールで、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="78cef-114">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Chemistry
```

<span data-ttu-id="78cef-115">詳細については、「[パッケージマネージャーコンソールガイド](https://docs.microsoft.com/nuget/tools/package-manager-console)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78cef-115">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="78cef-116">**コマンドラインまたは Visual Studio Code:** コマンドラインを単独で、または Visual Studio Code 内から使用する場合は、`dotnet` コマンドを使用して NuGet パッケージ参照をプロジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="78cef-116">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```bash
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a><span data-ttu-id="78cef-117">インストールの確認</span><span class="sxs-lookup"><span data-stu-id="78cef-117">Verifying Your Installation</span></span> 

<span data-ttu-id="78cef-118">Quantum 開発キットの残りの部分と同様に、量子化学ライブラリには、すぐに起動して実行するのに役立つ、完全にドキュメント化されたサンプルがいくつか付属しています。</span><span class="sxs-lookup"><span data-stu-id="78cef-118">Like the rest of the Quantum Development Kit, the quantum chemistry library comes with a number of fully documented samples to help you get up and running quickly.</span></span>
<span data-ttu-id="78cef-119">これらのサンプルを使用してインストールをテストするには、[メインサンプルリポジトリ](https://github.com/Microsoft/Quantum)を複製し、サンプルのいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="78cef-119">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum), then run one of the samples.</span></span>  <span data-ttu-id="78cef-120">たとえば、 [`MolecularHydrogen`](https://github.com/Microsoft/Quantum/tree/master/Chemistry/MolecularHydrogen)サンプルを実行するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="78cef-120">For example, to run the [`MolecularHydrogen`](https://github.com/Microsoft/Quantum/tree/master/Chemistry/MolecularHydrogen) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Chemistry/MolecularHydrogen
dotnet run
```

<span data-ttu-id="78cef-121">リポジトリを複製した後に Microsoft Visual Studio を使用して、quantum の化学ライブラリがインストールされていることを確認するには:</span><span class="sxs-lookup"><span data-stu-id="78cef-121">To verify the installation of the quantum chemistry library using Microsoft Visual Studio after cloning the repository:</span></span>
    1. <span data-ttu-id="78cef-122">[化学] フォルダーの ChemistrySamples ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="78cef-122">Open the ChemistrySamples.sln solution in the Chemistry folder.</span></span>  
    2. <span data-ttu-id="78cef-123">サンプル/1 を選択します。</span><span class="sxs-lookup"><span data-stu-id="78cef-123">Select Samples/1.</span></span> <span data-ttu-id="78cef-124">スタートアッププロジェクトとしての単純な分子/MolecularHydrogen。</span><span class="sxs-lookup"><span data-stu-id="78cef-124">Simple Molecules/MolecularHydrogen as the StartUp project.</span></span>
    3. <span data-ttu-id="78cef-125">F5 キーを押して、分子 Hydrogen クォンタムフェーズの推定デモを実行します。</span><span class="sxs-lookup"><span data-stu-id="78cef-125">Press F5 to run the molecular Hydrogen quantum phase estimation demo.</span></span>

<span data-ttu-id="78cef-126">エネルギーレベルの値の推定の詳細については、「[エネルギーレベルの推定の取得](xref:microsoft.quantum.chemistry.examples.energyestimate)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78cef-126">See [Obtaining energy level estimates](xref:microsoft.quantum.chemistry.examples.energyestimate) for more information on estimating the values of energy levels.</span></span>   


## <a name="using-the-quantum-development-kit-with-nwchem"></a><span data-ttu-id="78cef-127">NWChem での Quantum 開発キットの使用</span><span class="sxs-lookup"><span data-stu-id="78cef-127">Using the Quantum Development Kit with NWChem</span></span> ##

<span data-ttu-id="78cef-128">MolecularHydrogen サンプルでは、手動で構成された分子入力データを使用します。</span><span class="sxs-lookup"><span data-stu-id="78cef-128">The MolecularHydrogen sample uses molecular input data that is manually configured.</span></span>  <span data-ttu-id="78cef-129">これは、小さな例では問題ありませんが、大規模な量子化学には、何百万または十億の Hamiltonians が必要です。</span><span class="sxs-lookup"><span data-stu-id="78cef-129">While this is fine for small examples, quantum chemistry at scale require Hamiltonians with millions or billions of terms.</span></span> <span data-ttu-id="78cef-130">スケーラブルな計算化学パッケージによって生成された Hamiltonians は、手動でインポートするには大きすぎます。</span><span class="sxs-lookup"><span data-stu-id="78cef-130">Such Hamiltonians, generated by scalable computational chemistry packages are too large to import by hand.</span></span> 

<span data-ttu-id="78cef-131">Quantum 開発キットの quantum 化学ライブラリは、コンピューティング化学パッケージで適切に動作するように設計されています。これは、特に、環境分子サイエンス研究所が開発した[**Nwchem**](http://www.nwchem-sw.org/)計算化学プラットフォームです (EMSL) (太平洋北西国立研究室)</span><span class="sxs-lookup"><span data-stu-id="78cef-131">The quantum chemistry library for the Quantum Development Kit is designed to work well with computational chemistry packages, most notably the [**NWChem**](http://www.nwchem-sw.org/) computational chemistry platform developed by the Environmental Molecular Sciences Laboratory (EMSL) at Pacific Northwest National Laboratory.</span></span>
<span data-ttu-id="78cef-132">特に、`Microsoft.Quantum.Chemistry` パッケージには、 [Broombridge スキーマ](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)に示されている量子化学シミュレーションの問題のインスタンスを読み込むためのツールが用意されています。これは、最近のバージョンの NWChem のエクスポートでもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="78cef-132">In particular, the `Microsoft.Quantum.Chemistry` package provides tools for loading instances of quantum chemistry simulation problems represented in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), also supported for export by recent versions of NWChem.</span></span>

<span data-ttu-id="78cef-133">Quantum 開発キットと共に NWChem を使用して稼働させるには、次のいずれかの方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="78cef-133">To get up and running using NWChem together with the Quantum Development Kit, we suggest one of the following methods:</span></span>
- <span data-ttu-id="78cef-134">「統合[Aldata/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML)」でサンプルに用意されている既存の Broombridge ファイルの使用を開始します。</span><span class="sxs-lookup"><span data-stu-id="78cef-134">Get started using existing Broombridge files provided with the samples at [IntegralData/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML).</span></span>
- <span data-ttu-id="78cef-135">新しい Broombridge 形式の分子入力ファイルを生成するには、 [Microsoft Quantum Development Kit 用の Emsl 矢印ビルダー](https://arrows.emsl.pnnl.gov/api/qsharp_chem)を使用します。これは、NWChem の web ベースのフロントエンドです。</span><span class="sxs-lookup"><span data-stu-id="78cef-135">Use the [EMSL Arrows Builder for the Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) which is a web-based frontend to NWChem, to generate new Broombridge-formated molecular input files.</span></span>  
- <span data-ttu-id="78cef-136">PNNL によって提供される[Docker イメージ](https://hub.docker.com/r/nwchemorg/nwchem-qc/)を使用して、NWChem を実行します。</span><span class="sxs-lookup"><span data-stu-id="78cef-136">Use the [Docker image](https://hub.docker.com/r/nwchemorg/nwchem-qc/) provided by PNNL to run NWChem, or</span></span>
- <span data-ttu-id="78cef-137">お使いのプラットフォームに対して[NWChem をコンパイル](http://www.nwchem-sw.org/index.php/Compiling_NWChem)します。</span><span class="sxs-lookup"><span data-stu-id="78cef-137">[Compile NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) for your platform.</span></span>

<span data-ttu-id="78cef-138">NWChem を使用して、量子化モデルを使用して分析する方法の詳細については、「 [nwchem でのエンドツーエンド](xref:microsoft.quantum.chemistry.examples.endtoend)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78cef-138">See [End-to-end with NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) for more information on how to work with NWChem to chemical models to analyze with the Quantum Developmen Kit chemistry library.</span></span>

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a><span data-ttu-id="78cef-139">サンプルで提供されている Broombridge ファイルの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="78cef-139">Getting started using Broombridge files provided with the samples</span></span>
<span data-ttu-id="78cef-140">Quantum 開発キットのサンプルリポジトリの統合[Aldata/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML)フォルダーには、Broombridge 形式の分子データファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="78cef-140">The [IntegralData/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML) folder in the Quantum Development Kit Samples repository contains Broombridge-formated molecule data files.</span></span>  

<span data-ttu-id="78cef-141">簡単な例として、化学ライブラリサンプル[GetGateCount](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount)を使用して、Broombridge ファイルの1つから Hamiltonian を読み込み、クォンタムシミュレーション algorigthms のゲート推定を実行します。</span><span class="sxs-lookup"><span data-stu-id="78cef-141">As a simple example, use the chemistry library sample, [GetGateCount](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount) to load the Hamiltonian from one of Broombridge files and perform gate estimates of quantum simulation algorigthms:</span></span>

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

<span data-ttu-id="78cef-142">Broombridge スキーマで表される分子を入力する方法の詳細については[、「ファイルからの Hamiltonian の読み込み](xref:microsoft.quantum.chemistry.examples.loadhamiltonian)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78cef-142">See [Loading a Hamiltonian from file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) for more information on how to input molecules represented by the Broombridge schema.</span></span>  

<span data-ttu-id="78cef-143">リソースの推定の詳細については、「[リソース数の取得](xref:microsoft.quantum.chemistry.examples.resourcecounts)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78cef-143">See [Obtaining resource counts](xref:microsoft.quantum.chemistry.examples.resourcecounts) for more information on resource estimation.</span></span>  

### <a name="getting-started-using-the-emsl-arrows-builder"></a><span data-ttu-id="78cef-144">EMSL 矢印ビルダーの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="78cef-144">Getting started using the EMSL Arrows Builder</span></span>

<span data-ttu-id="78cef-145">EMSL 矢印は、NWChem および化学計算データベースを使用して分子データを生成するツールです。</span><span class="sxs-lookup"><span data-stu-id="78cef-145">EMSL Arrows is a tool that uses NWChem and chemical computational databases to generate molecule data.</span></span>  <span data-ttu-id="78cef-146">[Microsoft Quantum Development Kit 用の Emsl 矢印ビルダーでは](https://arrows.emsl.pnnl.gov/api/qsharp_chem)、複数の分子モデルビルダーを使用してモデルを入力し、Quantum Development Kit によって使用される Broombridge データファイルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="78cef-146">[EMSL Arrows Builder for the Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) allows you to enter your model using multiple molecular model builders and generate the Broombridge datafile to be used by the Quantum Development Kit.</span></span>  

<span data-ttu-id="78cef-147">EMSL ページで [' 命令 '] タブをクリックし、[' Simple 例 '] の指示に従って Broombridge ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="78cef-147">From the EMSL page, click on the ['Instuctions'] tab, and follow the ['Simple Examples'] instructions to generate Broombridge files.</span></span>  <span data-ttu-id="78cef-148">次に、[' GetGateCount '] を実行して、これらの分子のクォンタムリソースの推定値を確認します。</span><span class="sxs-lookup"><span data-stu-id="78cef-148">Then try running the ['GetGateCount'] to see the quantum resource estimates for these molecules.</span></span>

### <a name="installing-nwchem-from-source"></a><span data-ttu-id="78cef-149">ソースからの NWChem のインストール</span><span class="sxs-lookup"><span data-stu-id="78cef-149">Installing NWChem from Source</span></span>

<span data-ttu-id="78cef-150">ソースから NWChem をインストールする手順の詳細につい[ては、「PNNL」を](http://www.nwchem-sw.org/index.php/Compiling_NWChem)参照してください。</span><span class="sxs-lookup"><span data-stu-id="78cef-150">Full instructions on how to install NWChem from source [are provided by PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).</span></span>

> [!TIP]
> <span data-ttu-id="78cef-151">Windows 10 から NWChem を使用する場合は、Linux 用 Windows Subsystem が最適なオプションです。</span><span class="sxs-lookup"><span data-stu-id="78cef-151">If you wish to use NWChem from Windows 10, the Windows Subsystem for Linux is a great option.</span></span>
> <span data-ttu-id="78cef-152">[Ubuntu 18.04 LTS For Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab)をインストールしたら、お気に入りのターミナルから `ubuntu18.04` を実行し、上記の手順に従ってソースから NWChem をインストールします。</span><span class="sxs-lookup"><span data-stu-id="78cef-152">Once you have installed [Ubuntu 18.04 LTS for Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab), run `ubuntu18.04` from your favorite terminal and follow the instructions above to install NWChem from source.</span></span>

<span data-ttu-id="78cef-153">ソースから NWChem をコンパイルしたら、NWChem で提供されている `yaml_driver` スクリプトを実行して、NWChem 入力デッキから Broombridge インスタンスをすばやく作成できます。</span><span class="sxs-lookup"><span data-stu-id="78cef-153">Once you have compiled NWChem from source, you can run the `yaml_driver` script provided with NWChem to quickly produce Broombridge instances from NWChem input decks:</span></span>

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

<span data-ttu-id="78cef-154">このコマンドを実行すると、現在のディレクトリ内の Broombridge 形式で新しい `input.yaml` ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="78cef-154">This command will create a new `input.yaml` file in the Broombridge format within your current directory.</span></span>

### <a name="using-nwchem-with-docker"></a><span data-ttu-id="78cef-155">Docker での NWChem の使用</span><span class="sxs-lookup"><span data-stu-id="78cef-155">Using NWChem with Docker</span></span>

<span data-ttu-id="78cef-156">NWChem を使用するための事前に構築されたイメージは、 [Docker Hub](https://hub.docker.com)を介してクロスプラットフォームで使用できます。</span><span class="sxs-lookup"><span data-stu-id="78cef-156">Pre-built images for using NWChem are available cross-platform via [Docker Hub](https://hub.docker.com).</span></span>
<span data-ttu-id="78cef-157">使用を開始するには、ご利用のプラットフォームに応じた Docker のインストール手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="78cef-157">To get started, follow the Docker installation instructions for your platform:</span></span>

- [<span data-ttu-id="78cef-158">Ubuntu 用 Docker のインストール</span><span class="sxs-lookup"><span data-stu-id="78cef-158">Install Docker for Ubuntu</span></span>](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [<span data-ttu-id="78cef-159">MacOS 用 Docker のインストール</span><span class="sxs-lookup"><span data-stu-id="78cef-159">Install Docker for macOS</span></span>](https://docs.docker.com/docker-for-mac/install/)
- [<span data-ttu-id="78cef-160">Docker for Windows 10 のインストール</span><span class="sxs-lookup"><span data-stu-id="78cef-160">Install Docker for Windows 10</span></span>](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> <span data-ttu-id="78cef-161">Docker for Windows を使用している場合は、Docker デーモンを使用して、一時ディレクトリ (通常は `C:\` ドライブ) を含むドライブを共有する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78cef-161">If you are using Docker for Windows, you will need to share the drive containing your temporary directory (usually this is the `C:\` drive) with the Docker daemon.</span></span> <span data-ttu-id="78cef-162">詳細については、 [Docker のドキュメント](https://docs.docker.com/docker-for-windows/#shared-drives)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78cef-162">See the [Docker documentation](https://docs.docker.com/docker-for-windows/#shared-drives) for more details.</span></span>

<span data-ttu-id="78cef-163">Docker をインストールしたら、Quantum 開発キットのサンプルで提供されている PowerShell モジュールを使用してイメージを実行するか、手動でイメージを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="78cef-163">Once you have Docker installed, you can either use the PowerShell module provided with the Quantum Development Kit samples to run the image, or you can run the image manually.</span></span>
<span data-ttu-id="78cef-164">PowerShell の使用についてはここで詳しく説明します。Docker イメージを手動で使用する場合は、[イメージで提供さ](https://hub.docker.com/r/nwchemorg/nwchem-qc/)れているドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="78cef-164">We detail using PowerShell here; if you would like to use the Docker image manually, please see the [documentation provided with the image](https://hub.docker.com/r/nwchemorg/nwchem-qc/).</span></span>

#### <a name="running-nwchem-through-powershell-core"></a><span data-ttu-id="78cef-165">PowerShell Core を使用した NWChem の実行</span><span class="sxs-lookup"><span data-stu-id="78cef-165">Running NWChem through PowerShell Core</span></span>

<span data-ttu-id="78cef-166">Quantum 開発キットで NWChem Docker イメージを使用するには、NWChem との間でファイルの移動を処理する小さな PowerShell モジュールを用意しています。</span><span class="sxs-lookup"><span data-stu-id="78cef-166">To use the NWChem Docker image with the Quantum Development Kit, we provide a small PowerShell module that handles moving files in and out of NWChem for you.</span></span>
<span data-ttu-id="78cef-167">PowerShell Core をまだインストールしていない場合は、 [GitHub の powershell リポジトリ](https://github.com/PowerShell/PowerShell#get-powershell)からクロスプラットフォームをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="78cef-167">If you don't already have PowerShell Core installed, you can download it cross-platform from the [PowerShell repository on GitHub](https://github.com/PowerShell/PowerShell#get-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="78cef-168">PowerShell Core は、データサイエンスおよびビジネス分析ワークフローとの相互運用性を示すために、いくつかのサンプルにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="78cef-168">PowerShell Core is also used for some samples to demonstrate interoperability with data science and business analytics workflows.</span></span>

<span data-ttu-id="78cef-169">PowerShell Core がインストールされたら、`InvokeNWChem.psm1` をインポートして、現在のセッションで NWChem コマンドを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="78cef-169">Once you have PowerShell Core installed, import `InvokeNWChem.psm1` to make NWChem commands available in your current session:</span></span>

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

<span data-ttu-id="78cef-170">これにより、現在の PowerShell セッションで `Convert-NWChemToBroombridge` コマンドを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="78cef-170">This will make the `Convert-NWChemToBroombridge` command available in your current PowerShell session.</span></span>
<span data-ttu-id="78cef-171">Docker から必要なイメージをダウンロードし、それらを使用して NWChem 入力デッキを実行し、出力を Broombridge にキャプチャするには、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="78cef-171">To download any needed images from Docker and use them to run NWChem input decks and capture output to Broombridge, run the following:</span></span>

```powershell
Convert-NWChemToBroombridge ./input.nw
```

<span data-ttu-id="78cef-172">これにより、`input.nw`で NWChem が実行され、Broombridge ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="78cef-172">This will create a Broombridge file by running NWChem on `input.nw`.</span></span>
<span data-ttu-id="78cef-173">既定では、Broombridge の出力には入力デッキと同じ名前とパスが使用され、`.nw` 拡張子が `.yaml`に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="78cef-173">By default, the Broombridge output will have the same name and path as the input deck, with the `.nw` extension replaced by `.yaml`.</span></span>
<span data-ttu-id="78cef-174">これは、`-DestinationPath` パラメーターを使用して `Convert-NWChemToBroombridge`することによってオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="78cef-174">This can be overridden by using the `-DestinationPath` parameter to `Convert-NWChemToBroombridge`.</span></span>
<span data-ttu-id="78cef-175">PowerShell の組み込みヘルプ機能を使用して、詳細情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="78cef-175">More information can be obtained by using PowerShell's built-in help functionality:</span></span>

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```


