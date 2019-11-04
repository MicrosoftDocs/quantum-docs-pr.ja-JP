---
title: Microsoft Quantum Development Kit を更新する方法 (QDK) について説明します。
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: fc430a77f88878437e662c5b54507f70f3c6e020
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185853"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Microsoft Quantum Development Kit の更新 (QDK)

Microsoft Quantum Development Kit (QDK) を最新バージョンに更新する方法について説明します。

この記事では、QDK が既にインストールされていることを前提としています。 を初めてインストールする場合は、[インストールガイド](xref:microsoft.quantum.install)を参照してください。

更新手順は、開発環境によって異なります。 次のセクションから環境を選択します。

## <a name="python"></a>Python

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
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
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
    Version: 0.9.1909.3002
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. 更新された QDK バージョンを使用して、既存の quantum プログラムを実行できるようになりました。

## <a name="jupyter-notebooks"></a>Jupyter Notebook

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
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. これで、既存の Jupyter notebook を開いて、更新された QDK で実行できるようになりました。

## <a name="c-on-windows-using-visual-studio"></a>C#Windows の場合、Visual Studio の使用

1. Q # Visual Studio 拡張機能を更新する

    - Visual Studio によって、 [Quantum Visual studio 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)の更新を受け入れるように求められます
    - 更新プログラムを受け入れる

    > [!NOTE]
    > プロジェクトテンプレートは、拡張機能を使用して更新されます。 更新されたテンプレートは、新しく作成されたプロジェクトにのみ適用されます。 拡張機能が更新されても、既存のプロジェクトのコードは更新されません。

1. QDK パッケージを更新する

    - 既存のアプリケーションを開く
    - ソリューションエクスプローラーでの**依存関係**の選択
    - **[NuGet パッケージの管理]** を選択します。
    - Microsoft の Quantum パッケージを最新バージョンに更新し**ます。**

1. これで、最新の QDK でアプリケーションを実行できるようになりました。

## <a name="c-using-vs-code"></a>C#、VS Code の使用

1. クォンタム VS Code 拡張機能を更新する

    - 再起動 VS Code
    - **[拡張]** タブに移動します。
    - Visual Studio Code 拡張機能**の Microsoft Quantum Development Kit**を選択します
    - 拡張機能の再読み込み

1. クォンタムプロジェクトテンプレートを更新します。

   - **ビュー** -> **コマンドパレット**にアクセス
   - **[Q #: プロジェクトテンプレートのインストール]** を選択します。

1. VS Code で既存のアプリケーションを開きます。

   - .Csproj ファイルを編集して、新しいバージョンのパッケージを追加します。

    ```xml
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.9.1909.3002" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.9.1909.3002" />
    </ItemGroup>
    ```

    他の `Microsoft.Quantum` パッケージを使用する場合は、これらも更新します。

1. 更新された QDK でアプリケーションを実行できるようになりました。

## <a name="c-using-the-dotnet-command-line-tool"></a>C#、`dotnet` コマンドラインツールの使用

1. .NET 用の Quantum プロジェクトテンプレートを更新する

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. 既存のアプリケーションを更新して実行する

    - アプリケーションで QDK パッケージのバージョンを更新する

        ```bash
        dotnet add package Microsoft.Quantum.Development.Kit
        dotnet add package Microsoft.Quantum.Standard
        ```

        アプリケーションで他の `Microsoft.Quantum` パッケージを使用する場合は、これらも更新します。

    - アプリケーションを実行する

        ```bash
        dotnet run
        ```

    - 新しいパッケージバージョンでアプリケーションが実行されます。

## <a name="whats-next"></a>次に、

お好みの環境で Quantum 開発キットを更新したので、引き続き quantum プログラムの開発と実行を行うことができます。 プログラムをまだ作成していない場合は、[最初のクォンタムプログラム](xref:microsoft.quantum.write-program)を開始することができます。
