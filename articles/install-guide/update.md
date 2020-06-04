---
title: Quantum Development Kit (QDK) を更新する
description: 'Q # プロジェクトと Microsoft Quantum Development Kit を現在のバージョンに更新する方法について説明します。'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 3245f587493ce12cfec15c8f932fd092d85f688e
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327572"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Microsoft Quantum Development Kit の更新 (QDK)

Microsoft Quantum Development Kit (QDK) を最新バージョンに更新する方法について説明します。

この記事では、QDK が既にインストールされていることを前提としています。 を初めてインストールする場合は、[インストールガイド](xref:microsoft.quantum.install)を参照してください。

最新の QDK リリースを常に最新の状態に保つことをお勧めします。 最新の QDK バージョンにアップグレードするには、この更新ガイドに従ってください。 このプロセスは、次の2つの部分で構成されます。
1. 既存の Q # ファイルとプロジェクトを更新して、コードを更新された構文でアラインします。
2. 選択した開発環境の QDK 自体を更新しています。

## <a name="updating-q-projects"></a>Q # プロジェクトを更新しています 

Q # 操作をホストするために C# と Python のどちらを使用しているかにかかわらず、次の手順に従って Q # プロジェクトを更新します。

1. まず、 [.NET Core SDK 3.1](https://dotnet.microsoft.com/download)の最新バージョンがあることを確認します。 コマンドプロンプトで次のコマンドを実行します。

    ```dotnetcli
    dotnet --version
    ```

    出力が以上であることを確認し `3.1.100` ます。 インストールされていない場合は、[最新バージョン](https://dotnet.microsoft.com/download)をインストールして、もう一度確認します。 次に、セットアップに応じて、次の手順に従います (Visual Studio、Visual Studio Code、またはコマンドラインから直接)。

### <a name="update-q-projects-in-visual-studio"></a>Visual Studio での Q # プロジェクトの更新
 
1. 最新バージョンの Visual Studio 2019 に更新する方法について[は、こちら](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019)を参照してください。
2. Visual Studio でソリューションを開きます。
3. メニューから、[ソリューションのクリーン**ビルド**] を選択し  ->  **Clean Solution**ます。
4. 各 .csproj ファイルで、ターゲットフレームワークを `netcoreapp3.1` (または `netstandard2.1` ライブラリプロジェクトの場合は) に更新します。
    つまり、次のような形式の行を編集します。

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    ターゲットフレームワークの指定の詳細については、[こちら](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)を参照してください。

5. 各 .csproj ファイルで、 `Microsoft.Quantum.Sdk` 次の行に示されているように、SDK をに設定します。 バージョン番号は使用可能な最新のものである必要があり、[リリースノート](https://docs.microsoft.com/quantum/relnotes/)を確認することによって確認できます。

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. ソリューション内のすべてのファイルを保存して閉じます。

7. [**ツール**  ->  **] [コマンドライン**開発者コマンドプロンプト] を選択し  ->  **Developer Command Prompt**ます。 または、Visual Studio のパッケージ管理コンソールを使用することもできます。

8. ソリューション内のプロジェクトごとに、次のコマンドを実行してこのパッケージを**削除**します。

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   プロジェクト**で他**の Microsoft の quantum パッケージや microsoft.....................................................

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. コマンドプロンプトを閉じ、[**ビルド**  ->  **ビルドソリューション**] を*not*選択します ([ソリューションのリビルド] は選択しないでください)。

これで[、Visual Studio QDK 拡張機能を更新](#update-visual-studio-qdk-extension)することができます。


### <a name="update-q-projects-in-visual-studio-code"></a>Visual Studio Code で Q # プロジェクトを更新する

1. Visual Studio Code で、更新するプロジェクトが格納されているフォルダーを開きます。
2. [**ターミナル**  ->  の**新しいターミナル**] を選択します。
3. コマンドラインを使用して更新するための指示に従います (すぐ下)。

### <a name="update-q-projects-using-the-command-line"></a>コマンドラインを使用して Q # プロジェクトを更新する

1. メインプロジェクトファイルが格納されているフォルダーに移動します。

2. 次のコマンドを実行します。

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. QDK の現在のバージョンを確認します。 これを見つけるには、[リリースノート](https://docs.microsoft.com/quantum/relnotes/)を参照してください。 バージョンは、のような形式になり `0.11.2006.207` ます。

4. 各 `.csproj` ファイルで、次の手順を実行します。

    - ターゲットフレームワークをに更新 `netcoreapp3.1` `netstandard2.1` します (ライブラリプロジェクトの場合)。 つまり、次のような形式の行を編集します。

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        ターゲットフレームワークの指定の詳細については、[こちら](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)を参照してください。

    - プロジェクト定義の SDK への参照を置き換えます。 バージョン番号が、**手順 3**. で決定した値に対応していることを確認します。

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - パッケージへの参照を削除し `Microsoft.Quantum.Development.Kit` ます (存在する場合)。これは、次のエントリに指定されます。

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - すべての Microsoft クォンタムパッケージのバージョンを、QDK の最新リリースバージョン (**手順 3**で確認) に更新します。 これらのパッケージには、次のパターンの名前が付けられます。

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        パッケージへの参照の形式は次のとおりです。

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - 更新したファイルを保存します。

    - 次の手順を実行して、プロジェクトの依存関係を復元します。

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. メインプロジェクトが含まれているフォルダーに戻り、次のように実行します。

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

Q # プロジェクトを更新したので、次の手順に従って QDK 自体を更新します。

## <a name="updating-the-qdk"></a>QDK を更新しています

QDK を更新するプロセスは、開発言語と環境によって異なります。
以下の開発環境を選択してください。

* [Python: IQ # extension を更新する](#update-iq-for-python)
* [Jupyter Notebook: IQ # extension を更新する](#update-iq-for-jupyter-notebooks)
* [Visual Studio: QDK 拡張機能を更新する](#update-visual-studio-qdk-extension)
* [VS Code: QDK 拡張機能を更新する](#update-vs-code-qdk-extension)
* [コマンドラインと C#: プロジェクトテンプレートの更新](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a>Python 用の IQ # の更新

1. カーネルを更新する `iqsharp` 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. バージョンを確認する `iqsharp`

    ```dotnetcli
    dotnet iqsharp --version
    ```

    次の出力が表示されます。

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    `iqsharp`バージョンが高い場合は、[最新のリリース](xref:microsoft.quantum.relnotes)と一致している必要があります。

3. パッケージを更新する `qsharp`

    ```bash
    pip install qsharp --upgrade
    ```

4. バージョンを確認する `qsharp`

    ```bash
    pip show qsharp
    ```

    次の出力が表示されます。

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. ファイルの場所から次のコマンドを実行します。 `.qs`

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. 更新された QDK バージョンを使用して、既存の quantum プログラムを実行できるようになりました。

### <a name="update-iq-for-jupyter-notebooks"></a>Jupyter Notebook の IQ # を更新する

1. カーネルを更新する `iqsharp`

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. バージョンを確認する `iqsharp`

    ```dotnetcli
    dotnet iqsharp --version
    ```

    出力は次のようになります。

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    `iqsharp`バージョンが高い場合は、[最新のリリース](xref:microsoft.quantum.relnotes)と一致している必要があります。

3. Jupyter Notebook 内のセルから次のコマンドを実行します。

    ```
    %workspace reload
    ```

4. これで、既存の Jupyter notebook を開いて、更新された QDK で実行できるようになりました。

### <a name="update-visual-studio-qdk-extension"></a>Visual Studio QDK 拡張機能の更新

1. Q # Visual Studio 拡張機能を更新する

    - Visual Studio によって、 [Quantum Visual studio 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)の更新を受け入れるように求められます
    - 更新プログラムを受け入れる

    > [!NOTE]
    > プロジェクトテンプレートは、拡張機能を使用して更新されます。 更新されたテンプレートは、新しく作成されたプロジェクトにのみ適用されます。 拡張機能が更新されても、既存のプロジェクトのコードは更新されません。

### <a name="update-vs-code-qdk-extension"></a>QDK 拡張機能を更新 VS Code

1. クォンタム VS Code 拡張機能を更新する

    - 再起動 VS Code
    - [**拡張**] タブに移動します。
    - Visual Studio Code 拡張機能**の Microsoft Quantum Development Kit**を選択します
    - 拡張機能の再読み込み

2. クォンタムプロジェクトテンプレートを更新します。

   - **ビュー**  ->  **コマンドパレット**にアクセス
   - [ **Q #: プロジェクトテンプレートのインストール**] を選択します。
   - 数秒後に、"プロジェクトテンプレートが正常にインストールされました" というポップアップが表示されます。

### <a name="c-using-the-dotnet-command-line-tool"></a>C#、 `dotnet` コマンドラインツールの使用

1. .NET 用の Quantum プロジェクトテンプレートを更新する

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
