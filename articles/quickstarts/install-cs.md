---
title: Q# と .NET を使用した開発
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 714c15d9589095f0fe395fcd6941672167879dca
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885504"
---
# <a name="develop-with-q-and-net"></a>Q# と .NET を使用した開発

Q# は、C# や F# などの .NET 言語とうまく動作するように構築されています。
このガイドでは、Q# を .NET 言語で作成されたホスト プログラムとともに使用する方法を説明します。

まず、Q# アプリケーションと .NET ホストを作成し、次にホストから Q# を呼び出す方法を示します。

## <a name="prerequisites"></a>前提条件

- [Q# コマンド ライン プロジェクトで使用するための](xref:microsoft.quantum.install.standalone) Quantum 開発キットをインストールしていること。

## <a name="creating-a-q-library-and-a-net-host"></a>Q# ライブラリと .NET ホストを作成する

最初の手順として、Q# ライブラリのプロジェクトと、Q# ライブラリで定義された演算と関数を呼び出す .NET ホストのプロジェクトを作成します。

お使いの開発環境に対応するタブの指示に従ってください。
Visual Studio または VS Code 以外のエディターを使用している場合は、コマンド ラインの手順に従ってください。

### <a name="visual-studio-code-or-command-line"></a>[Visual Studio Code またはコマンド ライン](#tab/tabid-cmdline)

- 新しい Q# ライブラリを作成する

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- 新しい C# または F# のコンソール プロジェクトを作成する

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- Q# ライブラリを、ホスト プログラムからの参照として追加する

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- [オプション] 両方のプロジェクトに対してソリューションを作成する

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

- 新しい Q# ライブラリを作成する
  - **[ファイル]**  ->  **[新規]**  ->  **[プロジェクト]** の順に移動します。
  - 検索ボックスに、「Q#」と入力します
  - **[Q# ライブラリ]** を選択します
  - **[次へ]** を選択します
  - ライブラリの名前と場所を選択します
  - [ソリューションとプロジェクトを同じディレクトリに配置する] に**チェックを入れない**ようにします
  - **[作成]**
- 新しい C# または F# のホスト プログラムを作成する
  - **[ファイル]** → **[新規作成]** → **[プロジェクト]** に移動します
  - C# または F# の [コンソール アプリ (.NET Core)] を選択します
  - **[次へ]** を選択します
  - *[ソリューション]* で、[ソリューションに追加] を選択します
  - ホスト プログラムの名前を選択します
  - **[作成]**

***

## <a name="calling-into-q-from-net"></a>.NET から Q# を呼び出す

上の手順に従ってプロジェクトを設定したら、.NET コンソール アプリケーションから Q# を呼び出すことができます。
Q# コンパイラは、それぞれの Q# の演算と関数に対して .NET クラスを作成します。これにより、量子プログラムをシミュレーターで実行できるようになります。

たとえば、[.NET の相互運用性サンプル](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)には、次の Q# の演算の例が含まれています。

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

量子シミュレーターで .NET からこの演算を呼び出すには、Q# コンパイラが生成した `RunAlgorithm` .NET クラスの `Run` メソッドを使用できます。

### <a name="c"></a>[C#](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[F#](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a>次のステップ

これで、Q# コマンド ライン プログラムと .NET との相互運用性の両方に対して Quantum 開発キットを設定することができたので、[初めての量子プログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行することができます。
