---
title: 'Q # + を使用した開発C#'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 7803846279f230f5fc0ee8424bd39be735a650ca
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036289"
---
# <a name="develop-with-q--c"></a>Q # + を使用した開発C#

Q # 操作を呼び出すホストC#プログラムを開発するには、qdk をインストールします。

Q # は、.NET 言語 (特C#に) を使用して適切に動作するように構築されています。 この組み合わせは、さまざまな開発環境で使用できます。

- [Visual Studio をC#使用した Q # + (Windows)](#VS)
- [Visual Studio Code を使用C#した Q # + (Windows、Linux、Mac)](#VSC)
- [Q # + C# `dotnet` コマンドラインツールの使用](#command)

## Visual Studio を使用しC#た Q # + を使用した開発 <a name="VS"></a>

Visual Studio には、Q # プログラムを開発するための豊富な環境が用意されています。 Q # Visual Studio 拡張機能には、Q # のファイルとプロジェクトのテンプレートに加え、構文の強調表示、コード補完、IntelliSense のサポートが含まれています。


1. 前提条件

    - .NET Core クロス プラットフォーム開発ワークロードが有効な [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3

1. Q# Visual Studio 拡張機能のインストール

    - [Visual Studio 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)をダウンロードしてインストールする

1. `Hello World` アプリケーションを作成してインストールを確認する

    - 新しい Q# アプリケーションを作成する

        - **[ファイル]**  ->  **[新規]**  ->  **[プロジェクト]** の順に移動します。
        - 検索ボックスに、「`Q#`」と入力します
        - **[Q# Application]\(Q# アプリケーション\)** を選択します
        - **[次へ]** を選択します
        - アプリケーションの名前と格納する場所を選択します
        - **[作成]**

    - プロジェクトの確認

        2 つのファイルが作成されていることがわかります。`Driver.cs` は C# ホスト アプリケーションで、`Operation.qs` は、コンソールにメッセージを出力する簡単な操作を定義する Q# プログラムです。

    - アプリケーションの実行

        - **[デバッグ]**  ->  **[デバッグなしで開始]** の順に選択します。
        - テキスト `Hello quantum world!` がコンソール ウィンドウに出力されます。

> [!NOTE]
> * 1 つの Visual Studio ソリューションに複数のプロジェクトがある場合は、ソリューションに含まれるすべてのプロジェクトが、ソリューションと同じフォルダーまたはそのサブフォルダーのいずれかに存在する必要があります。  

## Visual Studio Code を使用したC# Q # + を使用した開発 <a name="VSC"></a>

Visual Studio Code (VS Code) は、Windows、Linux、および Mac で Q # プログラムを開発するための豊富な環境を提供します。  Q # の VS Code 拡張機能には、Q # 構文の強調表示、コード補完、Q # コードスニペットのサポートが含まれています。

1. 前提条件

   - [VS Code](https://code.visualstudio.com/download)
   - [.NET Core SDK 3.1 以降](https://www.microsoft.com/net/download)

1. Quantum VS Code 拡張機能のインストール

    - [VS Code 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)をインストールする

1. 量子プロジェクト テンプレートをインストールします。

   - **[表示]**  ->  **[コマンド パレット]** の順に選択します。
   - **[Q #: プロジェクトテンプレートのインストール]** を選択します。

    これで、Quantum Development Kit がインストールされ、使用しているアプリケーションとライブラリで使用できるようになりました。

1. `Hello World` アプリケーションを作成してインストールを確認する

    - 新しいプロジェクトを作成します。

        - **[表示]**  ->  **[コマンド パレット]** の順に選択します。
        - **[Q #: 新しいプロジェクトの作成]** を選択します。
        - **スタンドアロンコンソールアプリケーション**の選択
        - アプリケーションの作成先となるファイル システム上の場所に移動します。
        - プロジェクトが作成されたら、 **[Open new project...]\(新しいプロジェクトを開く...\)** ボタンをクリックします。

    - VS Code のC#拡張機能をまだインストールしていない場合は、ポップアップが表示されます。 拡張機能をインストールします。 

    - アプリケーションを実行します。

        - **ターミナル** -> **新しいターミナル**にアクセスする
        - 「`dotnet run`」と入力します
        - 出力ウィンドウに `Hello quantum world!` というテキストが表示されます。


> [!NOTE]
> * 複数のルート フォルダーを持つワークスペースは、Visual Studio Code の拡張機能では現在サポートされていません。 1 つの VS Code ワークスペース内に複数のプロジェクトがある場合は、すべてのプロジェクトが同じルート フォルダー内に含まれている必要があります。

## `dotnet` コマンドラインツールをC#使用した Q # + を使用した開発<a name="command"></a>

もちろん、単に .NET Core SDK と QDK プロジェクト テンプレートをインストールして、コマンド ラインから Q# プログラムを構築して実行することもできます。 

1. 前提条件

    - [.NET Core SDK 3.1 以降](https://www.microsoft.com/net/download)

1. .NET 用量子プロジェクト テンプレートをインストールします。

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    これで、Quantum Development Kit がインストールされ、使用しているアプリケーションとライブラリで使用できるようになりました。

1. `Hello World` アプリケーションを作成してインストールを確認する

    - 新しいアプリケーションを作成する

       ```dotnetcli
       dotnet new console -lang "Q#" -o runSayHello
       ```

    - 新しいアプリケーション ディレクトリに移動します。

       ```bash
       cd runSayHello
       ```

    アプリケーションのプロジェクト ファイルと共に、Q# ファイル (`Operation.qs`) と C# ホスト ファイル (`Driver.cs`) の 2 つのファイルが作成されていることがわかります。

    - アプリケーションの実行

        ```dotnetcli
        dotnet run
        ```

        `Hello quantum world!` という出力が表示されます。

    
## <a name="whats-next"></a>次の操作

これで、使用している環境に Quantum Development Kit がインストールされたので、[最初の量子プログラム](xref:microsoft.quantum.write-program)を作成して実行することができます。
