---
title: 量子機械学習パッケージの概要 | Microsoft Docs
description: 量子機械学習パッケージの概要
author: QuantumWriter
ms.author: alexeib
ms.date: 12/5/2019
ms.topic: conceptual
uid: microsoft.quantum.machine-learning.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1e36948a216a06d76b99cd451bbfac6f5defd7c8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858786"
---
# <a name="introduction-to-the-quantum-machine-learning-library"></a>Quantum Machine Learning Library の概要

Quantum Machine Learning Library は、Q# で記述された API であり、これを使用すると、量子/従来型のハイブリッド機械学習実験を実行できます。 このライブラリを使用すると、次のことが可能です。

- 独自のデータを読み込んで、量子シミュレーターで分類する

- サンプルとチュートリアルを使用して、量子機械学習の分野に慣れる

現在の従来型の機械学習フレームワークと比較すると、パフォーマンスが低下する可能性があります (すべての処理が、既に計算コストが高い量子デバイスのシミュレーションの上で実行されていることに注意してください)。

このドキュメントの目的は次のとおりです。

- 量子/従来型のハイブリッド学習のための機械学習ツール (Q\# で記述) を簡潔に紹介します。
- 機械学習の概念、具体的には、量子回路中心分類器 (量子逐次分類器としても知られる) での実現を紹介します。
- ライブラリで提供されるツールの使用を開始するための基礎に関するチュートリアル セットを提供します。
- そのような分類器のトレーニングと検証の方法、およびライブラリによって提供される特定の Q\# 操作へのそれらの変換方法について説明します。

このライブラリで実装されているモデルは、[回路中心量子分類器](https://arxiv.org/abs/1804.00633)で提示された量子の従来型トレーニング スキームに基づいています
