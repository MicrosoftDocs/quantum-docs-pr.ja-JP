---
title: Q# でグローバーの検索アルゴリズムを実行する - Quantum 開発キット
description: 正規の量子アルゴリズムの 1 つであるグローバーのアルゴリズムを示す Q# プロジェクトを構築します。
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: 9562e1937a2cac49d682cc0524d8fb29e276d95c
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426806"
---
# <a name="tutorial-implement-grovers-search-algorithm-in-q"></a>チュートリアル:Q\# でグローバーの検索アルゴリズムを実装する

このチュートリアルでは、グローバーの検索を構築して実行し、非構造化データの検索速度を上げる方法について学習できます。  グローバーの検索は、最も人気がある量子コンピューティング アルゴリズムの 1 つであり、この比較的小規模な Q# 実装で、量子ソリューションをプログラミングすることの利点のいくつかと、量子アルゴリズムを表わす Q# 量子プログラミング言語の概要が理解できます。  このガイドの最後に、シミュレーションの出力があります。そこでは、従来のコンピューターでリスト全体を検索するのにかかる時間に比べてほんのわずかな時間で、順序付けられていないエントリのリストから特定の文字列の検索に成功することを確認できます。

グローバーのアルゴリズムでは、特定の項目の非構造化データのリストが検索されます。 たとえば、次のような質問に回答できます。一組のトランプから引いたこのカードは、ハートのエースですか? 特定の項目のラベル付けは、"_マークされた入力_" と呼ばれます。

グローバーの検索アルゴリズムを使用すると、量子コンピューターで、探しているリスト内の項目数よりも少ない手順でこの検索が確実に実行されます。これは、従来のアルゴリズムでは実行できません。 一組のトランプの場合、速度の向上はごくわずかですが、数百万または数十億の項目が含まれるリストでは、大きな差が出ます。

数行のコードを記述するだけで、グローバーの検索アルゴリズムを構築できます。

## <a name="prerequisites"></a>前提条件

- Microsoft [Quantum 開発キット][install]。

## <a name="what-does-grovers-search-algorithm-do"></a>グローバーの検索アルゴリズムで何ができるか

グローバーのアルゴリズムでは、リスト内の項目が探している項目かどうかを確認します。 これは、各係数または確率振幅を使ってリストのインデックスの量子重ね合わせを構築し、その特定のインデックスが探しているものである確率を表すことで行います。

アルゴリズムは主に 2 つの手順から成ります。手順では、検索対象のインデックスの係数を、その係数の確率振幅が検索対象になるまで段階的に増やします。

増分ブーストの数は、リスト内の項目数より少なくなります。 これが、グローバーの検索アルゴリズムの手順が従来のアルゴリズムの手順より少ない理由です。

![グローバーの検索アルゴリズムの機能図](~/media/grover.png)

## <a name="write-the-code"></a>コードを作成する

1. Quantum 開発キットを使用して、任意の開発環境に `Grover` という[新しい Q# プロジェクトを作成](xref:microsoft.quantum.howto.createproject)します。

1. 新しいプロジェクトで次のコードを `Program.qs` ファイルに追加します。

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. 検索するリストを定義するために、新しいファイル `Reflections.qs` を作成し、次のコードに貼り付けます。

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    `ReflectAboutMarked` 操作では、検索対象としてマークが付けられた入力を定義します。これは、0 と 1 の交互の文字列です。 このサンプルにより、マークされた入力はハードコードされます。サンプルは他の入力を検索するために拡張したり、任意の入力用に一般化したりできます。

1. 次に、新しい Q# プログラムを実行して、`ReflectAboutMarked` によってマークされた項目を検索します。

### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a>Visual Studio または Visual Studio Code を使用する Q# コマンド ライン アプリケーション

実行可能ファイルは、プロジェクトの構成とコマンドライン オプションに応じて、シミュレーターまたはリソース推定機能で `@EntryPoint()` 属性でマークされた操作または関数を実行します。

Visual Studio では、Ctrl キーを押しながら F5 キーを押すだけでスクリプトを実行します。

VS Code では、ターミナルで次のように入力して、`Program.qs` の初回のビルドを行います。

```Command line
dotnet build
```

以降の実行では、再度ビルドする必要はありません。 これを実行するには、次のコマンドを入力して、Enter キーを押します。

```Command line
dotnet run --no-build
```

ターミナルに次のメッセージが表示されます。

```
operations.qs:
This operation applies Grover's algorithm to search all possible inputs to an operation to find a particular marked state.
Usage:
operations.qs [options] [command]

--n-qubits <n-qubits> (REQUIRED)
-s, --simulator <simulator>         The name of the simulator to use.
--version                           Show version information
-?, -h, --help                      Show help and usage information
Commands:
```

これは、使用するキュービットの数を指定しなかったためです。そのため、実行可能ファイルで使用できるコマンドがターミナルによって示されます。 5 つのキュービットを使用する場合は、次のように入力する必要があります。

```Command line
dotnet run --n-qubits 5
```

Enter キーを押すと、次の出力が表示されます。

```
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
[Zero,One,Zero,One,Zero]
```

## <a name="next-steps"></a>次のステップ

チュートリアルをお読みいただきありがとうございます。Q# を使用して独自の量子アプリケーションを記述する方法の詳細について、次のリソースもご覧ください。

- [QDK 入門ガイドに戻る](xref:microsoft.quantum.welcome)
- より一般的なグローバーの検索アルゴリズムの[サンプル](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)を試す
- [グローバーの検索と Quantum Katas について学習する](xref:microsoft.quantum.overview.katas)
- グローバーの検索アルゴリズムの背後にある量子コンピューティング手法である[振幅増幅][amplitude-amplification]について読む
- [量子コンピューティングの概念](xref:microsoft.quantum.concepts.intro)
- [Quantum 開発キット サンプル](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification
