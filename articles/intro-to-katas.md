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
# <a name="learn-quantum-computing-with-the-quantum-katas"></a><span data-ttu-id="373f8-103">Quantum Katas を使用して量子コンピューティングを学習する</span><span class="sxs-lookup"><span data-stu-id="373f8-103">Learn quantum computing with the Quantum Katas</span></span>

<span data-ttu-id="373f8-104">[Quantum Katas](https://github.com/Microsoft/QuantumKatas/) とは、量子コンピューティングと Q# プログラミングの要素を同時に学習することを目的とした、マイペースで進められるチュートリアルとプログラミング演習セットのオープンソース コレクションです。</span><span class="sxs-lookup"><span data-stu-id="373f8-104">[The Quantum Katas](https://github.com/Microsoft/QuantumKatas/) is an open-source collection of self-paced tutorials and sets of programming exercises aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span>

## <a name="learning-by-doing"></a><span data-ttu-id="373f8-105">実践的学習</span><span class="sxs-lookup"><span data-stu-id="373f8-105">Learning by Doing</span></span>

<span data-ttu-id="373f8-106">このプロジェクトで収集したチュートリアルと katas では、非常にシンプルな内容から非常に難しい内容に移行していく特定のトピックを網羅したプログラミング タスクを用意し、これを実践して学習する方法にウェイトを置いています。</span><span class="sxs-lookup"><span data-stu-id="373f8-106">The tutorials and katas collected in this project emphasize learning by doing: they offer programming tasks that cover certain topics which progress from very simple to quite challenging.</span></span> <span data-ttu-id="373f8-107">各タスクでは、何らかのコードを入力することが求められます。最初のタスクに必要なのは 1 行だけかもしれませんが、その後のタスクではかなりのコード フラグメントが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="373f8-107">Each task asks you to fill in some code; the first tasks might require just one line, and the later ones might require a sizable fragment of code.</span></span>

<span data-ttu-id="373f8-108">最も重要な点として、katas には、タスクに対するソリューションを設定、実行、および検証するテスト フレームワークが含まれています。</span><span class="sxs-lookup"><span data-stu-id="373f8-108">Most importantly, the katas include testing frameworks that sets up, runs and validates the solutions to the tasks.</span></span> <span data-ttu-id="373f8-109">これにより、ご自分のソリューションに関するフィードバックをすぐに得ることができ、間違っている場合にはご自分のアプローチを再検討することができます。</span><span class="sxs-lookup"><span data-stu-id="373f8-109">This allows you to get immediate feedback on your solution and to reconsider your approach if it is incorrect.</span></span>

<span data-ttu-id="373f8-110">Katas を使用すれば任意の環境で学習することができます。</span><span class="sxs-lookup"><span data-stu-id="373f8-110">You can use the Katas for learning in your environment of choice:</span></span>

* <span data-ttu-id="373f8-111">Binder 環境内でオンラインになっている Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="373f8-111">Jupyter Notebooks online within the Binder environment</span></span>
* <span data-ttu-id="373f8-112">ローカル コンピューターで実行されている Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="373f8-112">Jupyter Notebooks running on your local machine</span></span>
* <span data-ttu-id="373f8-113">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="373f8-113">Visual Studio</span></span>
* <span data-ttu-id="373f8-114">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="373f8-114">Visual Studio Code</span></span>

## <a name="what-can-i-learn-with-the-quantum-katas"></a><span data-ttu-id="373f8-115">Quantum Katas を使用して学習できることは何ですか?</span><span class="sxs-lookup"><span data-stu-id="373f8-115">What can I learn with the Quantum Katas?</span></span>

<span data-ttu-id="373f8-116">Quantum Katas で取り上げられている主なトピックの概要を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="373f8-116">Here is a summary of the main topics covered in the Quantum Katas.</span></span> <span data-ttu-id="373f8-117">量子コンピューティングの基本的な概念をしっかりと確実に把握するために、最初にこのラーニングパスに従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="373f8-117">We recommend you to follow this learning path in the beginning to make sure you have a solid grasp on the fundamental concepts of quantum computing.</span></span> <span data-ttu-id="373f8-118">もちろん、複雑な算術演算など、使い慣れたトピックをスキップし、好きな順序でアルゴリズムを学習することができます。</span><span class="sxs-lookup"><span data-stu-id="373f8-118">Of course, you can skip the topics you're comfortable with, such as complex arithmetic, and learn the algorithms in any order you want.</span></span>

### <a name="introduction-to-quantum-computing-concepts"></a><span data-ttu-id="373f8-119">量子コンピューティングの概念について</span><span class="sxs-lookup"><span data-stu-id="373f8-119">Introduction to quantum computing concepts</span></span>

* [<span data-ttu-id="373f8-120">複雑な算術演算</span><span class="sxs-lookup"><span data-stu-id="373f8-120">Complex arithmetic</span></span>](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/ComplexArithmetic)
* [<span data-ttu-id="373f8-121">線形代数</span><span class="sxs-lookup"><span data-stu-id="373f8-121">Linear algebra</span></span>](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/LinearAlgebra)
* [<span data-ttu-id="373f8-122">量子ビットの概念</span><span class="sxs-lookup"><span data-stu-id="373f8-122">The concept of a qubit</span></span>](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/Qubit)
* [<span data-ttu-id="373f8-123">単一量子ビットの量子ゲート</span><span class="sxs-lookup"><span data-stu-id="373f8-123">Single-qubit quantum gates</span></span>](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/SingleQubitGates)

### <a name="quantum-computing-fundamentals"></a><span data-ttu-id="373f8-124">量子コンピューティングの基礎</span><span class="sxs-lookup"><span data-stu-id="373f8-124">Quantum computing fundamentals</span></span>

* [<span data-ttu-id="373f8-125">量子ゲートの認識</span><span class="sxs-lookup"><span data-stu-id="373f8-125">Recognizing quantum gates</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/BasicGates)
* [<span data-ttu-id="373f8-126">量子重ね合わせの作成</span><span class="sxs-lookup"><span data-stu-id="373f8-126">Creating quantum superposition</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/Superposition)
* [<span data-ttu-id="373f8-127">測定を使用した量子の状態の識別</span><span class="sxs-lookup"><span data-stu-id="373f8-127">Distinguishing quantum states using measurements</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/Measurements)
* [<span data-ttu-id="373f8-128">共同測定</span><span class="sxs-lookup"><span data-stu-id="373f8-128">Joint measurements</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/JointMeasurements)

### <a name="algorithms"></a><span data-ttu-id="373f8-129">アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="373f8-129">Algorithms</span></span>

* [<span data-ttu-id="373f8-130">量子テレポーテーション</span><span class="sxs-lookup"><span data-stu-id="373f8-130">Quantum teleportation</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/Teleportation)
* [<span data-ttu-id="373f8-131">超密度符号化</span><span class="sxs-lookup"><span data-stu-id="373f8-131">Superdense coding</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)
* [<span data-ttu-id="373f8-132">Deutsch–Jozsa アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="373f8-132">Deutsch–Jozsa algorithm</span></span>](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/DeutschJozsaAlgorithm)
* [<span data-ttu-id="373f8-133">グローバーの検索アルゴリズムの実装</span><span class="sxs-lookup"><span data-stu-id="373f8-133">Implementing Grover's search algorithm</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/GroversAlgorithm)
* [<span data-ttu-id="373f8-134">グローバーの検索アルゴリズムの上位レベルのプロパティを探索</span><span class="sxs-lookup"><span data-stu-id="373f8-134">Exploring high-level properties of Grover's search algorithm</span></span>](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/ExploringGroversAlgorithm)
* <span data-ttu-id="373f8-135">グローバーのアルゴリズムを使用した実際の問題の解決: [SAT の問題](https://github.com/microsoft/QuantumKatas/blob/master/SolveSATWithGrover)および[グラフの色分けの問題](https://github.com/microsoft/QuantumKatas/blob/master/GraphColoring)</span><span class="sxs-lookup"><span data-stu-id="373f8-135">Solving real problems using Grover's algorithm: [SAT problems](https://github.com/microsoft/QuantumKatas/blob/master/SolveSATWithGrover) and [graph coloring problems](https://github.com/microsoft/QuantumKatas/blob/master/GraphColoring)</span></span>

### <a name="protocols-and-libraries"></a><span data-ttu-id="373f8-136">プロトコルとライブラリ</span><span class="sxs-lookup"><span data-stu-id="373f8-136">Protocols and libraries</span></span>

* [<span data-ttu-id="373f8-137">量子キー配布用の BB84 プロトコル</span><span class="sxs-lookup"><span data-stu-id="373f8-137">BB84 protocol for quantum key distribution</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/KeyDistribution_BB84)
* <span data-ttu-id="373f8-138">量子エラー訂正: [ビット反転エラー訂正コード](https://github.com/microsoft/QuantumKatas/tree/master/QEC_BitFlipCode)</span><span class="sxs-lookup"><span data-stu-id="373f8-138">Quantum error correction: [bit-flip error correcting code](https://github.com/microsoft/QuantumKatas/tree/master/QEC_BitFlipCode)</span></span>
* [<span data-ttu-id="373f8-139">位相推定</span><span class="sxs-lookup"><span data-stu-id="373f8-139">Phase estimation</span></span>](https://github.com/microsoft/QuantumKatas/blob/master/PhaseEstimation)
* <span data-ttu-id="373f8-140">量子の算術: [リップルキャリー加算器](https://github.com/microsoft/QuantumKatas/blob/master/RippleCarryAdder)</span><span class="sxs-lookup"><span data-stu-id="373f8-140">Quantum arithmetic: [building ripple-carry adders](https://github.com/microsoft/QuantumKatas/blob/master/RippleCarryAdder)</span></span>

### <a name="entanglement-games"></a><span data-ttu-id="373f8-141">もつれゲーム</span><span class="sxs-lookup"><span data-stu-id="373f8-141">Entanglement games</span></span>

* [<span data-ttu-id="373f8-142">CHSH ゲーム</span><span class="sxs-lookup"><span data-stu-id="373f8-142">CHSH game</span></span>](https://github.com/microsoft/QuantumKatas/blob/master/CHSHGame)
* [<span data-ttu-id="373f8-143">GHZ ゲーム</span><span class="sxs-lookup"><span data-stu-id="373f8-143">GHZ game</span></span>](https://github.com/microsoft/QuantumKatas/blob/master/GHZGame)
* [<span data-ttu-id="373f8-144">Mermin-Peres 魔方陣ゲーム</span><span class="sxs-lookup"><span data-stu-id="373f8-144">Mermin-Peres magic square game</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/MagicSquareGame)

## <a name="resources"></a><span data-ttu-id="373f8-145">リソース</span><span class="sxs-lookup"><span data-stu-id="373f8-145">Resources</span></span>

* <span data-ttu-id="373f8-146">[Quantum Katas](https://github.com/microsoft/QuantumKatas) の全シリーズを参照</span><span class="sxs-lookup"><span data-stu-id="373f8-146">See the full series of [Quantum Katas](https://github.com/microsoft/QuantumKatas)</span></span>
* [<span data-ttu-id="373f8-147">kata のオンライン実行</span><span class="sxs-lookup"><span data-stu-id="373f8-147">Run the katas online</span></span>](https://aka.ms/try-quantum-katas)
