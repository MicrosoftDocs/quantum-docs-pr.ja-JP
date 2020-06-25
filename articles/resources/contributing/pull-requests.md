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
# <a name="opening-pull-requests"></a>pull request を開く #

Quantum 開発キットのドキュメントはすべて、GitHub でホストされている複数のリポジトリを使用して、Git バージョン管理システムを使用して管理されます。
Git と GitHub を一緒に使用することで、Quantum 開発キットで幅広く共同作業が容易になります。
特に、Git リポジトリを複製したりフォークしたりして、そのリポジトリの完全に独立したコピーを作成することができます。
これにより、ツールを使用した投稿や、好きなペースで作業できるようになります。

準備ができたら、GitHub の_プル要求_機能を使用して、リポジトリへの投稿を含めるように要求を送信できます。
各プル要求のページには、投稿物を作成するすべての変更の詳細、投稿物に関するコメントの一覧、コミュニティの他のメンバーがフィードバックやアドバイスを提供するために使用できる一連のレビューツールが含まれています。

> [!NOTE]
> Git の完全なチュートリアルはこのガイドの範囲を超えていますが、Git の詳細については、次のリンク先を参照してください。
>
> - [Git について説明](https://www.atlassian.com/git)します。 Atlassian からの一連の git チュートリアルです。
> - [Visual Studio Code のバージョン管理](https://code.visualstudio.com/docs/editor/versioncontrol): GIT の GUI として Visual Studio Code を使用する方法についてのガイドです。
> - [Github の学習ラボ](https://lab.github.com/): Git、GitHub、および関連テクノロジを使用するための一連のオンラインコースです。
> - [Git の視覚化](https://git-school.github.io/visualizing-git/): git コマンドがリポジトリの状態を変更する方法を視覚化するための対話型ツールです。
> - [Git を使用したバージョン管理 (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): 科学技術計算に向けた git チュートリアルです。
> - [Git の分岐について学習](https://learngitbranching.js.org/)する: 新しい git 機能の学習に役立つ分岐とリベースの対話のセット。

## <a name="what-is-a-pull-request"></a>プル要求とは ##

前述のように、プル要求の内容について、少し時間を取っておくと**便利です。**
Git を使用する場合、変更は、変更前にリポジトリの状態にどのように関連しているかを説明する_コミット_として表されます。
多くの場合、前のコミットからの矢印を持つ円としてコミットが描画される図を描画します。

という_分岐_で投稿を開始したと `feature` します。
その後、 **Microsoft/クォンタム**のフォークは次のようになります。

![GitHub の作業ブランチ](~/media/git-workflow-step0.png)

ローカルリポジトリに変更を加えた場合は、別のリポジトリから変更を_取得_して、上流に発生した変更をキャッチアップできます。

![アップストリームリポジトリから変更をプルしてマージする](~/media/git-workflow-step1.png)

プル要求は同じように動作しますが、逆に、プル要求を開いたときに、で投稿をプルするようにアップストリームリポジトリを要求します。

![元のリポジトリに変更内容を再度プルするよう要求しています](~/media/git-workflow-step2.png)

いずれかのリポジトリに対してプル要求を開くと、GitHub はコミュニティ内の他のユーザーが変更の概要を確認し、コメントする機会を提供し、さらに優れた投稿を作成するための提案を行います。

![GitHub のプル要求のスクリーンショット](~/media/pull-request-header.png)

このプロセスを使用すると、GitHub の機能を使用して、共同作業を改善し、quantum プログラミングコミュニティの高品質の製品を維持することができます。

## <a name="how-to-make-a-pull-request"></a>プル要求を作成する方法 ##

プル要求を行うには、主に2つの方法があります。  
1つのファイルにのみ影響を与える小さな変更については、GitHub web インターフェイスを使用してプル要求を完全にオンラインにすることができます。 編集するファイルに移動して、編集アイコンを使用するだけです。  
より複雑な投稿については、ほとんどの場合、ローカルコンピューターにリポジトリを複製して、最初にプル要求を準備する方が簡単です。

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

## <a name="next-steps"></a>次の手順 ##

Git を使用して、Quantum 開発キットコミュニティをご利用いただき、ありがとうございます。
コードを投稿する方法の詳細については、次のガイドを参照してください。

> [!div class="nextstepaction"]
> [コードを投稿する方法を学ぶ](xref:microsoft.quantum.contributing.code)
