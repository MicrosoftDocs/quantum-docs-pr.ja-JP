---
title: 'Microsoft Q # 化学ライブラリのインストールと検証'
description: Microsoft Quantum の化学ライブラリをインストールし、NWChem 計算化学プラットフォームで使用する方法について説明します。
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: 48bf7bc980e238e622053f5c2bdd09604c572596
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276105"
---
# <a name="chemistry-library-installation-and-validation"></a>化学ライブラリのインストールと検証

Quantum 開発キットでは、NuGet パッケージを使用した量子化学アプリケーションがサポートされて [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) います。
他の NuGet パッケージと同様に、プロジェクトに化学ライブラリを簡単に追加できます。

**Visual Studio 2019:** Visual Studio 2019 を使用している場合は、NuGet パッケージマネージャーを使用して、quantum の化学パッケージを追加できます。
パッケージマネージャーを開くには、次のスクリーンショットのように、化学ライブラリを追加するプロジェクトを右クリックし、[NuGet パッケージの管理...] を選択します。

![Visual Studio 2019 での NuGet パッケージマネージャーの使用](~/media/vs2017-nuget-manage-packages.png)

[参照] タブで、パッケージ名 "Microsoft. Quantum." を検索します。

> [!NOTE]
> 必ず [プレリリース版を含める] をオンにしてください。

![プレリリースチェックボックスを含める](~/media/vs2017-nuget-package-search.png)

これにより、ダウンロード可能なパッケージが一覧表示されます。
左側のウィンドウで [Microsoft. Quantum. 化学] をクリックし、右側のウィンドウで最新のプレリリースバージョンを選択し、[インストール] をクリックします。

![最新の Microsoft の Quantum パッケージをインストールする](~/media/vs2017-nuget-select-chem.png)

詳細については、「[パッケージマネージャー UI ガイド](https://docs.microsoft.com/nuget/tools/package-manager-ui)」を参照してください。

または、パッケージマネージャーコンソールを使用して、コマンドラインインターフェイスを使用して、プロジェクトに量子化学ライブラリを追加することもできます。

![コマンドラインからのパッケージマネージャーコンソールの使用](~/media/vs2017-nuget-console-menu.png)

パッケージマネージャーコンソールで、次のように実行します。

```
Install-Package Microsoft.Quantum.Chemistry
```

詳細については、「[パッケージマネージャーコンソールガイド](https://docs.microsoft.com/nuget/tools/package-manager-console)」を参照してください。

**コマンドラインまたは Visual Studio Code:** コマンドラインを単独で、または Visual Studio Code 内で使用すると、コマンドを使用して `dotnet` NuGet パッケージ参照をプロジェクトに追加できます。

```dotnetcli
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a>インストールの確認 

Quantum 開発キットの残りの部分と同様に、量子化学ライブラリには、すぐに起動して実行するのに役立つ、完全にドキュメント化されたサンプルがいくつか付属しています。
これらのサンプルを使用してインストールをテストするには、[メインサンプルリポジトリ](https://github.com/Microsoft/Quantum)を複製し、サンプルのいずれかを実行します。  たとえば、サンプルを実行するには、次のようにし [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) ます。

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/chemistry/MolecularHydrogen
dotnet run
```

リポジトリを複製した後に Microsoft Visual Studio を使用して、quantum の化学ライブラリがインストールされていることを確認するには:
    1. [化学] フォルダーの ChemistrySamples ソリューションを開きます。  
    2. サンプル/1 を選択します。 スタートアッププロジェクトとしての単純な分子/MolecularHydrogen。
    3. F5 キーを押して、分子 Hydrogen クォンタムフェーズの推定デモを実行します。

エネルギーレベルの値の推定の詳細については、「[エネルギーレベルの推定の取得](xref:microsoft.quantum.chemistry.examples.energyestimate)」を参照してください。   


## <a name="using-the-quantum-development-kit-with-nwchem"></a>NWChem での Quantum 開発キットの使用 ##

MolecularHydrogen サンプルでは、手動で構成された分子入力データを使用します。  これは、小さな例では問題ありませんが、大規模な量子化学には、何百万または十億の Hamiltonians が必要です。 スケーラブルな計算化学パッケージによって生成された Hamiltonians は、手動でインポートするには大きすぎます。 

Quantum 開発キットの quantum 化学ライブラリは、計算化学パッケージで適切に動作するように設計されています。特に、環境分子サイエンス研究所 (EMSL) によって開発された、太平洋北西国立研究所で作成された[**Nwchem**](http://www.nwchem-sw.org/)計算化学プラットフォームです。
特に、 `Microsoft.Quantum.Chemistry` [Broombridge スキーマ](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)に示されている量子化学シミュレーションの問題のインスタンスを読み込むためのツールがパッケージに用意されています。これは、最近のバージョンの nwchem のエクスポートでもサポートされています。

Quantum 開発キットと共に NWChem を使用して稼働させるには、次のいずれかの方法をお勧めします。
- 「統合[Aldata/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML)」でサンプルに用意されている既存の Broombridge ファイルの使用を開始します。
- 新しい Broombridge 形式の分子入力ファイルを生成するには、 [Microsoft Quantum Development Kit 用の Emsl 矢印ビルダー](https://arrows.emsl.pnnl.gov/api/qsharp_chem)を使用します。これは、NWChem の web ベースのフロントエンドです。  
- PNNL によって提供される[Docker イメージ](https://hub.docker.com/r/nwchemorg/nwchem-qc/)を使用して、NWChem を実行します。
- お使いのプラットフォームに対して[NWChem をコンパイル](http://www.nwchem-sw.org/index.php/Compiling_NWChem)します。

NWChem を使用して、量子化モデルを使用して分析する方法の詳細については、「 [nwchem でのエンドツーエンド](xref:microsoft.quantum.chemistry.examples.endtoend)」を参照してください。

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a>サンプルで提供されている Broombridge ファイルの使用を開始する

Quantum 開発キットのサンプルリポジトリの統合[Aldata/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML)フォルダーには、Broombridge 形式の分子データファイルが含まれています。  

簡単な例として、化学ライブラリサンプル[GetGateCount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount)を使用して、Broombridge ファイルの1つから Hamiltonian を読み込み、クォンタムシミュレーション algorigthms のゲート推定を実行します。

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

Broombridge スキーマで表される分子を入力する方法の詳細については[、「ファイルからの Hamiltonian の読み込み](xref:microsoft.quantum.chemistry.examples.loadhamiltonian)」を参照してください。  

リソースの推定の詳細については、「[リソース数の取得](xref:microsoft.quantum.chemistry.examples.resourcecounts)」を参照してください。  

### <a name="getting-started-using-the-emsl-arrows-builder"></a>EMSL 矢印ビルダーの使用を開始する

EMSL 矢印は、NWChem および化学計算データベースを使用して分子データを生成するツールです。  [Microsoft Quantum Development Kit 用の Emsl 矢印ビルダーでは](https://arrows.emsl.pnnl.gov/api/qsharp_chem)、複数の分子モデルビルダーを使用してモデルを入力し、Quantum Development Kit によって使用される Broombridge データファイルを生成できます。  

EMSL ページで [' 命令 '] タブをクリックし、[' Simple 例 '] の指示に従って Broombridge ファイルを生成します。  次に、[' GetGateCount '] を実行して、これらの分子のクォンタムリソースの推定値を確認します。

### <a name="installing-nwchem-from-source"></a>ソースからの NWChem のインストール

ソースから NWChem をインストールする手順の詳細につい[ては、「PNNL」を](http://www.nwchem-sw.org/index.php/Compiling_NWChem)参照してください。

> [!TIP]
> Windows 10 から NWChem を使用する場合は、Linux 用 Windows Subsystem が最適なオプションです。
> [Ubuntu 18.04 LTS For Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab)をインストールしたら、 `ubuntu18.04` お気に入りのターミナルからを実行し、上記の手順に従ってソースから nwchem をインストールします。

ソースから NWChem をコンパイルしたら、 `yaml_driver` nwchem で提供されているスクリプトを実行して、nwchem 入力デッキから Broombridge インスタンスをすばやく作成できます。

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

このコマンドを実行すると、 `input.yaml` 現在のディレクトリ内の Broombridge 形式で新しいファイルが作成されます。

### <a name="using-nwchem-with-docker"></a>Docker での NWChem の使用

NWChem を使用するための事前に構築されたイメージは、 [Docker Hub](https://hub.docker.com)を介してクロスプラットフォームで使用できます。
使用を開始するには、ご利用のプラットフォームに応じた Docker のインストール手順に従ってください。

- [Ubuntu 用 Docker のインストール](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [MacOS 用 Docker のインストール](https://docs.docker.com/docker-for-mac/install/)
- [Docker for Windows 10 のインストール](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> Docker for Windows を使用する場合は、Docker デーモンを使用して、一時ディレクトリ (通常はドライブ) を含むドライブを共有する必要があり `C:\` ます。 詳細については、 [Docker のドキュメント](https://docs.docker.com/docker-for-windows/#shared-drives)を参照してください。

Docker をインストールしたら、Quantum 開発キットのサンプルで提供されている PowerShell モジュールを使用してイメージを実行するか、手動でイメージを実行することができます。
PowerShell の使用についてはここで詳しく説明します。Docker イメージを手動で使用する場合は、[イメージで提供さ](https://hub.docker.com/r/nwchemorg/nwchem-qc/)れているドキュメントを参照してください。

#### <a name="running-nwchem-through-powershell-core"></a>PowerShell Core を使用した NWChem の実行

Quantum 開発キットで NWChem Docker イメージを使用するには、NWChem との間でファイルの移動を処理する小さな PowerShell モジュールを用意しています。
PowerShell Core をまだインストールしていない場合は、 [GitHub の powershell リポジトリ](https://github.com/PowerShell/PowerShell#get-powershell)からクロスプラットフォームをダウンロードできます。

> [!NOTE]
> PowerShell Core は、データサイエンスおよびビジネス分析ワークフローとの相互運用性を示すために、いくつかのサンプルにも使用されます。

PowerShell Core がインストールされたら、 `InvokeNWChem.psm1` をインポートして、現在のセッションで NWChem コマンドを使用できるようにします。

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

これにより、 `Convert-NWChemToBroombridge` 現在の PowerShell セッションでコマンドを使用できるようになります。
Docker から必要なイメージをダウンロードし、それらを使用して NWChem 入力デッキを実行し、出力を Broombridge にキャプチャするには、次のように実行します。

```powershell
Convert-NWChemToBroombridge ./input.nw
```

これにより、NWChem on を実行して Broombridge ファイルが作成され `input.nw` ます。
既定では、Broombridge の出力は入力デッキと同じ名前とパスになり、拡張子は `.nw` に置き換えられ `.yaml` ます。
これは、のパラメーターを使用してオーバーライドでき `-DestinationPath` `Convert-NWChemToBroombridge` ます。
PowerShell の組み込みヘルプ機能を使用して、詳細情報を取得できます。

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```
