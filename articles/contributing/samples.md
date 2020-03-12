---
title: Microsoft QDK に貢献するサンプル
description: Microsoft Quantum Development Kit (QDK) にサンプルコードを投稿する方法について説明します。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.samples
ms.openlocfilehash: 3bd0de04a448c74eea6c3e8e3a15dcbb19f9d705
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2020
ms.locfileid: "79024153"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a>Quantum 開発キットに貢献するサンプル

[サンプルリポジトリ](https://github.com/Microsoft/Quantum)にコードを投稿することに関心がある場合は、quantum 開発コミュニティをより良い場所にしていただき、ありがとうございます。

## <a name="the-quantum-development-kit-samples-repository"></a>Quantum 開発キットのサンプルリポジトリ

できる限り多くの情報を提供するための貢献を準備するには、サンプルリポジトリがどのようにレイアウトされているかを簡単に確認してください。

```plaintext
microsoft/Quantum
📁 samples/
  📁 algorithms/
    📁 chsh-game/
      📝 CHSHGame.csproj
      📝 Game.qs
      📝 Host.cs
      📝 host.py
      📝 README.md
     ⋮
  📁 arithmetic/
  📁 characterization/
  📁 chemistry/
   ⋮
```

つまり、 [microsoft/Quantum リポジトリ](https://github.com/microsoft/Quantum)のサンプルは、サブジェクト領域によって `algorithms/`、`arithmetic/`、`characterization/`などの別のフォルダーに分類されます。
各サブジェクト領域のフォルダー内では、各サンプルは1つのフォルダーで構成され、ユーザーがそのサンプルを調査して使用するために必要なすべてのものを収集します。

## <a name="how-samples-are-structured"></a>サンプルの構造化方法

各フォルダーを構成するファイルについては、 [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game)のサンプルを参照してください。

| ファイル              | Description                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | .NET Core SDK を使用してサンプルをビルドするために使用される Q # プロジェクト |
| `Game.qs`         | このサンプルで使用される Q # の操作と関数                 |
| `Host.cs`         | C#サンプルを実行するために使用されるホストプログラム                     |
| `host.py`         | サンプルを実行するために使用される Python ホストプログラム                 |
| `README.md`       | サンプルの動作と使用方法に関するドキュメント    |

すべてのサンプルが完全に同じファイルセットを持つわけではありません (たとえばC#、一部のサンプルが、Python ホストを持たない場合や、補助データファイルを使用する必要があるサンプルもあります)。

## <a name="anatomy-of-a-helpful-readme-file"></a>役に立つ README ファイルの構造

ただし、特に重要なファイルとして、`README.md` ファイルがあります。これは、ユーザーがサンプルを使って作業を開始するために必要なファイルです。

各 `README.md` は、docs.microsoft.com/samples の投稿を見つけるのに役立ついくつかのメタデータから始める必要があります。

> [!div class="nextstepaction"]
> [Chsh ゲームのサンプルのレンダリング方法を確認する](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

このメタデータは、サンプルで使用されている言語 (通常は `qsharp`、`csharp`、および `python`) と、サンプルでカバーされている製品 (通常は `qdk`) を示す[Yaml ヘッダー](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header)として提供されます。

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> サンプルを docs.microsoft.com/samples に表示するには、ヘッダーの `page_type: sample` キーが必要です。
> 同様に、`product` と `language` キーは、ユーザーがサンプルを検索して実行できるようにするうえで重要です。

その後、新しいサンプルについて説明する短い概要を提供すると便利です。

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

また、サンプルのユーザーは、実行する必要があることを把握することもできます (たとえば、ユーザーが Quantum 開発キット自体を必要とするか、node.js などの追加ソフトウェアが必要なのか)。

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

そのすべてを使用して、サンプルを実行する方法をユーザーに伝えることができます。

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

最後に、サンプル内の各ファイルについて、さらに詳細な情報を入手できる場所をユーザーに通知すると便利です。

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> ここでは絶対 Url を使用してください。サンプルは docs.microsoft.com/samples でレンダリングされるときに別の URL に表示されるためです。
