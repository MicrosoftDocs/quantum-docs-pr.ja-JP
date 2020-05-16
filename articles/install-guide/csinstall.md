---
title: Q# と .NET を使用した開発
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 155367dbb1373f00e2b0bd732a5319b32462c9f9
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426502"
---
# <a name="develop-with-q-and-net"></a>Q# と .NET を使用した開発

Q # は、C# や F # などの .NET 言語で適切に動作するように構築されています。
このガイドでは、.NET 言語で記述されたホストプログラムで Q # を使用する方法について説明します。

## <a name="prerequisites"></a>必須コンポーネント

- [Q # コマンドラインプロジェクトで使用するための](xref:microsoft.quantum.install.standalone)Quantum 開発キットをインストールします。

## <a name="creating-a-q-library-and-a-net-host"></a>Q # ライブラリと .NET ホストの作成

最初の手順では、Q # ライブラリのプロジェクトを作成し、Q # ライブラリで定義されている操作と関数を呼び出す .NET ホストを作成します。

### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

- 新しい Q # ライブラリを作成する
  - ファイルの**File**  ->  **新しい**  ->  **プロジェクト**にアクセス
  - 検索ボックスに「Q #」と入力します。
  - **Q # ライブラリ**を選択します
  - **次**を選択
  - ライブラリの名前と場所を選択します
  - [プロジェクトとソリューションを同じディレクトリに配置する] が**オフ**になっていることを確認します。
  - **[作成]**
- 新しい C# または F # ホストプログラムを作成する
  - **ファイル**にジャンプ→ [**新規**] → [**プロジェクト**]
  - C# または F に対して [Console App (.NET Core)] を選択します。#
  - **次**を選択
  - [*ソリューション*] で、[ソリューションに追加] を選択します。
  - ホストプログラムの名前を選択してください
  - **[作成]**

### <a name="visual-studio-code-or-command-line"></a>[Visual Studio Code またはコマンドライン](#tab/tabid-cmdline)

- 新しい Q # ライブラリを作成する

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- 新しい C# または F # コンソールプロジェクトを作成する

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- ホストプログラムからの参照として Q # ライブラリを追加する

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- Optional両方のプロジェクトのソリューションを作成する

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a>.NET から Q # への呼び出し

上記の手順に従ってプロジェクトを設定したら、.NET コンソールアプリケーションから Q # を呼び出すことができます。
Q # コンパイラは、各 Q # 操作に対して .NET クラスを作成し、シミュレーターでクォンタムプログラムを実行できるようにします。

たとえば、 [.net 相互運用性のサンプル](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)には、Q # 操作の次の例が含まれています。

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

クォンタムシミュレーターで .NET からこの操作を呼び出すには、 `Run` `RunAlgorithm` Q # コンパイラによって生成された .net クラスのメソッドを使用できます。

### <a name="c"></a>[C#](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[F#](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a>次の手順

これで、2つのコマンドラインプログラムに対してクォンタム開発キットがセットアップされました。また、.NET との相互運用性のために、[最初のクォンタムプログラム](xref:microsoft.quantum.quickstarts.qrng)を記述して実行することができます。
