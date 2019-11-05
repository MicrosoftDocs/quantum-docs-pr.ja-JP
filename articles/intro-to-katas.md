---
title: Quantum Katas の概要
description: Microsoft Quantum Development Kit (QDK) で提供される kata (トレーニング演習) について説明します。
author: natke
ms.author: nakersha
ms.date: 10/17/2019
ms.topic: overview
uid: microsoft.quantum.overview.katas
ms.openlocfilehash: 7fb8dba2a10f9a983ebee52e394260bbdc0d2f9c
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2019
ms.locfileid: "73444142"
---
# <a name="learn-quantum-computing-with-the-quantum-katas"></a>Quantum Katas を使用して量子コンピューティングを学習する

[Quantum Katas](https://github.com/Microsoft/QuantumKatas/) とは、量子コンピューティングと Q# プログラミングの要素を同時に学習することを目的とした、マイペースで進められるチュートリアルとプログラミング演習セットのオープンソース コレクションです。

## <a name="learning-by-doing"></a>実践的学習

このプロジェクトで収集したチュートリアルと katas では、非常にシンプルな内容から非常に難しい内容に移行していく特定のトピックを網羅したプログラミング タスクを用意し、これを実践して学習する方法にウェイトを置いています。 各タスクでは、何らかのコードを入力することが求められます。最初のタスクに必要なのは 1 行だけかもしれませんが、その後のタスクではかなりのコード フラグメントが必要になる場合があります。

最も重要な点として、katas には、タスクに対するソリューションを設定、実行、および検証するテスト フレームワークが含まれています。 これにより、ご自分のソリューションに関するフィードバックをすぐに得ることができ、間違っている場合にはご自分のアプローチを再検討することができます。

Katas を使用すれば任意の環境で学習することができます。

* Binder 環境内でオンラインになっている Jupyter Notebook
* ローカル コンピューターで実行されている Jupyter Notebook
* Visual Studio
* Visual Studio Code

## <a name="what-can-i-learn-with-the-quantum-katas"></a>Quantum Katas を使用して学習できることは何ですか?

Quantum Katas で取り上げられている主なトピックの概要を以下に示します。 量子コンピューティングの基本的な概念をしっかりと確実に把握するために、最初にこのラーニングパスに従うことをお勧めします。 もちろん、複雑な算術演算など、使い慣れたトピックをスキップし、好きな順序でアルゴリズムを学習することができます。

### <a name="introduction-to-quantum-computing-concepts"></a>量子コンピューティングの概念について

* [複雑な算術演算](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/ComplexArithmetic)
* [線形代数](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/LinearAlgebra)
* [量子ビットの概念](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/Qubit)
* [単一量子ビットの量子ゲート](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/SingleQubitGates)

### <a name="quantum-computing-fundamentals"></a>量子コンピューティングの基礎

* [量子ゲートの認識](https://github.com/microsoft/QuantumKatas/tree/master/BasicGates)
* [量子重ね合わせの作成](https://github.com/microsoft/QuantumKatas/tree/master/Superposition)
* [測定を使用した量子の状態の識別](https://github.com/microsoft/QuantumKatas/tree/master/Measurements)
* [共同測定](https://github.com/microsoft/QuantumKatas/tree/master/JointMeasurements)

### <a name="algorithms"></a>アルゴリズム

* [量子テレポーテーション](https://github.com/microsoft/QuantumKatas/tree/master/Teleportation)
* [超密度符号化](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)
* [Deutsch–Jozsa アルゴリズム](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/DeutschJozsaAlgorithm)
* [グローバーの検索アルゴリズムの実装](https://github.com/microsoft/QuantumKatas/tree/master/GroversAlgorithm)
* [グローバーの検索アルゴリズムの上位レベルのプロパティを探索](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/ExploringGroversAlgorithm)
* グローバーのアルゴリズムを使用した実際の問題の解決: [SAT の問題](https://github.com/microsoft/QuantumKatas/blob/master/SolveSATWithGrover)および[グラフの色分けの問題](https://github.com/microsoft/QuantumKatas/blob/master/GraphColoring)

### <a name="protocols-and-libraries"></a>プロトコルとライブラリ

* [量子キー配布用の BB84 プロトコル](https://github.com/microsoft/QuantumKatas/tree/master/KeyDistribution_BB84)
* 量子エラー訂正: [ビット反転エラー訂正コード](https://github.com/microsoft/QuantumKatas/tree/master/QEC_BitFlipCode)
* [位相推定](https://github.com/microsoft/QuantumKatas/blob/master/PhaseEstimation)
* 量子の算術: [リップルキャリー加算器](https://github.com/microsoft/QuantumKatas/blob/master/RippleCarryAdder)

### <a name="entanglement-games"></a>もつれゲーム

* [CHSH ゲーム](https://github.com/microsoft/QuantumKatas/blob/master/CHSHGame)
* [GHZ ゲーム](https://github.com/microsoft/QuantumKatas/blob/master/GHZGame)
* [Mermin-Peres 魔方陣ゲーム](https://github.com/microsoft/QuantumKatas/tree/master/MagicSquareGame)

## <a name="resources"></a>リソース

* [Quantum Katas](https://github.com/microsoft/QuantumKatas) の全シリーズを参照
* [kata のオンライン実行](https://aka.ms/try-quantum-katas)
