---
uid: microsoft.quantum.welcome
title: Quantum Development Kit (QDK) の概要
description: Microsoft Quantum 開発キット (QDK) を使用して Q# で量子プロジェクトのプログラミングを開始する方法について説明します。
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: overview
ms.openlocfilehash: cea39e47ec5e7e2ad97adbbb39ba586274564967
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "77907632"
---
# <a name="get-started-with-the-quantum-development-kit-qdk"></a>Quantum Development Kit (QDK) の概要

Microsoft Quantum Development Kit にようこそ。  
QDK には、量子アプリケーション開発専用に設計されたプログラミング言語、Q# を使用して、独自の量子プログラムおよび実験を構築するために必要なあらゆるツールが含まれています。 

すぐに始めるには、[QDK インストール ガイド](xref:microsoft.quantum.install)を参照してください。
次に、Windows、Linux、または MacOS マシンに Quantum 開発キットをインストールして、独自の量子プログラムを作成するための手順が示されます。

コーディングを開始する準備ができておらず、量子コンピューティングと Q# の詳細を知りたい場合は、この記事を読んで、リソースを自由にお役立てください。 「[量子コンピューティングに関する 5 つの質問](#five-questions-about-quantum-computing)」セクションで、目的のリンクを見つけてください。

## <a name="get-started-programming"></a>プログラミングを開始する

Quantum 開発キットには、Q# を使用して量子プログラムを開発する方法を学習するためのさまざまな方法が用意されています。
量子の利用を開始するために、*クイックスタート*を試すことができます。

* この[量子乱数ジェネレーター](xref:microsoft.quantum.quickstarts.qrng)は "Q# Hello World" スタイルのアプリケーションであり、量子の概念を簡単に紹介し、量子アプリケーションを数分でビルドして実行できます。
* [Q# を使った量子の基本](xref:microsoft.quantum.write-program)に関するガイドでは、量子プログラミングの基本的な概念を示す Q# プログラムの記述について説明します。 
    コーディングを開始する準備ができていない場合でも、QDK をインストールせずに説明を読み進めることで、Q# プログラミング言語の概要と量子コンピューティングの最初の概念を理解することができます。
* [グローバーの検索アルゴリズム](xref:microsoft.quantum.quickstarts.search)では、Q# プログラムが Q# が持つ力からアイデアを得て、低レベルの量子操作を抽象化する方法で量子アルゴリズムを表す例を提供しています。 
    このクイックスタートでは、さまざまなプログラミング環境 (Python ホスト、.NET 言語ホスト、Visual Studio、Visual Studio Code) を使用してプログラムを開発する方法を学習できます。

### <a name="learning-further"></a>今後の学習
* Q# プログラミングの詳細については、[Quantum Katas](https://github.com/Microsoft/QuantumKatas) に関する説明をご覧ください。これは、Q# のプログラミング演習を通じて量子コンピューティングを紹介するマイペースで進められるプログラミング演習のコレクションです。
    これらの katas の多くは、Q# ノートブックとしても利用できます。 
* [サンプル リポジトリ](https://github.com/Microsoft/Quantum)では、Q# を使用して量子プログラムを作成する方法について複数の例を紹介しています。 これらのサンプルのほとんどは、オープンソースの[量子ライブラリ](https://github.com/Microsoft/QuantumLibraries)を使用して記述されています。これには、[標準](xref:microsoft.quantum.libraries.standard.intro)および[化学](xref:microsoft.quantum.chemistry.concepts.intro)ライブラリ (以下の詳細を参照) が含まれます。

## <a name="five-questions-about-quantum-computing"></a>量子コンピューティングに関する 5 つの質問

量子開発の初心者の場合、これは少し面倒であると感じるかと思います。 ここでは、量子コンピューティングの学習を開始する際に役立つリソースを用意しました。 これらの簡単な記事を参考にして、すぐにプログラミングを開始することをお勧めします。
* [量子コンピューティングとは](xref:microsoft.quantum.overview.what)
* [量子コンピューターでできること](xref:microsoft.quantum.overview.computers)
* [量子コンピューティングを学ぶ理由](xref:microsoft.quantum.overview.why)
* [Q# とは](xref:microsoft.quantum.overview.qsharp)
* [Q# で量子コンピューティングを学習する方法](xref:microsoft.quantum.overview.learn)

## <a name="quantum-development-kit-documentation"></a>Quantum Development Kit のドキュメント

現在のドキュメントには、次の追加のトピックが含まれています。

### <a name="using-q"></a>Q# の使用
* [量子開発手法](xref:microsoft.quantum.techniques.intro)では、Q# で量子プログラムを作成するために使用される主要な概念を紹介します。 トピックには、ファイル構造、操作と関数、量子ビットの使用、およびいくつかの高度なトピックがあります。
* [Q# 言語リファレンス](xref:microsoft.quantum.language.intro)では、型モデル、式、ステートメント、コンパイラの使用など、Q# 言語の詳細を説明します。
* [量子シミュレーターとホスト アプリケーション](xref:microsoft.quantum.machines)では、量子アルゴリズムがどのように実行されるか、どの量子コンピューターを使用できるか、および量子プログラム用に Q# 以外のドライバーを書き込む方法について説明します。

### <a name="q-libraries"></a>Q# ライブラリ
* [Q# 標準ライブラリ](xref:microsoft.quantum.libraries.standard.intro)では、従来の言語制御の要件と Q# 量子アルゴリズムの両方をサポートする操作と関数について説明します。 
    トピックには、制御フロー、データ構造、エラー修正、テスト、デバッグが含まれます。 
* [Q# 化学ライブラリ](xref:microsoft.quantum.chemistry.concepts.intro)では、量子化学シミュレーションをサポートする操作や関数について説明します。これは、量子コンピューティングの重要なアプリケーションです。 トピックには、ハミルトン力学や量子位相推定のシミュレーションなどが含まれます。
* [Q# 数値ライブラリ](xref:microsoft.quantum.numerics.intro)では、対象のコンピューターのネイティブ操作に関して複雑な算術関数の表現をサポートする操作と関数について説明します。
* [Q# ライブラリ リファレンス](xref:microsoft.quantum.standardlibsintro)には、名前空間別のライブラリ エンティティに関する参照情報が含まれています。

### <a name="general-quantum-computing"></a>一般的な量子コンピューティング
* [量子コンピューティングの概念](xref:microsoft.quantum.concepts.intro)では、量子コンピューティングへの線形代数の関連性、量子ビットの性質や使用法、量子回線の読み取り方法などのトピックを紹介します。
* [量子コンピューティング用語集](xref:microsoft.quantum.glossary)では、量子コンピューティングおよびプログラム開発に固有の重要な一部の用語を示します。 
    フィールドに慣れないお客様の場合、このドキュメントが手軽な参考資料として役立ちます。
* [関連項目](xref:microsoft.quantum.more-information)には、量子コンピューティングのトピックを詳しく解説する厳選された参考資料が含まれています。

### <a name="additional-info"></a>追加情報
* [Microsoft Quantum Development Kit のリリース ノート](xref:microsoft.quantum.relnotes)


## <a name="be-a-part-of-the-q-open-source-community"></a>Q# のオープンソース コミュニティに参加する
オープンソースの開発キットである Quantum 開発キットにより、開発者はすべての人の量子コンピューティングへのアクセスを容易にすることができるため、世界で最も切迫している課題の一部を解決できるようになります。  オープンソース ソフトウェアを必要とする教育機関は、その量子の学習と開発のために Q# をデプロイできます。 また、開発キットのオープンソース化により、開発者やドメインの専門家は、コードを使用して改善やアイデアを投稿する機会を得ることができます。

お客様のフィードバック、参加、および Quantum 開発キットへの貢献が重要です。  Quantum Development Kit ソースの詳細のほか、フィードバックの提供方法、決定に参加する方法、この増加している量子開発プラットフォームに貢献する方法については、「[Quantum Development Kit に貢献する](xref:microsoft.quantum.contributing)」を参照してください。

Microsoft の量子コンピューティング イニシアチブに関する一般情報が必要な場合は、[Microsoft クォンタム](https://www.microsoft.com/en-us/quantum/)に関する記事を参照してください。
