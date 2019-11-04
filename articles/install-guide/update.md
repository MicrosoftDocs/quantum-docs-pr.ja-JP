---
title: Microsoft Quantum Development Kit を更新する方法 (QDK) について説明します。
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ebf1f15d65a12c921cd3f04e4111d463d1060f8e
ms.sourcegitcommit: c93fea5980d1d46fbda1e7c7153831b9337134bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2019
ms.locfileid: "73463283"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Microsoft Quantum Development Kit の更新 (QDK)

Microsoft Quantum Development Kit (QDK) を最新バージョンに更新する方法について説明します。

この記事では、QDK が既にインストールされていることを前提としています。 を初めてインストールする場合は、[インストールガイド](xref:microsoft.quantum.install)を参照してください。


## <a name="updating-q-projects"></a>Q # プロジェクトを更新しています 

1. まず、 [.NET Core SDK 3.0](https://dotnet.microsoft.com/download)の最新バージョンをインストールし、コマンドプロンプトで次のコマンドを実行します。
```bash
dotnet --version
```
 出力が3.0.100 以上であることを確認してから、セットアップに応じて次の手順に従います。

### <a name="in-visual-studio"></a>Visual Studio で使用する
 
 1. 最新バージョンの Visual Studio 2019 に更新する方法について[は、こちら](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019)を参照してください。
 2. Visual Studio でソリューションを開く
 3. メニューから [ビルド > クリーンソリューション] を選択します。 
 4. 各 .csproj ファイルの[ターゲットフレームワーク](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework)を netcoreapp 3.0 (または、ライブラリプロジェクトの場合は netstandard 2.1) に更新します。
 5. ソリューション内のすべてのファイルを保存して閉じる
 6. ツール > コマンドライン > を選択し開発者コマンドプロンプト
 7. ソリューション内の各プロジェクトに対して、次のコマンドを実行します。
 ```bash
 dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
 ```
プロジェクトで他の Microsoft の Quantum パッケージが使用されている場合は、コマンドも実行します。 
 8. コマンドプロンプトを閉じ、[ビルド > ビルド] を選択します (リビルドは最初に失敗するため、[ソリューションのリビルド] を選択しない*でください)* 。

### <a name="in-visual-studio-code"></a>Visual Studio Code

1. Visual Studio Code で、更新するプロジェクトが格納されているフォルダーを開きます。
1. ターミナル > [新しいターミナル] を選択します。
1. コマンドラインを使用して更新するための手順に従います。

### <a name="using-the-command-line"></a>コマンドラインの使用

1. プロジェクトファイルが格納されているフォルダーに移動します。
2. 次のコマンドを実行します。
```bash
dotnet clean [project_name].csproj
```

3. 各 .csproj ファイルの[ターゲットフレームワーク](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)を netcoreapp 3.0 (または、ライブラリプロジェクトの場合は netstandard 2.1) に更新します。
4. 次のコマンドを実行します。
```bash
dotnet add package Microsoft.Quantum.Development.Kit
```
プロジェクトで他の Microsoft の Quantum パッケージが使用されている場合は、コマンドも実行します。

5. すべてのファイルを保存して閉じる
6. プロジェクトの依存関係ごとに1-4 を繰り返し、メインプロジェクトが含まれているフォルダーに戻り、を実行します。
```bash
dotnet build [project_name].csproj
```

## <a name="update-iq-for-python"></a>Python 用の IQ # の更新

1. `iqsharp` カーネルを更新する

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. `iqsharp` のバージョンを確認する

    ```bash
    dotnet iqsharp --version
    ```

    次の出力が表示されます。

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```

1. `qsharp` パッケージを更新する

    ```bash
    pip install qsharp --upgrade
    ```

1. `qsharp` のバージョンを確認する

    ```bash
    pip show qsharp
    ```

    次の出力が表示されます。

    ```bash
    Name: qsharp
    Version: 0.10.1911.307
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
1. `.qs` ファイルの場所から次のコマンドを実行します。
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

1. 更新された QDK バージョンを使用して、既存の quantum プログラムを実行できるようになりました。

## <a name="update-iq-for-jupyter-notebooks"></a>Jupyter notebook の IQ # を更新する

1. `iqsharp` カーネルを更新する

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. `iqsharp` のバージョンを確認する

    ```bash
    dotnet iqsharp --version
    ```

    次の出力が表示されます。

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```
1. Jupyter Notebook 内のセルから次のコマンドを実行します。
    ```
    %workspace reload
    ```

1. これで、既存の Jupyter notebook を開いて、更新された QDK で実行できるようになりました。

## <a name="update-visual-studio-qdk-extension"></a>Visual Studio QDK 拡張機能の更新

1. Q # Visual Studio 拡張機能を更新する

    - Visual Studio によって、 [Quantum Visual studio 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)の更新を受け入れるように求められます
    - 更新プログラムを受け入れる

    > [!NOTE]
    > プロジェクトテンプレートは、拡張機能を使用して更新されます。 更新されたテンプレートは、新しく作成されたプロジェクトにのみ適用されます。 拡張機能が更新されても、既存のプロジェクトのコードは更新されません。

## <a name="update-vs-code-qdk-extension"></a>QDK 拡張機能を更新 VS Code

1. クォンタム VS Code 拡張機能を更新する

    - 再起動 VS Code
    - **[拡張]** タブに移動します。
    - Visual Studio Code 拡張機能**の Microsoft Quantum Development Kit**を選択します
    - 拡張機能の再読み込み

1. クォンタムプロジェクトテンプレートを更新します。

   - **[表示]**  ->  **[コマンド パレット]** の順に選択します。
   - **[Q #: プロジェクトテンプレートのインストール]** を選択します。

## <a name="c-using-the-dotnet-command-line-tool"></a>C#、`dotnet` コマンドラインツールの使用

1. .NET 用の Quantum プロジェクトテンプレートを更新する

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a>次に、

お好みの環境で Quantum 開発キットを更新したので、引き続き quantum プログラムの開発と実行を行うことができます。 プログラムをまだ作成していない場合は、[最初のクォンタムプログラム](xref:microsoft.quantum.write-program)を開始することができます。
