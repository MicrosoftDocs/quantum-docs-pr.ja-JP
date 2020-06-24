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
# <a name="numerics-library-installation-and-validation"></a><span data-ttu-id="f0b17-103">数値ライブラリのインストールと検証</span><span class="sxs-lookup"><span data-stu-id="f0b17-103">Numerics Library Installation and Validation</span></span>

<span data-ttu-id="f0b17-104">Quantum 開発キットでは、NuGet パッケージを使用した数値の機能がサポートされて [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) います。</span><span class="sxs-lookup"><span data-stu-id="f0b17-104">The Quantum Development Kit provides support for numerics functionality through the [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet package.</span></span>

<span data-ttu-id="f0b17-105">**Visual Studio >= 2019:** Visual Studio 2019 以降を使用している場合は、NuGet パッケージマネージャーを使用して数値パッケージを追加できます。</span><span class="sxs-lookup"><span data-stu-id="f0b17-105">**Visual Studio >=2019:** If you are using Visual Studio 2019 or later, you can add the numerics package using the NuGet Package Manager.</span></span>
<span data-ttu-id="f0b17-106">これを行うには、[NuGet パッケージの管理...] を選択します。Visual Studio の [プロジェクト] メニュー項目を表示します。</span><span class="sxs-lookup"><span data-stu-id="f0b17-106">To do so, select "Manage NuGet Packages..." from the "Project" menu item in Visual Studio.</span></span>

<span data-ttu-id="f0b17-107">[参照] タブで、パッケージ名 "Microsoft. Quantum" を検索します。</span><span class="sxs-lookup"><span data-stu-id="f0b17-107">From the Browse tab, search for the package name "Microsoft.Quantum.Numerics"</span></span>

> [!NOTE]
> <span data-ttu-id="f0b17-108">必ず [プレリリース版を含める] をオンにしてください。</span><span class="sxs-lookup"><span data-stu-id="f0b17-108">Make sure to tick "Include prerelease"</span></span>

<span data-ttu-id="f0b17-109">これにより、ダウンロード可能なパッケージが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0b17-109">This will list the packages available for download.</span></span>
<span data-ttu-id="f0b17-110">"Microsoft..............?" をポイントすると、バージョン番号の右側に下向きの矢印が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0b17-110">Hovering over "Microsoft.Quantum.Numerics" reveals a downward-pointing arrow to the right of the version number.</span></span>
<span data-ttu-id="f0b17-111">数値パッケージをインストールするには、矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0b17-111">Click on the arrow in order to install the numerics package.</span></span>

<span data-ttu-id="f0b17-112">詳細については、「[パッケージマネージャー UI ガイド](https://docs.microsoft.com/nuget/tools/package-manager-ui)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b17-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="f0b17-113">または、パッケージマネージャーコンソールを使用して、コマンドラインインターフェイスを使用して数値ライブラリをプロジェクトに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="f0b17-113">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![コマンドラインからのパッケージマネージャーコンソールの使用](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="f0b17-115">パッケージマネージャーコンソールで、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="f0b17-115">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="f0b17-116">詳細については、「[パッケージマネージャーコンソールガイド](https://docs.microsoft.com/nuget/tools/package-manager-console)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b17-116">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="f0b17-117">**コマンドラインまたは Visual Studio Code:** コマンドラインを単独で、または Visual Studio Code 内で使用すると、コマンドを使用して `dotnet` NuGet パッケージ参照をプロジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="f0b17-117">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a><span data-ttu-id="f0b17-118">インストールの確認</span><span class="sxs-lookup"><span data-stu-id="f0b17-118">Verifying your installation</span></span>

<span data-ttu-id="f0b17-119">残りの Quantum 開発キットと同様に、数値ライブラリには、できるだけ早く開始するのに役立つサンプルが付属しています。</span><span class="sxs-lookup"><span data-stu-id="f0b17-119">Like the rest of the Quantum Development Kit, the numerics library comes with samples that help you get started as quickly as possible.</span></span>
<span data-ttu-id="f0b17-120">これらのサンプルを使用してインストールをテストするには、[メインサンプルリポジトリ](https://github.com/Microsoft/Quantum)を複製し、サンプルのいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0b17-120">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum) and then run one of the samples.</span></span>

<span data-ttu-id="f0b17-121">サンプルを実行するには、次のようにし [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) ます。</span><span class="sxs-lookup"><span data-stu-id="f0b17-121">To run the [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
