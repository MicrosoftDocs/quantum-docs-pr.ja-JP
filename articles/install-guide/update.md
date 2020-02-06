---
title: Microsoft Quantum Development Kit を更新する方法 (QDK) について説明します。
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: f19285ae0e008b3460d06430a236f098d716e268
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036314"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Microsoft Quantum Development Kit の更新 (QDK)

Microsoft Quantum Development Kit (QDK) を最新バージョンに更新する方法について説明します。

この記事では、QDK が既にインストールされていることを前提としています。 を初めてインストールする場合は、[インストールガイド](xref:microsoft.quantum.install)を参照してください。

最新の QDK リリースを常に最新の状態に保つことをお勧めします。 最新の QDK バージョンにアップグレードするには、この更新ガイドに従ってください。 このプロセスは、次の2つの部分で構成されます。
1. 既存の Q # ファイルとプロジェクトを更新して、コードを更新された構文に合わせる
2. 選択した開発環境の QDK 自体を更新しています 

## <a name="updating-q-projects"></a>Q # プロジェクトを更新しています 

Q # 操作をホストするC#ためにまたは Python のどちらを使用しているかにかかわらず、次の手順に従って q # プロジェクトを更新します。

1. まず、 [.NET Core SDK 3.1](https://dotnet.microsoft.com/download)の最新バージョンがあることを確認します。 コマンドプロンプトで次のコマンドを実行します。

    ```dotnetcli
    dotnet --version
    ```

    出力が `3.1.100` 以上であることを確認します。 インストールされていない場合は、[最新バージョン](https://dotnet.microsoft.com/download)をインストールして、もう一度確認します。 次に、セットアップに応じて、次の手順に従います (Visual Studio、Visual Studio Code、またはコマンドラインから直接)。

### <a name="update-q-projects-in-visual-studio"></a>Visual Studio での Q # プロジェクトの更新
 
1. 最新バージョンの Visual Studio 2019 に更新する方法について[は、こちら](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019)を参照してください。
2. Visual Studio でソリューションを開く
3. メニューから [**ビルド** -> **クリーンソリューション**] を選択します。
4. 各 .csproj ファイルで、ターゲットフレームワークを `netcoreapp3.0` に更新します (または、ライブラリプロジェクトの場合は `netstandard2.1` ます)。
    つまり、次のような形式の行を編集します。

    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```

    ターゲットフレームワークの指定の詳細については、[こちら](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)を参照してください。
5. ソリューション内のすべてのファイルを保存して閉じる
6. **ツール** -> **コマンドライン** -> を選択し**開発者コマンドプロンプト**
7. ソリューション内の各プロジェクトに対して、次のコマンドを実行します。

    ```dotnetcli
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   プロジェクトで他の Microsoft の Quantum パッケージ (たとえば、Microsoft の Quantum) を使用している場合は、コマンドも実行します。
8. コマンドプロンプトを閉じ、[**ビルド** -> **ビルド**] を選択します ([ソリューションのリビルド *] は選択しないでください)*

これで[、Visual Studio QDK 拡張機能を更新](#update-visual-studio-qdk-extension)することができます。


### <a name="update-q-projects-in-visual-studio-code"></a>Visual Studio Code で Q # プロジェクトを更新する

1. Visual Studio Code で、更新するプロジェクトが格納されているフォルダーを開きます。
2. **ターミナル** ->  **[新しいターミナル]** を選択します。
3. コマンドラインを使用して更新するための指示に従います (すぐ下)。

### <a name="update-q-projects-using-the-command-line"></a>コマンドラインを使用して Q # プロジェクトを更新する

1. プロジェクトファイルが格納されているフォルダーに移動します。
2. 次のコマンドを実行します。

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. 各 .csproj ファイルで、ターゲットフレームワークを `netcoreapp3.0` に更新します (または、ライブラリプロジェクトの場合は `netstandard2.1` ます)。
    つまり、次のような形式の行を編集します。

    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```

    ターゲットフレームワークの指定の詳細については、[こちら](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)を参照してください。
4. 次のコマンドを実行します。

    ```dotnetcli
    dotnet add package Microsoft.Quantum.Development.Kit
    ```

    プロジェクトで他の Microsoft の Quantum パッケージ (たとえば、Microsoft の Quantum) を使用している場合は、コマンドも実行します。
5. すべてのファイルを保存して閉じます。
6. プロジェクトの依存関係ごとに1-4 を繰り返し、メインプロジェクトが含まれているフォルダーに戻り、を実行します。

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
* [コマンドラインと: C#プロジェクトテンプレートの更新](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a>Python 用の IQ # の更新

1. `iqsharp` カーネルを更新する 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. `iqsharp` のバージョンを確認する

    ```dotnetcli
    dotnet iqsharp --version
    ```

    以下の出力が表示されます。

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    `iqsharp` のバージョンが高い場合は心配しないでください。[最新のリリース](xref:microsoft.quantum.relnotes)と一致している必要があります。

3. `qsharp` パッケージを更新する

    ```bash
    pip install qsharp --upgrade
    ```

4. `qsharp` のバージョンを確認する

    ```bash
    pip show qsharp
    ```

    以下の出力が表示されます。

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. `.qs` ファイルの場所から次のコマンドを実行します。

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. 更新された QDK バージョンを使用して、既存の quantum プログラムを実行できるようになりました。

### <a name="update-iq-for-jupyter-notebooks"></a>Jupyter Notebook の IQ # を更新する

1. `iqsharp` カーネルを更新する

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. `iqsharp` のバージョンを確認する

    ```dotnetcli
    dotnet iqsharp --version
    ```

    出力は次のようになります。

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    `iqsharp` のバージョンが高い場合は心配しないでください。[最新のリリース](xref:microsoft.quantum.relnotes)と一致している必要があります。

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
    - **[拡張]** タブに移動します。
    - Visual Studio Code 拡張機能**の Microsoft Quantum Development Kit**を選択します
    - 拡張機能の再読み込み

2. クォンタムプロジェクトテンプレートを更新します。

   - **[表示]**  ->  **[コマンド パレット]** の順に選択します。
   - **[Q #: プロジェクトテンプレートのインストール]** を選択します。
   - 数秒後に、"プロジェクトテンプレートが正常にインストールされました" というポップアップが表示されます。

### <a name="c-using-the-dotnet-command-line-tool"></a>C#、`dotnet` コマンドラインツールの使用

1. .NET 用の Quantum プロジェクトテンプレートを更新する

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a>次の操作

お好みの環境で Quantum 開発キットを更新したので、引き続き quantum プログラムの開発と実行を行うことができます。 プログラムをまだ作成していない場合は、[最初のクォンタムプログラム](xref:microsoft.quantum.write-program)を開始することができます。
