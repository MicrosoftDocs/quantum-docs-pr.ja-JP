---
title: Quantum 開発キット (QDK) を更新する
description: Q# プロジェクトと Microsoft Quantum 開発キットを現在のバージョンに更新する方法を説明します。
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 457083ea4756d64375834e5a276c2d91031138fe
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885146"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Microsoft Quantum 開発キット (QDK) を更新する

Microsoft Quantum 開発キット (QDK) を、最新のバージョンに更新する方法を説明します。

この記事では、QDK が既にインストールされていることを前提としています。 初めてインストールしようとしている場合は、[インストール ガイド](xref:microsoft.quantum.install)をご覧ください。

常に最新の QDK リリースを使用することをお勧めします。 この更新ガイドに従って、最新の QDK バージョンにアップグレードしましょう。 このプロセスは 2 つの部分から成っています。
1. 既存の Q# ファイルとプロジェクトを更新して、更新された構文にコードが合致するようにします。
2. 選択した開発環境に対して、QDK そのものを更新します。

## <a name="updating-q-projects"></a>Q# プロジェクトの更新 

Q# の演算をホストするために C# と Python のどちらを使用しているかに関わらず、次の手順に従って Q# プロジェクトを更新してください。

1. 最初に、最新バージョンの [.NET Core SDK 3.1](https://dotnet.microsoft.com/download) を使用していることを確認します。 コマンド プロンプトで、次のコマンドを実行します。

    ```dotnetcli
    dotnet --version
    ```

    出力が `3.1.100` 以上であることを確認します。 そうでない場合、[最新バージョン](https://dotnet.microsoft.com/download)をインストールして、もう一度確認します。 その後、自分の設定 (Visual Studio、Visual Studio Code、または直接コマンド ラインで) に応じて次の手順に従います。

### <a name="update-q-projects-in-visual-studio"></a>Visual Studio で Q# プロジェクトを更新する
 
1. [こちら](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019)の手順を参照して、Visual Studio 2019 の最新バージョンに更新します。
2. Visual Studio でソリューションを開きます。
3. メニューから、 **[ビルド]**  ->  **[ソリューションのクリーン]** を選択します。
4. それぞれの .csproj ファイルで、ターゲット フレームワークを `netcoreapp3.1` (ライブラリ プロジェクトの場合は `netstandard2.1`) に更新します。
    つまり、フォームの行を次のように編集します。

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    ターゲット フレームワークの指定の詳細については、[ここ](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)を参照してください。

5. それぞれの .csproj ファイルで、次の行で示されているように SDK を `Microsoft.Quantum.Sdk` に設定します。 バージョン番号は利用可能な最新のものにする必要がありますので、ご注意ください。[リリース ノート](https://docs.microsoft.com/quantum/relnotes/)を確認してください。

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. ソリューションのすべてのファイルを保存し、閉じます。

7. **[ツール]**  ->  **[コマンド ライン]**  ->  **[開発者コマンド プロンプト]** を選択します。 または、Visual Studio のパッケージ管理コンソールを使用することもできます。

8. ソリューションの各プロジェクトに対して、次のコマンドを実行してこのパッケージを**削除**します。

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   プロジェクトで他の Microsoft.Quantum または Microsoft.Azure.Quantum パッケージ (Microsoft.Quantum.Numerics) を使用している場合、これらに対して **add** コマンドを実行して使用しているバージョンを更新してください。

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. コマンド プロンプトを閉じて、 **[ビルド]**  ->  **[ソリューションのビルド]** を選択します ([ソリューションのリビルド] は選択 "*しない*" でください)。

これで、[Visual Studio の QDK 拡張機能の更新](#update-visual-studio-qdk-extension)に進むことができます。


### <a name="update-q-projects-in-visual-studio-code"></a>Visual Studio Code で Q# プロジェクトを更新する

1. Visual Studio Code で、更新するプロジェクトが含まれるフォルダーを開きます。
2. **[ターミナル]**  ->  **[新しいターミナル]** を選択します。
3. コマンド ラインを使用する更新の手順に従います (すぐ下にあります)。

### <a name="update-q-projects-using-the-command-line"></a>コマンド ラインを使用して Q# プロジェクトを更新する

1. メイン プロジェクト ファイルが含まれているフォルダーに移動します。

2. 次のコマンドを実行します。

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. QDK の現在のバージョンを確認します。 そのためには、[リリース ノート](https://docs.microsoft.com/quantum/relnotes/)を確認します。 バージョンの形式は、`0.11.2006.207` のようになっています。

4. それぞれの `.csproj` ファイルで、次のステップを繰り返します。

    - ターゲット フレームワークを `netcoreapp3.1` (ライブラリ プロジェクトの場合は `netstandard2.1`) に更新します。 つまり、フォームの行を次のように編集します。

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        ターゲット フレームワークの指定の詳細については、[こちら](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)を参照してください。

    - プロジェクト定義で、SDK への参照を置き換えます。 バージョン番号が、**手順 3** で確認した値に対応していることを確認します。

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - もしある場合は、パッケージ `Microsoft.Quantum.Development.Kit` への参照を削除します。これは、次のエントリで指定されます。

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - すべての Microsoft Quantum パッケージのバージョンを、QDK の最新のリリース バージョン (**手順 3** で確認済み) に更新します。 これらのパッケージの名称は、次のようなパターンになっています。

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        パッケージへの参照は、次のような形式になっています。

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - 更新したファイルを保存します。

    - 次を実行して、プロジェクトの依存関係を復元します。

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. メイン プロジェクトが含まれるフォルダーに戻り、次を実行します。

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

Q# プロジェクトが更新されたので、次の手順に従って QDK そのものを更新します。

## <a name="updating-the-qdk"></a>QDK の更新

QDK を更新するプロセスは、開発の言語と環境に応じて異なります。
自分の開発環境を次から選択します。

* [Python: `qsharp` パッケージを更新する](#update-the-qsharp-python-package)
* [Jupyter Notebook: IQ# カーネルを更新する](#update-the-iq-jupyter-kernel)
* [Visual Studio: QDK 拡張機能を更新する](#update-visual-studio-qdk-extension)
* [VS Code: QDK 拡張機能を更新する](#update-vs-code-qdk-extension)
* [コマンド ラインと C#: プロジェクト テンプレートを更新する](#c-using-the-dotnet-command-line-tool)


### <a name="update-the-qsharp-python-package"></a>`qsharp` Python パッケージを更新する

更新手順は、最初のインストールに conda を使用したか、.NET CLI と pip を使用したかによって異なります。

#### <a name="update-using-conda-recommended"></a>[conda を使用して更新する (推奨)](#tab/tabid-conda)

1. `qsharp` パッケージをインストールした conda 環境をアクティブ化してから、次のコマンドを実行して更新します。

    ```
    conda update -c quantum-engineering qsharp
    ```

1. `.qs` ファイルの場所から次のコマンドを実行します。

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[.NET CLI と pip を使用した更新 (上級者向け)](#tab/tabid-dotnetcli)

1. `iqsharp` カーネルを更新します 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. `iqsharp` のバージョンを確認します

    ```dotnetcli
    dotnet iqsharp --version
    ```

    次の出力が表示されます。

    ```
    iqsharp: 0.12.20070124
    Jupyter Core: 1.4.0.0
    ```

    `iqsharp` のバージョンが高い場合も問題ありません。 [最新のリリース](xref:microsoft.quantum.relnotes)と一致している必要があります。

1. `qsharp` パッケージを更新します。

    ```
    pip install qsharp --upgrade
    ```

1. `qsharp` のバージョンを確認します

    ```
    pip show qsharp
    ```

    次の出力が表示されます。

    ```
    Name: qsharp
    Version: 0.12.20070124
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. `.qs` ファイルの場所から次のコマンドを実行します。

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

***

これで、更新された `qsharp` Python パッケージを使用して既存の量子プログラムを実行できるようになりました。

### <a name="update-the-iq-jupyter-kernel"></a>IQ# Jupyter カーネルを更新する

更新手順は、最初のインストールに conda を使用したか、.NET CLI と pip を使用したかによって異なります。

#### <a name="update-using-conda-recommended"></a>[conda を使用して更新する (推奨)](#tab/tabid-conda)

1. `qsharp` パッケージをインストールした conda 環境をアクティブ化してから、次のコマンドを実行して更新します。

    ```
    conda update -c quantum-engineering qsharp
    ```

1. 既存の Q# 用の Jupyter Notebook それぞれのセルから、次のコマンドを実行します。

    ```
    %workspace reload
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[.NET CLI と pip を使用した更新 (上級者向け)](#tab/tabid-dotnetcli)

1. `Microsoft.Quantum.IQSharp` パッケージを更新します。

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. `iqsharp` のバージョンを確認します。

    ```dotnetcli
    dotnet iqsharp --version
    ```

    出力は次のようになります。

    ```
    iqsharp: 0.12.20070124
    Jupyter Core: 1.4.0.0
    ```

    `iqsharp` のバージョンが高い場合も問題ありません。 [最新のリリース](xref:microsoft.quantum.relnotes)と一致している必要があります。

1. 既存の Q# 用の Jupyter Notebook それぞれのセルから、次のコマンドを実行します。

    ```
    %workspace reload
    ```

***

更新された IQ# カーネルを使用して、既存の Q# 用の Jupyter Notebook を実行できるようになりました。

### <a name="update-visual-studio-qdk-extension"></a>Visual Studio の QDK 拡張機能を更新する

1. Q# Visual Studio 拡張機能を更新します

    - Visual Studio で、[Quantum Visual Studio 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)への更新を受け入れるように求められます
    - 更新を受け入れます

    > [!NOTE]
    > プロジェクト テンプレートは、拡張機能とともに更新されます。 更新されたテンプレートは、新たに作成されたプロジェクトにのみ適用されます。 拡張機能が更新される際に、既存のプロジェクトのコードは更新されません。

### <a name="update-vs-code-qdk-extension"></a>VS Code の QDK 拡張機能を更新する

1. Quantum VS Code 拡張機能を更新します

    - VS Code を再起動します
    - **[拡張機能]** タブに移動します
    - **[Microsoft Quantum Development Kit for Visual Studio Code]\(Visual Studio Code 用 Microsoft Quantum 開発キット\)** を選択します
    - 拡張機能を再度読み込みます

2. Quantum プロジェクト テンプレートを更新します

   - **[表示]**  ->  **[コマンド パレット]** の順に選択します。
   - **[Q#:Install project templates]\(Q#: プロジェクト テンプレートのインストール\)** を選択します。
   - 数秒後に、[project templates installed successfully]\(プロジェクト テンプレートが正常にインストールされました\) というポップアップが表示されます。

### <a name="c-using-the-dotnet-command-line-tool"></a>C# で `dotnet` コマンド ライン ツールを使用する

1. .NET 用 Quantum プロジェクト テンプレートを更新します

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
