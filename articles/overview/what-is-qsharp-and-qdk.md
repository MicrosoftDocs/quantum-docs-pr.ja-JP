---
title: Q# プログラミング言語と QDK とは
description: Microsoft Quantum 開発キットと Q# プログラミング言語について、および量子プログラムの作成方法について説明します。
author: bradben
ms.author: v-benbra
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.q-sharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: 21adfcc1c5321d87665adb39a3c838bbda0b8861
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834569"
---
# <a name="what-are-the-no-locq-programming-language-and-qdk"></a>Q# プログラミング言語と QDK とは

Q# は、量子アルゴリズムを開発および実行するための Microsoft のオープンソース プログラミング言語です。 これは Quantum 開発キット (QDK) に含まれています。QDK には、[Q# ライブラリ](xref:microsoft.quantum.libraries)、[量子シミュレーター](xref:microsoft.quantum.machines)、[他のプログラミング環境用の拡張機能](xref:microsoft.quantum.install)、[API ドキュメント](xref:microsoft.quantum.apiref-intro)が含まれています。 QDK には、標準の Q# ライブラリに加えて、化学、機械学習、数値のライブラリも含まれています。

プログラミング言語としての Q# では、Python、C#、F# から一般的な要素を取り入れ、ループ、if/then ステートメント、共通データ型を使用してプログラムを作成するための基本的な手続き型のモデルをサポートします。 また、新しい量子固有のデータ構造と演算も導入されています。

## <a name="what-can-i-do-with-the-qdk"></a>QDK でできること

QDK は Q# 用のフル機能の開発キットであり、さまざまな環境で実行できる量子アプリケーションを開発するために、一般的なツールと言語で使用できます。 Q# プログラムは、コンソール アプリケーションとして Jupyter Notebook 経由で実行するか、または Python または .NET ホスト プログラムを使用することができます。

### <a name="develop-in-common-tools-and-environments"></a>一般的なツールと環境で開発する

量子開発を [Visual Studio、Visual Studio Code](xref:microsoft.quantum.install.standalone)、[Jupyter Notebook](xref:microsoft.quantum.install.jupyter) と統合します。 組み込みの API を使用して、プログラムを、ホスト言語である [Python](xref:microsoft.quantum.install.python) および [.NET](xref:microsoft.quantum.install.cs) と組み合わせます。

### <a name="try-quantum-operations-and-domain-specific-libraries"></a>量子演算と分野固有のライブラリを試す

重ね合わせ、もつれ、およびその他の量子演算を確認するために、量子アルゴリズムを記述してテストします。 Q# ライブラリを使用すると、低レベルの演算シーケンスを設計しなくても、複雑な量子演算を実行できます。

### <a name="run-programs-in-simulators"></a>シミュレーターでプログラムを実行する

全状態の量子シミュレーターや限定された範囲の Toffoli シミュレーターで量子プログラムを実行するか、さまざまなリソース エスティメーターで Q# コードをテストします。 

## <a name="where-can-i-learn-more"></a>詳細情報を得るには?

|||
| ---- | ---- |
| **量子コンピューティングが初めての場合** | [主要な概念](xref:microsoft.quantum.overview.understanding)に関するページで、量子物理学と量子コンピューティングの基礎を確認します。|
| **Q# 言語について深く理解したい場合** | 「[Q# ユーザー ガイド](xref:microsoft.quantum.guide)」で型、式、変数、量子プログラムの構造について確認します。|
| **量子プログラムの作成を始めたい場合** | [クイックスタート](xref:microsoft.quantum.install)で、Q# 環境を設定し、量子プログラムの作成を開始します。|

## <a name="how-does-no-locq-work"></a>Q# のしくみ

Q# プログラムは、スタンドアロン アプリケーションとしてコンパイルすることも、Python または .NET 言語で記述されたホスト プログラムによって呼び出すこともできます。

プログラムをコンパイルして実行すると、量子シミュレーターのインスタンスが作成され、それに Q# コードが渡されます。 シミュレーターでは、Q# コードを使用して量子ビット (量子粒子のシミュレーション) を作成し、変換を適用してその状態を変更します。 その後、シミュレーター内の量子演算の結果がプログラムに返されます。  

シミュレーター内で Q# コードを分離すると、アルゴリズムが量子物理学の法則に従うようになり、量子コンピューターで正しく実行できます。

![Qsharp コード フロー](~/media/qsharp-code-flow.png)

## <a name="how-do-i-use-the-qdk"></a>QDK の使用方法

Q# コンパイラ、Q# ライブラリ、量子シミュレーターなど、Q# プログラムの作成と実行に必要なものはすべて、ローカル コンピューターからインストールして実行できます。 最終的には、実際の量子コンピューターで Q# プログラムをリモートで実行できるようになりますが、それまでは、QDK で提供される量子シミュレーターによって正確で信頼性の高い結果が得られます。

- [Q# アプリケーション](xref:microsoft.quantum.install.standalone) の開発は、作業を開始するための最も簡単な方法です。

- スタンドアロンの [Jupyter Notebook を IQ#](xref:microsoft.quantum.install.jupyter) (Q# プログラムをコンパイル、シミュレート、視覚化するための Jupyter の拡張機能) で実行します。

- [Python](xref:microsoft.quantum.install.python) を使い慣れている場合は、開始時にこれをホスト プログラミング プラットフォームとして使用できます。 Python は、開発者の間だけでなく、科学者、研究者、教師にも広く使用されています。

- すでに [C#、F#、または VB.NET](xref:microsoft.quantum.install.cs) の使用経験があり、Visua Studio の開発環境に慣れている場合は、Q# への対応準備のために Visual Studio に追加する必要がある拡張機能はわずかです。  

## <a name="summary"></a>まとめ

Q# は、量子プログラムを開発するためのオープンソースのプログラミング言語です。 これは、複雑な量子演算を作成できるようにするライブラリと、プログラムを正確に実行してテストするための量子シミュレーターを備えています。 Q# プログラムは、スタンドアロン アプリとして実行することも、Python または .NET のホスト プログラムから呼び出すこともでき、ローカル コンピューターから作成、実行、およびテストできます。

## <a name="next-steps"></a>次の手順

[量子コンピューティングの線形代数](xref:microsoft.quantum.overview.algebra)
