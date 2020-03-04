---
title: Q# で量子コンピューティングを学習する方法
description: 量子コンピューティングを開始する際に役立つ基本的な数学と物理学の知識のリソース。
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: article
uid: microsoft.quantum.overview.learn
ms.openlocfilehash: 17fc4e7a73f93a86d981996bf8b59309bccb6e67
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907751"
---
# <a name="how-to-learn-about-quantum-computing"></a>量子コンピューティングを学習する方法

量子コンピューティングの学習と、初めてのプログラムの作成に関するガイダンスを入手できます。 このガイドは完全ではありませんが、出発点として適しています。

## <a name="getting-started-overview"></a>概要

「[Microsoft Quantum Development Kit の概要](xref:microsoft.quantum.welcome)」では、Q# を用いた量子コンピューティングの概要が説明されています。これには、初めて Q# プログラムを作成するときのためのチュートリアル、使用開始ガイド、および量子プログラム開発のための Q# 量子ライブラリの概要が含まれます。

## <a name="learning-the-basics-what-do-you-need-to-know"></a>基本知識の学習: 知る必要があること

Q# や量子コンピューティングについて学習したり、量子アプリケーションの作成を開始したりするために、量子物理学の知識は必要ありません。

これらの概念から、量子プログラムのコーディングを開始するために必要になる基本的な知識を得ることができます。  

* [基本的な量子力学](xref:microsoft.quantum.concepts.intro):コーディングを開始するために量子物理学の知識は必要ないと言いました (これは本当です)。 しかし、量子力学とその数学表記に関する基本的な概念は、量子プログラミングの理解に役立ちます。

* **線形代数 (ベクトルと行列)** :量子コンピューティングでは、量子の状態がベクトルによって表されます。量子操作は、これらのベクトルに適用される線形変換となります。  こちらは[線形代数に関する Jupyter Notebook チュートリアル](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra)です。  線形代数については、[ベクトルと行列](xref:microsoft.quantum.concepts.vectors)に関する概念ガイドを参照してください。

* **複雑な算術演算**: 量子状態ベクトルの係数は複素数です。 これを使わなくてもいくつかの基本的な量子コンピューティングの概念を理解することはできますが、そう遠くないうちにこれを量子の道具箱に入れなければならなくなるでしょう。  この[複雑な算術計算についての Jupyter Notebook チュートリアル](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic)では、量子コンピューティングを使用するために必要な数学的な背景について説明されています。 

基本を理解できたので、最初の量子プログラムの記述方法の学習を開始する準備ができました。  学習を進めるには多くの方法があります。

## <a name="do-the-quantum-katas"></a>Quantum Katas を行う

[Quantum Katas](xref:microsoft.quantum.overview.katas) は、量子コンピューティングと Q # プログラミングの要素を同時に学習することを目的とした、マイペースで進められる一連のオープンソース チュートリアルです。  各 kata では、katas を正しく完了するために必要な量子コンピューティングの概念を学習するために使用できる追加の学習資料が参照されています。  

## <a name="dive-into-the-theory"></a>理論を深く学習する

量子力学と量子コンピューティングの理論について詳しく知りたい方もいるかもしれません。 その際に役に立つ資料の一覧を以下に示します。

* [量子コンピューティングの概念](xref:microsoft.quantum.concepts.intro)を説明しているガイドから始めます。これは、量子コンピューティングの基本的な概念をまとめたものです。
* _Learn Quantum Computing with Python and Q#_ (Sarah C. Kaiser および Christopher E. Granade) は、量子力学の経験がほとんどあるいはまったくないが、いくらかのプログラミングの知識はある方にとって絶好の入門書です。
* _Quantum Computation and Quantum Information_ (Michael A. Nielsen、Isaac L. Chuang) は、量子コンピューティングの分野で最もよく引用される教科書で、このテーマにおける標準的な教科書と見なされています。 この書籍は、量子力学とコンピューター サイエンスに関する最小限の経験を前提としています。 このテーマに関する綿密な導入を求めている方にとっても、高度な概念が書かれた参考書を探している方にとっても、絶好の選択肢となります。
* MIT OpenCourseWare は、Allan Adams による量子力学の基本を学ぶための優れた[オンライン コース](https://www.youtube.com/watch?v=lZ3bPUKo5zc&list=PLUl4u3cNGP61-9PEhRognw5vryrSEVLPr)を用意しています。 基礎となる物理現象を深く理解したい開発者に最適です。

## <a name="join-the-quantum-community"></a>量子コミュニティに参加する

これを単独で学ぶ必要はありません。アマチュアや専門家による大規模なコミュニティのサポートを受けることができます。 積極的に質問してみましょう。

* Q# または量子コンピューティングに関する質問がある場合は、Quantum Computing StackExchange サイトを調べてみてください。 同じような質問が見つからない場合は、いつでも新しく質問することができます。 
* Q# に関する最新のニュースとリソースについては、[Q# ブログ](https://devblogs.microsoft.com/qsharp/)と [Microsoft Quantum ブログ](https://cloudblogs.microsoft.com/quantum/)をご覧ください。
* [Q# コミュニティ](https://qsharp.community/)や [Awesome Q#](https://project-awesome.org/ebraminio/awesome-qsharp) を確認し、その他のリソースや資料を探します。

 量子コンピューティングについて学習したい場合は、[Microsoft Quantum Network](https://info.microsoft.com/LearnMoreAboutMicrosoftQuantumNetwork.html) がカリキュラムを知る参考になります。  

