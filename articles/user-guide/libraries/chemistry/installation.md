---
title: Microsoft Q# 化学ライブラリのインストール
description: Microsoft Quantum の化学ライブラリをインストールし、NWChem 計算化学プラットフォームで使用する方法について説明します。
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.installation
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5d32544bbce527a376345023d5549308fd4e7c79
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854076"
---
# <a name="chemistry-library-installation"></a>化学ライブラリのインストール

[ **MolecularHydrogen** サンプル](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen)では、手動で構成された分子入力データを使用します。
これは、小さな例では問題ありませんが、大規模な量子化学では、何百万または十億の Hamiltonians を持つ必要があります。
スケーラブルな計算化学パッケージによって生成されるこのような Hamiltonians は、大きすぎて手動でインポートすることはできません。

Quantum 開発キットの quantum 化学ライブラリは、計算化学パッケージで適切に動作するように設計されています。特に、環境分子サイエンス研究所 (EMSL) によって開発された、太平洋北西国立研究所で作成された [**Nwchem**](http://www.nwchem-sw.org/) 計算化学プラットフォームです。
特に、 [Broombridge スキーマ](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)に示されている量子化学シミュレーションの問題のインスタンスを読み込むためのツールを提供しています。 [ これは、](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry)最近のバージョンの nwchem のエクスポートでもサポートされています。

Quantum Development Kit 化学ライブラリには、 `qdk-chem` 従来の形式と [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)を変換するためのコマンドラインツールも用意されています。

このセクションでは、Broombridge、または従来の形式とを使用して、Quantum 開発キットを使用する方法について詳しく説明し `qdk-chem` ます。

## <a name="using-the-quantum-development-kit-with-nwchem"></a>NWChem での Quantum 開発キットの使用

Quantum 開発キットと共に NWChem を使用して稼働させるには、次のいずれかの方法を使用します。

- 「統合 [Aldata/YAML](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML)」でサンプルに用意されている既存の Broombridge ファイルの使用を開始します。
- 新しい Broombridge 形式の分子入力ファイルを生成するには、 [Microsoft Quantum Development Kit 用の Emsl 矢印ビルダー](https://arrows.emsl.pnnl.gov/api/qsharp_chem) を使用します。これは、NWChem の web ベースのフロントエンドです。  
- PNNL によって提供される [Docker イメージ](https://hub.docker.com/r/nwchemorg/nwchem-qc/) を使用して、NWChem を実行します。
- お使いのプラットフォームに対して[NWChem をコンパイル](http://www.nwchem-sw.org/index.php/Compiling_NWChem)します。

NWChem を使用して、量子化モデルを使用して分析する方法の詳細については、「 [nwchem でのエンドツーエンド](xref:microsoft.quantum.chemistry.examples.endtoend) 」を参照してください。

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a>サンプルで提供されている Broombridge ファイルの使用を開始する

Quantum 開発キットのサンプルリポジトリの統合 [Aldata/YAML](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML) フォルダーには、Broombridge 形式の分子データファイルが含まれています。  

簡単な例として、化学ライブラリサンプル [GetGateCount](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/GetGateCount) を使用して、Broombridge ファイルの1つから Hamiltonian を読み込み、クォンタムシミュレーション algorigthms のゲート推定を実行します。

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

Broombridge スキーマで表される分子を入力する方法の詳細については [、「ファイルからの Hamiltonian の読み込み](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) 」を参照してください。  

リソースの推定の詳細については、「 [リソース数の取得](xref:microsoft.quantum.chemistry.examples.resourcecounts) 」を参照してください。  

### <a name="getting-started-using-the-emsl-arrows-builder"></a>EMSL 矢印ビルダーの使用を開始する

EMSL 矢印は、NWChem および化学計算データベースを使用して分子データを生成するツールです。  [Microsoft Quantum Development Kit 用の Emsl 矢印ビルダーでは](https://arrows.emsl.pnnl.gov/api/qsharp_chem) 、複数の分子モデルビルダーを使用してモデルを入力し、Quantum Development Kit によって使用される Broombridge データファイルを生成できます。  

EMSL ページで [' 命令 '] タブをクリックし、[' Simple 例 '] の指示に従って Broombridge ファイルを生成します。  次に、[' GetGateCount '] を実行して、これらの分子のクォンタムリソースの推定値を確認します。

### <a name="installing-nwchem-from-source"></a>ソースからの NWChem のインストール

ソースから NWChem をインストールする手順の詳細につい [ては、「PNNL」を](http://www.nwchem-sw.org/index.php/Compiling_NWChem)参照してください。

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
> Docker for Windows を使用する場合は、Docker デーモンを使用して、一時ディレクトリ (通常はドライブ) を含むドライブを共有する必要があり `C:\` ます。 詳細については、 [Docker のドキュメント](https://docs.docker.com/docker-for-windows/#shared-drives) を参照してください。

Docker をインストールしたら、Quantum 開発キットのサンプルで提供されている PowerShell モジュールを使用してイメージを実行するか、手動でイメージを実行することができます。
PowerShell の使用についてはここで詳しく説明します。Docker イメージを手動で使用する場合は、 [イメージで提供さ](https://hub.docker.com/r/nwchemorg/nwchem-qc/)れているドキュメントを参照してください。

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

## <a name="using-the-quantum-development-kit-with-qdk-chem"></a>での Quantum 開発キットの使用 `qdk-chem`

をインストールするには、 `qdk-chem` コマンドラインで .NET Core SDK を使用します。

```dotnetcli
dotnet tool install --global Microsoft.Quantum.Chemistry.Tools
```

をインストールしたら `qdk-chem` 、オプションを使用して、 `--help` ツールによって提供される機能に関する詳細情報を取得でき `qdk-chem` ます。

Broombridge との間で変換を行うには、次のコマンドを使用し `qdk-chem convert` ます。

```
qdk-chem convert --from fcidump --to broombridge data.fcidump --out data.yml
```

`qdk-chem convert`また、このコマンドは標準入力からデータを受け入れ、標準出力に書き込むことができます。これは、スクリプトや、従来の形式にエクスポートするツールとの統合に特に役立ちます。
たとえば Bash の場合は次のようになります。

```bash
cat data.fcidump | qdk-convert --from fcidump --to broombridge - > data.yml
```
