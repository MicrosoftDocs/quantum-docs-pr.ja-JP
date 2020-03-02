---
title: Q# でグローバーの検索アルゴリズムを実行する - Quantum 開発キット
description: 正規の量子アルゴリズムの 1 つであるグローバーのアルゴリズムを示す Q# プロジェクトを構築します。
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: 0e64fcd56929fa33397c45bf1b2e99bf687eca6f
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906952"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a>クイック スタート:Q# でグローバーの検索アルゴリズムを実装する

このクイック スタートでは、グローバーの検索を構築して実行子、非構造化データの検索速度を上げる方法について学習できます。  グローバーの検索は、最も人気がある量子コンピューティング アルゴリズムの 1 つであり、この比較的小規模な Q# 実装で、量子ソリューションをプログラミングすることの利点のいくつかと、量子アルゴリズムを表わす Q# 量子プログラミング言語の概要が理解できます。  ガイドの終わりには、シミュレーションの出力があります。この中で、旧式のコンピューターではリスト全体を検索するためにかかったであろう時間に比べ、ほんのわずかな時間で注文リストから特定の文字列を検索することに成功しています。

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

1. 新しいプロジェクトで次のコードを `Operations.qs` ファイルに追加します。

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-40":::

1. 検索するリストを定義するために、新しいファイル `Reflections.qs` を作成し、次のコードに貼り付けます。

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    `ReflectAboutMarked` 操作では、検索対象としてマークが付けられた入力を定義します。これは、0 と 1 の交互の文字列です。 このサンプルにより、マークされた入力はハードコードされます。サンプルは他の入力を検索するために拡張したり、任意の入力用に一般化したりできます。

1. 次に、新しい Q# プログラムを実行して、`ReflectAboutMarked` によってマークされた項目を検索します。

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Visual Studio Code またはコマンド ラインを使用した Python](#tab/tabid-python)

    Python から新しい Q# プログラムを実行するには、次のコードを `host.py` として保存します。

    :::code language="python" source="~/quantum/samples/algorithms/simple-grover/host.py" range="9-14":::

    次に、コマンド ラインから Python ホスト プログラムを実行できます。

    ```bash
    $ python host.py
    Preparing Q# environment...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    [0, 1, 0, 1, 0]
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[Visual Studio Code またはコマンド ラインを使用した C#](#tab/tabid-csharp)

    C# から新しい Q# プログラムを実行するには、次の C# コードを含めるように `Driver.cs` を変更します。

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    次に、コマンド ラインから C# ホスト プログラムを実行できます。

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```

    ### <a name="c-with-visual-studio-2019"></a>[Visual Studio 2019 を使用した C#](#tab/tabid-vs2019)

    Visual Studio で C# から新しい Q# プログラムを実行するには、次の C# コードを含めるように `Driver.cs` を変更します。

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    F5 キーを押すと、プログラムは実行を開始し、新しいポップアップ ウィンドウに次の結果が表示されます。 

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```
    ***

    `ReflectAboutMarked` 操作は 4 回だけ呼び出され、Q# プログラムにより $2^{5} = 32$ の入力で "01010" の入力を見つけることができました。

## <a name="next-steps"></a>次のステップ

クイックスタートをお読みいただきありがとうございます。Q# を使用して独自の量子アプリケーションを記述する方法の詳細について、次のリソースもご覧ください。

- [QDK 入門ガイドに戻る](xref:microsoft.quantum.welcome)
- より一般的なグローバーの検索アルゴリズムの[サンプル](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)を試す
- [グローバーの検索と Quantum Katas について学習する](xref:microsoft.quantum.overview.katas)
- グローバーの検索アルゴリズムの背後にある量子コンピューティング手法である[振幅増幅](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification)について読む
- [量子コンピューティングの概念](xref:microsoft.quantum.concepts.intro)
- [Quantum 開発キット サンプル](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
