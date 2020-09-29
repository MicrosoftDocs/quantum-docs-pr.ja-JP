---
title: Q# と Binder を使用した開発
description: Binder を使用して Q# アプリケーションを作成する方法について説明します。
author: bradben
ms.author: v-benbra
ms.date: 9/03/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.binder
no-loc:
- Q#
- $$v
ms.openlocfilehash: f993a1145dd8c01045d4cc7cfd0c98efd574ea78
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90836559"
---
# <a name="develop-with-no-locq-and-binder"></a><span data-ttu-id="974e7-103">Q# と Binder を使用した開発</span><span class="sxs-lookup"><span data-stu-id="974e7-103">Develop with Q# and Binder</span></span>

<span data-ttu-id="974e7-104">Binder を使用して、Jupyter Notebook をオンラインで実行し、共有することができます。</span><span class="sxs-lookup"><span data-stu-id="974e7-104">You can use Binder to run and share your Jupyter Notebooks online.</span></span>

## <a name="use-binder-with-the-microsoft-qdk-samples"></a><span data-ttu-id="974e7-105">Microsoft QDK サンプルでの Binder の使用</span><span class="sxs-lookup"><span data-stu-id="974e7-105">Use Binder with the Microsoft QDK samples</span></span>

<span data-ttu-id="974e7-106">Microsoft QDK サンプルを使用するように Binder を自動的に構成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="974e7-106">To configure Binder automatically to use the Microsoft QDK samples:</span></span>

1. <span data-ttu-id="974e7-107">ブラウザーを開いて､ https://aka.ms/try-qsharp を実行します。</span><span class="sxs-lookup"><span data-stu-id="974e7-107">Open a browser and run https://aka.ms/try-qsharp.</span></span>
1. <span data-ttu-id="974e7-108">**Quantum Development Kit Samples** ランディング ページで、 **[Q# notebook]** をクリックして、IQ# を使用して独自の量子アプリケーション ノートブックを記述する方法を学習します。</span><span class="sxs-lookup"><span data-stu-id="974e7-108">On the **Quantum Development Kit Samples** landing page, click **Q# notebook** to learn how to use IQ# to write your own quantum application notebooks.</span></span>

![QDK ランディング ページ](~/media/binder-install.png)

## <a name="use-binder-with-your-own-notebooks-and-repository"></a><span data-ttu-id="974e7-110">独自のノートブックとリポジトリで Binder を使用する</span><span class="sxs-lookup"><span data-stu-id="974e7-110">Use Binder with your own notebooks and repository</span></span>

<span data-ttu-id="974e7-111">GitHub リポジトリに既にノートブックがある場合は、リポジトリと連携するように Binder を構成できます。</span><span class="sxs-lookup"><span data-stu-id="974e7-111">If you already have notebooks in a GitHub repository, you can configure Binder to work with your repo:</span></span>

1. <span data-ttu-id="974e7-112">リポジトリのルートに *Dockerfile* という名前のファイルがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="974e7-112">Ensure that there is a file named *Dockerfile* in the root of your repository.</span></span> <span data-ttu-id="974e7-113">このファイルには、少なくとも次の行が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="974e7-113">The file must contain at least the following lines:</span></span>

    ```bash
    FROM mcr.microsoft.com/quantum/iqsharp-base:0.12.20082513
    
    USER root
    COPY . ${HOME}
    RUN chown -R ${USER} ${HOME}
    
    USER ${USER}
    ```

    > [!NOTE]
    > <span data-ttu-id="974e7-114">IQ# の最新バージョンは、[リリース ノート](xref:microsoft.quantum.relnotes)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="974e7-114">You can verify the most current version of IQ# in the [Release Notes](xref:microsoft.quantum.relnotes).</span></span>

    <span data-ttu-id="974e7-115">Dockerfile 作成の詳細については、[Dockerfile リファレンス](https://docs.docker.com/engine/reference/builder/)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="974e7-115">For more information about creating a Dockerfile, see the [Dockerfile reference](https://docs.docker.com/engine/reference/builder/).</span></span>

2. <span data-ttu-id="974e7-116">ブラウザーを開いて、[mybinder.org](https://mybinder.org) を表示します。</span><span class="sxs-lookup"><span data-stu-id="974e7-116">Open a browser to [mybinder.org](https://mybinder.org).</span></span>
3. <span data-ttu-id="974e7-117">**GitHub URL** としてリポジトリ名 (たとえば *MyName/MyRepo*) を入力し、 **[launch]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="974e7-117">Enter your repository name as the **GitHub URL** (for example *MyName/MyRepo*), and click **launch**.</span></span>

![MyBinder フォーム](~/media/mybinder.png)
    
## <a name="next-steps"></a><span data-ttu-id="974e7-119">次のステップ</span><span class="sxs-lookup"><span data-stu-id="974e7-119">Next steps</span></span>

<span data-ttu-id="974e7-120">これで、Binder 環境の設定が完了したので、[最初の量子プログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行できます。</span><span class="sxs-lookup"><span data-stu-id="974e7-120">Now that you have set up your Binder environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
