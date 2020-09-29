---
uid: microsoft.quantum.welcome
title: Quantum Development Kit (QDK) の概要
description: Microsoft Quantum 開発キットを使用して Q# で量子プロジェクトのプログラミングを開始する方法について説明します。
author: bradben
ms.author: v-benbra
ms.date: 5/10/2020
ms.topic: overview
no-loc:
- Q#
- $$v
ms.openlocfilehash: e56b0e0455773481fbff6cfb7f4a6817cfc93d1a
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834501"
---
# <a name="get-started-with-the-quantum-development-kit-qdk"></a>Quantum Development Kit (QDK) の概要

Microsoft Quantum Development Kit にようこそ。  

Quantum 開発キット (QDK) には、量子アプリケーション開発専用に設計されたプログラミング言語である Q# を使用して、独自の量子プログラムおよび実験を構築するために必要なあらゆるツールが含まれています。

すぐに始めるには、まず [QDK 設定ガイド](xref:microsoft.quantum.install)を参照してください。
Windows、Linux、または MacOS を搭載したマシンに Quantum 開発キットを設定して、独自の量子プログラムを作成するための手順が示されます。

量子コンピューティングを初めて利用する場合は、「[概要](xref:microsoft.quantum.overview.introduction)」セクションを参照して、量子コンピューターで何が実行できのか、および量子コンピューティングの基礎を確認してください。

## <a name="get-started-programming"></a>プログラミングを開始する

Quantum 開発キットには、Q# を使用して量子プログラムを開発する方法を学習するためのさまざまな方法が用意されています。
量子の力の利用を開始する場合は、チュートリアルを試すことができます。

* [量子乱数ジェネレーター](xref:microsoft.quantum.quickstarts.qrng) - "Q# Hello World" スタイルのアプリケーションであり、量子の概念を簡単に紹介し、量子アプリケーションを数分でビルドして実行できます。
* [Q# でのもつれの確認](xref:microsoft.quantum.write-program) - このチュートリアルでは、量子プログラミングの基本的な概念を示す Q# プログラムの記述方法について説明します。 コーディングを開始する準備ができていない場合でも、QDK をインストールせずに説明を読み進めることで、Q# プログラミング言語の概要と量子コンピューティングの最初の概念を理解することができます。
* [グローバーの検索アルゴリズム](xref:microsoft.quantum.quickstarts.search) - この Q# プログラムの例では、低レベルの量子演算を抽象化する方法を探ることで、量子アルゴリズムを表すための Q# の能力を確認します。
    このチュートリアルでは、Visual Studio または Visual Studio Code を使用して、Q# アプリケーションとしてプログラムを開発する手順について説明します。

### <a name="learning-further"></a>今後の学習
* [量子コンピューティングの Microsoft Learn モジュール](https://docs.microsoft.com/learn/browse/?term=quantum)は、ご自身のペースとスケジュールで中核概念を習得できるように構成されています。 [最初のモジュール](https://docs.microsoft.com/learn/modules/qsharp-create-first-quantum-development-kit/)では、QDK で量子プログラムを作成する方法の基本を学習できます。
* Q# プログラミングの詳細については、[Quantum Katas](https://github.com/Microsoft/QuantumKatas) に関する説明をご覧ください。これは、Q# のプログラミング演習を通じて量子コンピューティングを紹介する、マイペースで進められるプログラミング演習のコレクションです。
    これらの katas の多くは、Q# ノートブックとしても利用できます。 
* [サンプル リポジトリ](https://github.com/Microsoft/Quantum)では、Q# を使用して量子プログラムを作成する方法について複数の例を紹介しています。 これらのサンプルのほとんどは、オープンソースの[量子ライブラリ](https://github.com/Microsoft/QuantumLibraries)を使用して記述されています。これには、[標準](xref:microsoft.quantum.libraries.standard.intro)および[化学](xref:microsoft.quantum.chemistry.concepts.intro)ライブラリ (以下の詳細を参照) が含まれます。

## <a name="key-concepts-for-quantum-computing"></a>量子コンピューティングの主要な概念

量子開発の初心者の場合、これは少し面倒であると感じるかと思います。 これらの主要な概念を参照することで、量子の世界に足を踏み入れる手助けとなり、量子コンピューティングが従来のコンピューティングとどのように違うかを理解できます。

* [量子コンピューティングについて](xref:microsoft.quantum.overview.understanding)
* [量子コンピューターと量子シミュレーター](xref:microsoft.quantum.overview.simulators)
* [Q# プログラミング言語と QDK とは](xref:microsoft.quantum.overview.q-sharp)
* [量子コンピューティングの線形代数](xref:microsoft.quantum.overview.algebra)

## <a name="quantum-development-kit-documentation"></a>Quantum Development Kit のドキュメント

現在のドキュメントには、次の追加のトピックが含まれています。

### <a name="no-locq-developer-guides"></a>Q# 開発者ガイド

* 「[Q# ユーザー ガイド](xref:microsoft.quantum.guide)」では、Q# で量子プログラムを作成するための中核概念について詳しく説明します。
* [量子シミュレーターとホスト アプリケーション](xref:microsoft.quantum.machines)では、量子アルゴリズムがどのように計算されるか、どの量子コンピューターを使用できるか、および量子プログラム用に Q# 以外のドライバーを作成する方法について説明します。

### <a name="no-locq-libraries"></a>Q# ライブラリ

* [Q# 標準ライブラリ](xref:microsoft.quantum.libraries.standard.intro)では、従来の言語制御の要件と Q# 量子アルゴリズムの両方をサポートする操作と関数について説明します。 
    トピックには、制御フロー、データ構造、エラー修正、テスト、デバッグが含まれます。 
* [Q# 化学ライブラリ](xref:microsoft.quantum.chemistry.concepts.intro)では、量子化学シミュレーションをサポートする操作や関数について説明します。これは、量子コンピューティングの重要な応用です。 トピックには、ハミルトン力学や量子位相推定のシミュレーションなどが含まれます。
* [Q# 数値ライブラリ](xref:microsoft.quantum.numerics.intro)では、対象のコンピューターのネイティブ操作に関して複雑な算術関数の表現をサポートする操作と関数について説明します。
* [Q# ライブラリ リファレンス](xref:microsoft.quantum.apiref-intro)には、名前空間別のライブラリ エンティティに関する参照情報が含まれています。

### <a name="general-quantum-computing"></a>一般的な量子コンピューティング

* [量子コンピューティングの概念](xref:microsoft.quantum.concepts.intro)では、量子コンピューティングへの線形代数の関連性、量子ビットの性質や使用法、量子回線の読み取り方法などのトピックを紹介します。
* [量子コンピューティング用語集](xref:microsoft.quantum.glossary)では、量子コンピューティングおよびプログラム開発に固有の重要な一部の用語を示します。
    フィールドに慣れないお客様の場合、このドキュメントが手軽な参考資料として役立ちます。
* [関連項目](xref:microsoft.quantum.more-information)には、量子コンピューティングのトピックを詳しく解説する厳選された参考資料が含まれています。

### <a name="additional-info"></a>追加情報

* [Microsoft Quantum Development Kit のリリース ノート](xref:microsoft.quantum.relnotes)


## <a name="be-a-part-of-the-no-locq-open-source-community"></a>Q# のオープンソース コミュニティに参加する

オープンソースの開発キットである Quantum 開発キットにより、開発者はすべての人の量子コンピューティングへのアクセスを容易にすることができるため、世界で最も切迫している課題の一部を解決できるようになります。  オープンソース ソフトウェアを必要とする教育機関は、その量子の学習と開発のために Q# をデプロイできます。 また、開発キットのオープンソース化により、開発者やドメインの専門家は、コードを使用して改善やアイデアを投稿する機会を得ることができます。

お客様のフィードバック、参加、および Quantum 開発キットへの貢献が重要です。  Quantum Development Kit ソースの詳細のほか、フィードバックの提供方法、決定に参加する方法、この増加している量子開発プラットフォームに貢献する方法については、「[Quantum Development Kit に貢献する](xref:microsoft.quantum.contributing)」を参照してください。

Microsoft の量子コンピューティング イニシアチブに関する一般情報が必要な場合は、[Microsoft クォンタム](https://www.microsoft.com/en-us/quantum/)に関する記事を参照してください。
