---
title: 数値ライブラリのインストールと検証 |Microsoft Docs
description: 数値ライブラリのインストールと検証
author: thomashaener
ms.author: thhaner
ms.date: 05/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: c41bb73ea484271689eea2ca1b59ce6639dc15a7
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036459"
---
# <a name="numerics-library-installation-and-validation"></a>数値ライブラリのインストールと検証

Quantum 開発キットでは、 [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet パッケージを使用した数値の機能がサポートされています。

**Visual Studio > = 2019:** Visual Studio 2019 以降を使用している場合は、NuGet パッケージマネージャーを使用して数値パッケージを追加できます。
これを行うには、[NuGet パッケージの管理...] を選択します。Visual Studio の [プロジェクト] メニュー項目を表示します。

[参照] タブで、パッケージ名 "Microsoft. Quantum" を検索します。

> [!NOTE]
> 必ず [プレリリース版を含める] をオンにしてください。

これにより、ダウンロード可能なパッケージが一覧表示されます。
"Microsoft..............?" をポイントすると、バージョン番号の右側に下向きの矢印が表示されます。
数値パッケージをインストールするには、矢印をクリックします。

詳細については、「[パッケージマネージャー UI ガイド](https://docs.microsoft.com/nuget/tools/package-manager-ui)」を参照してください。

または、パッケージマネージャーコンソールを使用して、コマンドラインインターフェイスを使用して数値ライブラリをプロジェクトに追加することもできます。

![](../../media/vs2017-nuget-console-menu.png)

パッケージマネージャーコンソールで、次のように実行します。

```
Install-Package Microsoft.Quantum.Numerics
```

詳細については、「[パッケージマネージャーコンソールガイド](https://docs.microsoft.com/nuget/tools/package-manager-console)」を参照してください。

**コマンドラインまたは Visual Studio Code:** コマンドラインを単独で、または Visual Studio Code 内から使用する場合は、`dotnet` コマンドを使用して NuGet パッケージ参照をプロジェクトに追加できます。

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a>インストールの確認

残りの Quantum 開発キットと同様に、数値ライブラリには、できるだけ早く開始するのに役立つサンプルが付属しています。
これらのサンプルを使用してインストールをテストするには、[メインサンプルリポジトリ](https://github.com/Microsoft/Quantum)を複製し、サンプルのいずれかを実行します。

[`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd)サンプルを実行するには:

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
