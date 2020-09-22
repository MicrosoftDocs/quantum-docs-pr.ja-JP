---
title: 量子機械学習パッケージの概要 | Microsoft Docs
description: 量子機械学習パッケージの概要
author: QuantumWriter
ms.author: alexeib
ms.date: 12/5/2019
ms.topic: article
uid: microsoft.quantum.machine-learning.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 321901a7976e4633a672495827c27c5f1645ad30
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835691"
---
# <a name="introduction-to-the-quantum-machine-learning-library"></a><span data-ttu-id="f54f2-103">Quantum Machine Learning Library の概要</span><span class="sxs-lookup"><span data-stu-id="f54f2-103">Introduction to the Quantum Machine Learning Library</span></span>

<span data-ttu-id="f54f2-104">Quantum Machine Learning Library は、Q# で記述された API であり、これを使用すると、量子/従来型のハイブリッド機械学習実験を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f54f2-104">The Quantum Machine Learning Library is an API, written in Q#, that gives you the ability to run hybrid quantum/classical machine learning experiments.</span></span> <span data-ttu-id="f54f2-105">このライブラリを使用すると、次のことが可能です。</span><span class="sxs-lookup"><span data-stu-id="f54f2-105">The library gives you the ability to:</span></span>

- <span data-ttu-id="f54f2-106">独自のデータを読み込んで、量子シミュレーターで分類する</span><span class="sxs-lookup"><span data-stu-id="f54f2-106">Load your own data to classify with quantum simulators</span></span>

- <span data-ttu-id="f54f2-107">サンプルとチュートリアルを使用して、量子機械学習の分野に慣れる</span><span class="sxs-lookup"><span data-stu-id="f54f2-107">Use samples and tutorials to get introduced to the field of quantum machine learning</span></span>

<span data-ttu-id="f54f2-108">現在の従来型の機械学習フレームワークと比較すると、パフォーマンスが低下する可能性があります (すべての処理が、既に計算コストが高い量子デバイスのシミュレーションの上で実行されていることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="f54f2-108">You can expect low performance compared to current classical machine learning frameworks (remember that everything is running on top of the simulation of a quantum device that is already computationally expensive).</span></span>

<span data-ttu-id="f54f2-109">このドキュメントの目的は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f54f2-109">The purpose of this documentation is:</span></span>

- <span data-ttu-id="f54f2-110">量子/従来型のハイブリッド学習のための機械学習ツール (Q\# で記述) を簡潔に紹介します。</span><span class="sxs-lookup"><span data-stu-id="f54f2-110">A concise introduction to machine learning tools (written in Q\#) for hybrid quantum/classical learning.</span></span>
- <span data-ttu-id="f54f2-111">機械学習の概念、具体的には、量子回路中心分類器 (量子逐次分類器としても知られる) での実現を紹介します。</span><span class="sxs-lookup"><span data-stu-id="f54f2-111">Introduce machine learning concepts and specifically their realization in quantum circuit centric classifiers (also known as quantum sequential classifiers).</span></span>
- <span data-ttu-id="f54f2-112">ライブラリで提供されるツールの使用を開始するための基礎に関するチュートリアル セットを提供します。</span><span class="sxs-lookup"><span data-stu-id="f54f2-112">Provide a set of tutorials on the basics to start using the tools provided by the library.</span></span>
- <span data-ttu-id="f54f2-113">そのような分類器のトレーニングと検証の方法、およびライブラリによって提供される特定の Q\# 操作へのそれらの変換方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f54f2-113">Discuss the training and validation methods for such classifiers and how they translate into specific Q\# operations provided by the library.</span></span>

<span data-ttu-id="f54f2-114">このライブラリで実装されているモデルは、[回路中心量子分類器](https://arxiv.org/abs/1804.00633)で提示された量子の従来型トレーニング スキームに基づいています</span><span class="sxs-lookup"><span data-stu-id="f54f2-114">The model implemented in this library is based on the quantum-classical training scheme presented in [Circuit-centric quantum classifiers](https://arxiv.org/abs/1804.00633)</span></span>
