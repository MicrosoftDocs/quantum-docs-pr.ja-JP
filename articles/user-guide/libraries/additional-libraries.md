---
title: その他の Q# ライブラリを使用する
description: '他の Q # ライブラリを quantum アプリケーションに追加する方法について説明します。'
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
ms.openlocfilehash: b82113b925870d07c8a28aecd50176e009826062
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "86872636"
---
# <a name="using-additional-q-libraries"></a>追加の Q # ライブラリの使用

Quantum Development Kit は、Q # プロジェクトに追加できる_NuGet パッケージ_を使用して、ドメイン固有の追加機能を提供します。

| Q # ライブラリ  | NuGet パッケージ | Notes |
|---------|---------|--------|
| [Q # 標準ライブラリ](xref:microsoft.quantum.libraries.standard.intro) | [**Microsoft. Quantum. Standard**](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | 既定で含まれる |
| [量子化学ライブラリ](xref:microsoft.quantum.chemistry.concepts.intro) | [**Microsoft.Quantum.Chemistry**](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [量子数値ライブラリ](xref:microsoft.quantum.numerics.intro) | [**Microsoft. Quantum. 数値**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [Quantum Machine Learning Library](xref:microsoft.quantum.libraries.machine-learning.intro) | [**Microsoft.Quantum.MachineLearning**](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

任意の環境およびホスト言語で使用するために Quantum 開発キットをインストールすると、追加のインストールを行わなくても、個別の Q # プロジェクトに簡単にライブラリを追加できます。

> [!NOTE]
> 一部の Q # ライブラリは、Q # プログラムと並行して動作する追加のツールや、ホストアプリケーションと統合されているツールで適切に動作する場合があります。
> たとえば、[化学ライブラリのインストール手順](xref:microsoft.quantum.chemistry.concepts.installation)では、NWChem 計算化学プラットフォームと共に[ **Microsoft の quantum**パッケージ](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry)を使用する方法と、 `qdk-chem` quantum の化学データを操作するためのコマンドラインツールをインストールする方法について説明します。

## <a name="q-command-line-applications-or-net-interopability"></a>[Q # コマンドラインアプリケーションまたは .NET interopability](#tab/tabid-csproj)

**コマンドラインまたは Visual Studio Code:** コマンドラインを単独で使用するか Visual Studio Code 内から使用すると、コマンドを使用して `dotnet` NuGet パッケージ参照をプロジェクトに追加できます。
たとえば、 [**Microsoft の Quantum**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics)パッケージを追加するには、次のコマンドを実行します。

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

**Visual Studio:** Visual Studio 2019 以降を使用している場合は、NuGet パッケージマネージャーを使用して追加の Q # パッケージを追加できます。
パッケージを読み込むには: 
1. Visual Studio でプロジェクトを開いた状態で、[**プロジェクト**] メニューの [ **NuGet パッケージの管理...** ] を選択します。

2. [**参照**] をクリックし、[**プレリリースを含める**] を選択して、パッケージ名として「Microsoft. Quantum. 数値」を検索します。 これにより、ダウンロード可能なパッケージが一覧表示されます。

3. [ **..** .] をポイントし、バージョン番号の右側にある下向きの矢印をクリックして、数値パッケージをインストールします。

詳細については、「[パッケージマネージャー UI ガイド](https://docs.microsoft.com/nuget/tools/package-manager-ui)」を参照してください。

または、パッケージマネージャーコンソールを使用して、コマンドラインインターフェイスを使用して数値ライブラリをプロジェクトに追加することもできます。

![コマンドラインからのパッケージマネージャーコンソールの使用](~/media/vs2017-nuget-console-menu.png)

パッケージマネージャーコンソールで、次のように実行します。

```
Install-Package Microsoft.Quantum.Numerics
```

詳細については、「[パッケージマネージャーコンソールガイド](https://docs.microsoft.com/nuget/tools/package-manager-console)」を参照してください。

## <a name="iq-notebooks"></a>[IQ # Notebook](#tab/tabid-notebook)

[ `%package` マジックコマンド](xref:microsoft.quantum.iqsharp.magic-ref.package)を使用して、他のパッケージを IQ # Notebook で使用できるようにすることができます。
たとえば、IQ # Notebook で使用するために、 [**Microsoft の Quantum**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics)パッケージを追加するには、notebook セルで次のコマンドを実行します。

```
%package Microsoft.Quantum.Numerics
```

このコマンドに従うと、notebook 内の任意のセルでパッケージを使用できるようになります。
現在のワークスペースの Q # コードからパッケージを使用できるようにするには、パッケージを追加した後でワークスペースを再読み込みします。

```
%workspace reload
```

## <a name="python-interoperability"></a>[Python の相互運用性](#tab/tabid-python)


メソッドを使用して、Python ホストプログラムで追加のパッケージを使用できるようにすることができ [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) ます。
たとえば、IQ # Notebook で使用するために、 [**Microsoft の Quantum**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics)パッケージを追加するには、次の Python コードを実行します。

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

このコマンドに従うと、を使用してコンパイルされたすべての Q # コードでパッケージが使用できるようになり `qsharp.compile` ます。
現在のワークスペースの Q # コードからパッケージを使用できるようにするには、パッケージを追加した後でワークスペースを再読み込みします。

```python
qsharp.reload()
```

***
