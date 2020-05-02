---
title: 'ドライバーとホスト言語を使用せずに Q # プログラムを実行する'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e83acaf10af952da06abf4737ad2ec91f1cf1b8e
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "82706803"
---
# <a name="q-command-line-applications"></a>Q # コマンドラインアプリケーション

Q # プログラムは、C#、F #、Python などのホスト言語でドライバーを使用しなくても、独自に実行できます。

## <a name="pre-requisites"></a>前提条件

- [.NET Core SDK 3.1 以降](https://www.microsoft.com/net/download)

## <a name="installation"></a>インストール

任意の IDE で Q # コマンドラインアプリケーションをビルドできますが、Q # アプリケーションには Visual Studio Code (VS Code) または Visual Studio IDE を使用することを強くお勧めします。 VS Code または Visual Studio と QDK Visual Studio Code 拡張機能を使用すると、豊富な機能を利用できます。

- [VS Code](https://code.visualstudio.com/download)のインストール (Windows、Linux、および Mac)
- VS Code または[の Qdk 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)をインストールします。
- .NET Core クロス プラットフォーム開発ワークロードが有効な [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3
- [Visual Studio 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)をダウンロードしてインストールする


## <a name="develop-with-q-using-vs-code"></a>VS Code を使用した Q # での開発

量子プロジェクト テンプレートをインストールします。

- **ビュー** -> **コマンドパレット**にアクセス
- [ **Q #: プロジェクトテンプレートのインストール**] を選択します。

これで、Quantum Development Kit がインストールされ、使用しているアプリケーションとライブラリで使用できるようになりました。
- 新しいプロジェクトを作成します。
  - **ビュー** -> **コマンドパレット**にアクセス
  - [ **Q #: 新しいプロジェクトの作成**] を選択します。
  - **スタンドアロンコンソールアプリケーション**の選択
  - アプリケーションの作成先となるファイル システム上の場所に移動します。
  - プロジェクトが作成されたら、**[Open new project...]\(新しいプロジェクトを開く...\)** ボタンをクリックします。
        
- プロジェクトの確認
  - "Created" という名前`Program.qs`のファイルが表示されます。このファイルは、コンソールにメッセージを出力する簡単な操作を定義する Q # プログラムです。

- アプリケーションを実行します。
  - **ターミナル** -> の**新しいターミナル**にアクセス
  - 「`dotnet run`」と入力します
  - 出力ウィンドウに `Hello quantum world!` というテキストが表示されます。


> [!NOTE]
> * 複数のルート フォルダーを持つワークスペースは、Visual Studio Code の拡張機能では現在サポートされていません。 1 つの VS Code ワークスペース内に複数のプロジェクトがある場合は、すべてのプロジェクトが同じルート フォルダー内に含まれている必要があります。

## <a name="develop-with-q-using-visual-studio"></a>Visual Studio を使用した Q # での開発

`Hello World` アプリケーションを作成してインストールを確認する

- 新しい Q# アプリケーションを作成する
  - **ファイル** -> の**新しい** -> **プロジェクト**にアクセス
  - 検索ボックスに、「`Q#`」と入力します
  - **[Q# Application]\(Q# アプリケーション\)** を選択します
  - **次**を選択
  - アプリケーションの名前と格納する場所を選択します
  - **[作成]**

- プロジェクトの確認
  - という名前`Program.qs`のファイルが作成されていることがわかります。これは、コンソールにメッセージを出力する簡単な操作を定義する Q # プログラムです。

- アプリケーションの実行
  - デバッグ**Debug** -> を**行わないデバッグ開始**の選択
  - テキスト `Hello quantum world!` がコンソール ウィンドウに出力されます。

> [!NOTE]
> * 1 つの Visual Studio ソリューションに複数のプロジェクトがある場合は、ソリューションに含まれるすべてのプロジェクトが、ソリューションと同じフォルダーまたはそのサブフォルダーのいずれかに存在する必要があります。  


## <a name="whats-next"></a>次の内容

これで、使用している環境に Quantum Development Kit がインストールされたので、[最初の量子プログラム](xref:microsoft.quantum.write-program)を作成して実行することができます。
