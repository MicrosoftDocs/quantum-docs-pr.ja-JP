---
title: プル要求を開く
description: Microsoft Quantum Development Kit にコードまたはドキュメントを投稿する準備ができたら、GitHub プル要求を送信する方法について説明します。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.pulls
ms.openlocfilehash: 82af3b5123588cc06882f746ffcb0402ad3f0f2e
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275479"
---
# <a name="opening-pull-requests"></a><span data-ttu-id="44cb1-103">pull request を開く</span><span class="sxs-lookup"><span data-stu-id="44cb1-103">Opening Pull Requests</span></span> #

<span data-ttu-id="44cb1-104">Quantum 開発キットのドキュメントはすべて、GitHub でホストされている複数のリポジトリを使用して、Git バージョン管理システムを使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="44cb1-104">All of the documentation for the Quantum Development Kit is managed using the Git version control system through the use of several repositories hosted on GitHub.</span></span>
<span data-ttu-id="44cb1-105">Git と GitHub を一緒に使用することで、Quantum 開発キットで幅広く共同作業が容易になります。</span><span class="sxs-lookup"><span data-stu-id="44cb1-105">Using Git and GitHub together makes it easy to collaborate widely on the Quantum Development Kit.</span></span>
<span data-ttu-id="44cb1-106">特に、Git リポジトリを複製したりフォークしたりして、そのリポジトリの完全に独立したコピーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="44cb1-106">In particular, any Git repository can be cloned or forked to make a completely independent copy of that repository.</span></span>
<span data-ttu-id="44cb1-107">これにより、ツールを使用した投稿や、好きなペースで作業できるようになります。</span><span class="sxs-lookup"><span data-stu-id="44cb1-107">This allows you to work on your contribution with the tools and at a pace that you prefer.</span></span>

<span data-ttu-id="44cb1-108">準備ができたら、GitHub の_プル要求_機能を使用して、リポジトリへの投稿を含めるように要求を送信できます。</span><span class="sxs-lookup"><span data-stu-id="44cb1-108">When you're ready, you can send us a request to include your contribution into our repos, using GitHub's _pull request_ functionality.</span></span>
<span data-ttu-id="44cb1-109">各プル要求のページには、投稿物を作成するすべての変更の詳細、投稿物に関するコメントの一覧、コミュニティの他のメンバーがフィードバックやアドバイスを提供するために使用できる一連のレビューツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="44cb1-109">The page for each pull request includes details of all the changes that make your contribution, a list of comments on your contribution, and a set of review tools that other members of the community can use to provide feedback and advice.</span></span>

> [!NOTE]
> <span data-ttu-id="44cb1-110">Git の完全なチュートリアルはこのガイドの範囲を超えていますが、Git の詳細については、次のリンク先を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44cb1-110">While a full tutorial on Git is beyond the scope of this guide, we can suggest the following links for more resources on learning Git:</span></span>
>
> - <span data-ttu-id="44cb1-111">[Git について説明](https://www.atlassian.com/git)します。 Atlassian からの一連の git チュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="44cb1-111">[Learn Git](https://www.atlassian.com/git): A set of Git tutorials from Atlassian.</span></span>
> - <span data-ttu-id="44cb1-112">[Visual Studio Code のバージョン管理](https://code.visualstudio.com/docs/editor/versioncontrol): GIT の GUI として Visual Studio Code を使用する方法についてのガイドです。</span><span class="sxs-lookup"><span data-stu-id="44cb1-112">[Version Control in Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): A guide on how to use Visual Studio Code as a GUI for Git.</span></span>
> - <span data-ttu-id="44cb1-113">[Github の学習ラボ](https://lab.github.com/): Git、GitHub、および関連テクノロジを使用するための一連のオンラインコースです。</span><span class="sxs-lookup"><span data-stu-id="44cb1-113">[GitHub Learning Lab](https://lab.github.com/): A set of online courses for using Git, GitHub, and related technologies.</span></span>
> - <span data-ttu-id="44cb1-114">[Git の視覚化](https://git-school.github.io/visualizing-git/): git コマンドがリポジトリの状態を変更する方法を視覚化するための対話型ツールです。</span><span class="sxs-lookup"><span data-stu-id="44cb1-114">[Visualizing Git](https://git-school.github.io/visualizing-git/): An interactive tool for visualizing how Git commands change the state of a repository.</span></span>
> - <span data-ttu-id="44cb1-115">[Git を使用したバージョン管理 (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): 科学技術計算に向けた git チュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="44cb1-115">[Version Control with Git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): A Git tutorial oriented towards scientific computing.</span></span>
> - <span data-ttu-id="44cb1-116">[Git の分岐について学習](https://learngitbranching.js.org/)する: 新しい git 機能の学習に役立つ分岐とリベースの対話のセット。</span><span class="sxs-lookup"><span data-stu-id="44cb1-116">[Learn Git Branching](https://learngitbranching.js.org/): An interactive set of branching and rebasing puzzles to help learn new Git features.</span></span>

## <a name="what-is-a-pull-request"></a><span data-ttu-id="44cb1-117">プル要求とは</span><span class="sxs-lookup"><span data-stu-id="44cb1-117">What is a Pull Request?</span></span> ##

<span data-ttu-id="44cb1-118">前述のように、プル要求の内容について、少し時間を取っておくと**便利です。**</span><span class="sxs-lookup"><span data-stu-id="44cb1-118">Having said the above, it's helpful to take a few moments to say what a pull request **is**.</span></span>
<span data-ttu-id="44cb1-119">Git を使用する場合、変更は、変更前にリポジトリの状態にどのように関連しているかを説明する_コミット_として表されます。</span><span class="sxs-lookup"><span data-stu-id="44cb1-119">When working with Git, any changes are represented as _commits_ that describe how those changes are related to the state of the repository before those changes.</span></span>
<span data-ttu-id="44cb1-120">多くの場合、前のコミットからの矢印を持つ円としてコミットが描画される図を描画します。</span><span class="sxs-lookup"><span data-stu-id="44cb1-120">We'll often draw diagrams in which commits are drawn as circles with arrows from previous commits.</span></span>

<span data-ttu-id="44cb1-121">という_分岐_で投稿を開始したと `feature` します。</span><span class="sxs-lookup"><span data-stu-id="44cb1-121">Suppose you have started a contribution in a _branch_ called `feature`.</span></span>
<span data-ttu-id="44cb1-122">その後、 **Microsoft/クォンタム**のフォークは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="44cb1-122">Then your fork of **Microsoft/Quantum** might look something like this:</span></span>

![GitHub の作業ブランチ](~/media/git-workflow-step0.png)

<span data-ttu-id="44cb1-124">ローカルリポジトリに変更を加えた場合は、別のリポジトリから変更を_取得_して、上流に発生した変更をキャッチアップできます。</span><span class="sxs-lookup"><span data-stu-id="44cb1-124">If you make your changes in your local repository, you can _pull_ changes from another repository into yours to catch up to any changes that happened upstream.</span></span>

![アップストリームリポジトリから変更をプルしてマージする](~/media/git-workflow-step1.png)

<span data-ttu-id="44cb1-126">プル要求は同じように動作しますが、逆に、プル要求を開いたときに、で投稿をプルするようにアップストリームリポジトリを要求します。</span><span class="sxs-lookup"><span data-stu-id="44cb1-126">Pull requests work the same way, but in reverse: when you open a pull request, you ask for the upstream repository to pull your contribution in.</span></span>

![元のリポジトリに変更内容を再度プルするよう要求しています](~/media/git-workflow-step2.png)

<span data-ttu-id="44cb1-128">いずれかのリポジトリに対してプル要求を開くと、GitHub はコミュニティ内の他のユーザーが変更の概要を確認し、コメントする機会を提供し、さらに優れた投稿を作成するための提案を行います。</span><span class="sxs-lookup"><span data-stu-id="44cb1-128">When you open a pull request to one of our repositories, GitHub will offer an opportunity for others in the community to see a summary of your changes, to comment on them, and to make suggestions for how to help make an even better contribution.</span></span>

![GitHub のプル要求のスクリーンショット](~/media/pull-request-header.png)

<span data-ttu-id="44cb1-130">このプロセスを使用すると、GitHub の機能を使用して、共同作業を改善し、quantum プログラミングコミュニティの高品質の製品を維持することができます。</span><span class="sxs-lookup"><span data-stu-id="44cb1-130">Using this process helps us use GitHub functionality to improve contributions and to maintain a high-quality product for the quantum programming community.</span></span>

## <a name="how-to-make-a-pull-request"></a><span data-ttu-id="44cb1-131">プル要求を作成する方法</span><span class="sxs-lookup"><span data-stu-id="44cb1-131">How to Make a Pull Request</span></span> ##

<span data-ttu-id="44cb1-132">プル要求を行うには、主に2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="44cb1-132">There are two main ways to make a pull request.</span></span>  
<span data-ttu-id="44cb1-133">1つのファイルにのみ影響を与える小さな変更については、GitHub web インターフェイスを使用してプル要求を完全にオンラインにすることができます。</span><span class="sxs-lookup"><span data-stu-id="44cb1-133">For small changes that only affect a single file, the GitHub web interface can be used to make a pull request entirely online.</span></span> <span data-ttu-id="44cb1-134">編集するファイルに移動して、編集アイコンを使用するだけです。</span><span class="sxs-lookup"><span data-stu-id="44cb1-134">Simply navigate to the file you want to edit and use the edit icon.</span></span>  
<span data-ttu-id="44cb1-135">より複雑な投稿については、ほとんどの場合、ローカルコンピューターにリポジトリを複製して、最初にプル要求を準備する方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="44cb1-135">For more complicated contributions, it's most often easier to clone the repository to your local computer to prepare for a pull request first.</span></span>

<!--
### Using the Web Interface ###

**TODO**

### Command-Line and GitHub Flow ###

Most of the time, it's easier to prepare a pull request on your own computer; that makes it easier to work incrementally, and to test your changes.
If you haven't already done so, the first step is to _fork_ the repository that you'd like to contribute to.
Forking makes a complete clone of the original repository, but under your GitHub account instead of under [Microsoft](http://github.com/Microsoft/) or [MicrosoftDocs](http://github.com/MicrosoftDocs/).
This way, you can edit your personal fork to your heart's content before making a pull request for your work.

**TODO: pick up here**

## Code Review and Etiquette ##

**TODO: PR ettiquette, reviews, etc.**

-->

## <a name="next-steps"></a><span data-ttu-id="44cb1-136">次の手順</span><span class="sxs-lookup"><span data-stu-id="44cb1-136">Next steps</span></span> ##

<span data-ttu-id="44cb1-137">Git を使用して、Quantum 開発キットコミュニティをご利用いただき、ありがとうございます。</span><span class="sxs-lookup"><span data-stu-id="44cb1-137">Congratulations on using Git to help out the Quantum Development Kit community!</span></span>
<span data-ttu-id="44cb1-138">コードを投稿する方法の詳細については、次のガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="44cb1-138">To learn more about how to contribute code, please continue with the following guide.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="44cb1-139">コードを投稿する方法を学ぶ</span><span class="sxs-lookup"><span data-stu-id="44cb1-139">Learn how to contribute code</span></span>](xref:microsoft.quantum.contributing.code)
