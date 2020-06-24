---
title: Microsoft 量子数値ライブラリ-インストールと検証
description: Microsoft Quantum の数値ライブラリを Visual Studio 2019 以降のインストールに追加する方法について説明します。
author: thomashaener
ms.author: thhaner
ms.date: 05/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: 60ee91a552fad5becf8eda437406b6e0dfba0eb4
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276124"
---
# <a name="numerics-library-installation-and-validation"></a>数値ライブラリのインストールと検証

Quantum 開発キットでは、NuGet パッケージを使用した数値の機能がサポートされて [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) います。

**Visual Studio >= 2019:** Visual Studio 2019 以降を使用している場合は、NuGet パッケージマネージャーを使用して数値パッケージを追加できます。
これを行うには、[NuGet パッケージの管理...] を選択します。Visual Studio の [プロジェクト] メニュー項目を表示します。

[参照] タブで、パッケージ名 "Microsoft. Quantum" を検索します。

> [!NOTE]
> 必ず [プレリリース版を含める] をオンにしてください。

これにより、ダウンロード可能なパッケージが一覧表示されます。
"Microsoft..............?" をポイントすると、バージョン番号の右側に下向きの矢印が表示されます。
数値パッケージをインストールするには、矢印をクリックします。

詳細については、「[パッケージマネージャー UI ガイド](https://docs.microsoft.com/nuget/tools/package-manager-ui)」を参照してください。

または、パッケージマネージャーコンソールを使用して、コマンドラインインターフェイスを使用して数値ライブラリをプロジェクトに追加することもできます。

![コマンドラインからのパッケージマネージャーコンソールの使用](~/media/vs2017-nuget-console-menu.png)

パッケージマネージャーコンソールで、次のように実行します。

```
Install-Package Microsoft.Quantum.Numerics
```

詳細については、「[パッケージマネージャーコンソールガイド](https://docs.microsoft.com/nuget/tools/package-manager-console)」を参照してください。

**コマンドラインまたは Visual Studio Code:** コマンドラインを単独で、または Visual Studio Code 内で使用すると、コマンドを使用して `dotnet` NuGet パッケージ参照をプロジェクトに追加できます。

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a>インストールの確認

残りの Quantum 開発キットと同様に、数値ライブラリには、できるだけ早く開始するのに役立つサンプルが付属しています。
これらのサンプルを使用してインストールをテストするには、[メインサンプルリポジトリ](https://github.com/Microsoft/Quantum)を複製し、サンプルのいずれかを実行します。

サンプルを実行するには、次のようにし [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) ます。

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
