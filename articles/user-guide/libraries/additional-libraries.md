---
title: 追加の Q# ライブラリの使用
description: Quantum アプリケーションにライブラリを追加する方法について説明 Q# します。
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
no-loc:
- Q#
- $$v
ms.openlocfilehash: 39bf7dc52f4670a6e4536efc437d001c96f9584a
ms.sourcegitcommit: 11bd357baeb6ab53a402882979e75964d0869b57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2020
ms.locfileid: "88992141"
---
# <a name="using-additional-no-locq-libraries"></a>追加の Q# ライブラリの使用

Quantum Development Kit は、プロジェクトに追加できる _NuGet パッケージ_ によって、ドメイン固有の追加機能を提供し Q# ます。

| Q# ライブラリ  | NuGet パッケージ | メモ |
|---------|---------|--------|
| [Q# 標準ライブラリ](xref:microsoft.quantum.libraries.standard.intro) | [**Microsoft. Quantum. Standard**](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | 既定で含まれる |
| [量子化学ライブラリ](xref:microsoft.quantum.chemistry.concepts.intro) | [**Microsoft.Quantum.Chemistry**](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [量子数値ライブラリ](xref:microsoft.quantum.numerics.intro) | [**Microsoft. Quantum. 数値**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [Quantum Machine Learning Library](xref:microsoft.quantum.libraries.machine-learning.intro) | [**Microsoft.Quantum.MachineLearning**](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

任意の環境およびホスト言語で使用するために Quantum 開発キットをインストールすると、追加のインストールなしで個別のプロジェクトに簡単にライブラリを追加でき Q# ます。

> [!NOTE]
> ライブラリによって Q# は、プログラムと共に動作する追加のツール Q# や、ホストアプリケーションと統合されるツールを使用することができます。
> たとえば、[化学ライブラリのインストール手順](xref:microsoft.quantum.chemistry.concepts.installation)では、NWChem 計算化学プラットフォームと共に[ **Microsoft の quantum**パッケージ](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry)を使用する方法と、 `qdk-chem` quantum の化学データを操作するためのコマンドラインツールをインストールする方法について説明します。

## <a name="no-locq-applications-or-net-interopability"></a>[Q# アプリケーションまたは .NET interopability](#tab/tabid-csproj)

**コマンドプロンプトまたは Visual Studio Code:** コマンドプロンプトを単独で、または Visual Studio Code 内で使用すると、コマンドを使用して `dotnet` NuGet パッケージ参照をプロジェクトに追加できます。
たとえば、 [**Microsoft の Quantum**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) パッケージを追加するには、次のコマンドを実行します。

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

**Visual Studio:** Visual Studio 2019 以降を使用している場合は、 Q# NuGet パッケージマネージャーを使用してパッケージを追加できます。
パッケージを読み込むには: 
1. Visual Studio でプロジェクトを開いた状態で、[**プロジェクト**] メニューの [ **NuGet パッケージの管理...** ] を選択します。

2. [ **参照**] をクリックし、[ **プレリリースを含める** ] を選択して、パッケージ名として「Microsoft. Quantum. 数値」を検索します。 これにより、ダウンロード可能なパッケージが一覧表示されます。

3. [ **..** .] をポイントし、バージョン番号の右側にある下向きの矢印をクリックして、数値パッケージをインストールします。

詳細については、「 [パッケージマネージャー UI ガイド](https://docs.microsoft.com/nuget/tools/package-manager-ui)」を参照してください。

または、パッケージマネージャーコンソールを使用して、コマンドラインインターフェイスを使用して数値ライブラリをプロジェクトに追加することもできます。

![コマンドプロンプトからのパッケージマネージャーコンソールの使用](~/media/vs2017-nuget-console-menu.png)

パッケージマネージャーコンソールで、次のように実行します。

```
Install-Package Microsoft.Quantum.Numerics
```

詳細については、「 [パッケージマネージャーコンソールガイド](https://docs.microsoft.com/nuget/tools/package-manager-console)」を参照してください。

## <a name="ino-locq-notebooks"></a>[I Q# notebook](#tab/tabid-notebook)

Q# [ `%package` マジックコマンド](xref:microsoft.quantum.iqsharp.magic-ref.package)を使用して、追加のパッケージを I Notebook で使用できるようにすることができます。
たとえば、I notebook で使用するために [**Microsoft の Quantum**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) パッケージを追加するには、 Q# notebook セルで次のコマンドを実行します。

```
%package Microsoft.Quantum.Numerics
```

このコマンドに従うと、notebook 内の任意のセルでパッケージを使用できるようになります。
現在のワークスペースのコードからパッケージを使用できるようにするには Q# 、パッケージを追加した後でワークスペースを再読み込みします。

```
%workspace reload
```

## <a name="python-interoperability"></a>[Python の相互運用性](#tab/tabid-python)


メソッドを使用して、Python ホストプログラムで追加のパッケージを使用できるようにすることができ [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages) ます。
たとえば、I Notebook で使用するために [**Microsoft の Quantum**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) パッケージを追加するには、 Q# 次の Python コードを実行します。

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

このコマンドに従うと、 Q# を使用してコンパイルされたすべてのコードでパッケージが使用できるようになり `qsharp.compile` ます。
現在のワークスペースのコードからパッケージを使用できるようにするには Q# 、パッケージを追加した後でワークスペースを再読み込みします。

```python
qsharp.reload()
```

***
