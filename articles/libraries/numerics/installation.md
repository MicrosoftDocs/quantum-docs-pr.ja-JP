---
title: 数値ライブラリのインストールと検証 |Microsoft Docs
description: 数値ライブラリのインストールと検証
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: 8369a6f342ee8e6f56b69bd1f2ce3df40e4093aa
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184629"
---
# <a name="numerics-library-installation-and-validation"></a><span data-ttu-id="340c4-103">数値ライブラリのインストールと検証</span><span class="sxs-lookup"><span data-stu-id="340c4-103">Numerics Library Installation and Validation</span></span>

<span data-ttu-id="340c4-104">Quantum 開発キットでは、 [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet パッケージを使用した数値の機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="340c4-104">The Quantum Development Kit provides support for numerics functionality through the [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet package.</span></span>

<span data-ttu-id="340c4-105">**Visual Studio > = 2019:** Visual Studio 2019 以降を使用している場合は、NuGet パッケージマネージャーを使用して数値パッケージを追加できます。</span><span class="sxs-lookup"><span data-stu-id="340c4-105">**Visual Studio >=2019:** If you are using Visual Studio 2019 or later, you can add the numerics package using the NuGet Package Manager.</span></span>
<span data-ttu-id="340c4-106">これを行うには、[NuGet パッケージの管理...] を選択します。Visual Studio の [プロジェクト] メニュー項目を表示します。</span><span class="sxs-lookup"><span data-stu-id="340c4-106">To do so, select "Manage NuGet Packages..." from the "Project" menu item in Visual Studio.</span></span>

<span data-ttu-id="340c4-107">[参照] タブで、パッケージ名 "Microsoft. Quantum" を検索します。</span><span class="sxs-lookup"><span data-stu-id="340c4-107">From the Browse tab, search for the package name "Microsoft.Quantum.Numerics"</span></span>

> [!NOTE]
> <span data-ttu-id="340c4-108">必ず [プレリリース版を含める] をオンにしてください。</span><span class="sxs-lookup"><span data-stu-id="340c4-108">Make sure to tick "Include prerelease"</span></span>

<span data-ttu-id="340c4-109">これにより、ダウンロード可能なパッケージが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="340c4-109">This will list the packages available for download.</span></span>
<span data-ttu-id="340c4-110">"Microsoft..............?" をポイントすると、バージョン番号の右側に下向きの矢印が表示されます。</span><span class="sxs-lookup"><span data-stu-id="340c4-110">Hovering over "Microsoft.Quantum.Numerics" reveals a downward-pointing arrow to the right of the version number.</span></span>
<span data-ttu-id="340c4-111">数値パッケージをインストールするには、矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="340c4-111">Click on the arrow in order to install the numerics package.</span></span>

<span data-ttu-id="340c4-112">詳細については、「[パッケージマネージャー UI ガイド](https://docs.microsoft.com/nuget/tools/package-manager-ui)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="340c4-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="340c4-113">または、パッケージマネージャーコンソールを使用して、コマンドラインインターフェイスを使用して数値ライブラリをプロジェクトに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="340c4-113">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="340c4-114">パッケージマネージャーコンソールで、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="340c4-114">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="340c4-115">詳細については、「[パッケージマネージャーコンソールガイド](https://docs.microsoft.com/nuget/tools/package-manager-console)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="340c4-115">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="340c4-116">**コマンドラインまたは Visual Studio Code:** コマンドラインを単独で、または Visual Studio Code 内から使用する場合は、`dotnet` コマンドを使用して NuGet パッケージ参照をプロジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="340c4-116">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```bash
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a><span data-ttu-id="340c4-117">インストールの確認</span><span class="sxs-lookup"><span data-stu-id="340c4-117">Verifying your installation</span></span>

<span data-ttu-id="340c4-118">残りの Quantum 開発キットと同様に、数値ライブラリには、できるだけ早く開始するのに役立つサンプルが付属しています。</span><span class="sxs-lookup"><span data-stu-id="340c4-118">Like the rest of the Quantum Development Kit, the numerics library comes with samples that help you get started as quickly as possible.</span></span>
<span data-ttu-id="340c4-119">これらのサンプルを使用してインストールをテストするには、[メインサンプルリポジトリ](https://github.com/Microsoft/Quantum)を複製し、サンプルのいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="340c4-119">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum) and then run one of the samples.</span></span>

<span data-ttu-id="340c4-120">[`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/Numerics/CustomModAdd)サンプルを実行するには:</span><span class="sxs-lookup"><span data-stu-id="340c4-120">To run the [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/Numerics/CustomModAdd) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics/CustomModAdd
dotnet run
```