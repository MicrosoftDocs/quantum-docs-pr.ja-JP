---
title: Quantum Katas の概要
description: Microsoft Quantum Development Kit (QDK) で提供される kata (トレーニング演習) について説明します。
author: natke
ms.author: nakersha
ms.date: 10/17/2019
ms.topic: overview
uid: microsoft.quantum.overview.katas
ms.openlocfilehash: af54a2260147b8ca07919b241548aac85ed0d8a1
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "76821101"
---
# <a name="learn-quantum-computing-with-the-quantum-katas"></a><span data-ttu-id="099fa-103">Quantum Katas を使用して量子コンピューティングを学習する</span><span class="sxs-lookup"><span data-stu-id="099fa-103">Learn quantum computing with the Quantum Katas</span></span>

<span data-ttu-id="099fa-104">[Quantum Katas](https://github.com/Microsoft/QuantumKatas/) とは、量子コンピューティングと Q# プログラミングの要素を同時に学習することを目的とした、マイペースで進められるチュートリアルとプログラミング演習セットのオープンソース コレクションです。</span><span class="sxs-lookup"><span data-stu-id="099fa-104">[The Quantum Katas](https://github.com/Microsoft/QuantumKatas/) is an open-source collection of self-paced tutorials and sets of programming exercises aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span>

## <a name="learning-by-doing"></a><span data-ttu-id="099fa-105">実践的学習</span><span class="sxs-lookup"><span data-stu-id="099fa-105">Learning by Doing</span></span>

<span data-ttu-id="099fa-106">このプロジェクトで収集したチュートリアルと演習では、非常にシンプルな内容から非常に難しい内容に移行していく特定のトピックを網羅したプログラミング タスクを用意し、これを実践して学習する方法にウェイトを置いています。</span><span class="sxs-lookup"><span data-stu-id="099fa-106">The tutorials and exercises collected in this project emphasize learning by doing: they offer programming tasks that cover certain topics which progress from very simple to quite challenging.</span></span> <span data-ttu-id="099fa-107">各タスクでは、何らかのコードを入力することが求められます。最初のタスクに必要なのは 1 行だけかもしれませんが、その後のタスクではかなりのコード フラグメントが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="099fa-107">Each task asks you to fill in some code; the first tasks might require just one line, and the later ones might require a sizable fragment of code.</span></span>

<span data-ttu-id="099fa-108">最も重要な点として、katas には、タスクに対するソリューションを設定、実行、および検証するテスト フレームワークが含まれています。</span><span class="sxs-lookup"><span data-stu-id="099fa-108">Most importantly, the katas include testing frameworks that sets up, runs and validates the solutions to the tasks.</span></span> <span data-ttu-id="099fa-109">これにより、ご自分のソリューションに関するフィードバックをすぐに得ることができ、間違っている場合にはご自分のアプローチを再検討することができます。</span><span class="sxs-lookup"><span data-stu-id="099fa-109">This allows you to get immediate feedback on your solution and to reconsider your approach if it is incorrect.</span></span>

<span data-ttu-id="099fa-110">Katas を使用すれば任意の環境で学習することができます。</span><span class="sxs-lookup"><span data-stu-id="099fa-110">You can use the Katas for learning in your environment of choice:</span></span>

* <span data-ttu-id="099fa-111">Binder 環境内でオンラインになっている Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="099fa-111">Jupyter Notebooks online within the Binder environment</span></span>
* <span data-ttu-id="099fa-112">ローカル コンピューターで実行されている Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="099fa-112">Jupyter Notebooks running on your local machine</span></span>
* <span data-ttu-id="099fa-113">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="099fa-113">Visual Studio</span></span>
* <span data-ttu-id="099fa-114">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="099fa-114">Visual Studio Code</span></span>

## <a name="what-can-i-learn-with-the-quantum-katas"></a><span data-ttu-id="099fa-115">Quantum Katas を使用して学習できることは何ですか?</span><span class="sxs-lookup"><span data-stu-id="099fa-115">What can I learn with the Quantum Katas?</span></span>

<span data-ttu-id="099fa-116">Quantum Katas で取り上げられている主なトピックの概要を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="099fa-116">Here is a summary of the main topics covered in the Quantum Katas.</span></span> <span data-ttu-id="099fa-117">量子コンピューティングの基本的な概念をしっかりと確実に把握するために、最初にこのラーニングパスに従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="099fa-117">We recommend you to follow this learning path in the beginning to make sure you have a solid grasp on the fundamental concepts of quantum computing.</span></span> <span data-ttu-id="099fa-118">もちろん、複雑な算術演算など、使い慣れたトピックをスキップし、好きな順序でアルゴリズムを学習することができます。</span><span class="sxs-lookup"><span data-stu-id="099fa-118">Of course, you can skip the topics you're comfortable with, such as complex arithmetic, and learn the algorithms in any order you want.</span></span>

### <a name="introduction-to-quantum-computing-concepts"></a><span data-ttu-id="099fa-119">量子コンピューティングの概念について</span><span class="sxs-lookup"><span data-stu-id="099fa-119">Introduction to quantum computing concepts</span></span>

* [<span data-ttu-id="099fa-120">複雑な算術演算</span><span class="sxs-lookup"><span data-stu-id="099fa-120">Complex arithmetic</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic)
* [<span data-ttu-id="099fa-121">線形代数</span><span class="sxs-lookup"><span data-stu-id="099fa-121">Linear algebra</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra)
* [<span data-ttu-id="099fa-122">量子ビットの概念</span><span class="sxs-lookup"><span data-stu-id="099fa-122">The concept of a qubit</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/Qubit)
* [<span data-ttu-id="099fa-123">単一量子ビットの量子ゲート</span><span class="sxs-lookup"><span data-stu-id="099fa-123">Single-qubit quantum gates</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/SingleQubitGates)
* [<span data-ttu-id="099fa-124">マルチ量子システム</span><span class="sxs-lookup"><span data-stu-id="099fa-124">Multi-qubit systems</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/MultiQubitSystems)
* [<span data-ttu-id="099fa-125">マルチ量子ゲート</span><span class="sxs-lookup"><span data-stu-id="099fa-125">Multi-qubit gates</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/MultiQubitGates)

### <a name="quantum-computing-fundamentals"></a><span data-ttu-id="099fa-126">量子コンピューティングの基礎</span><span class="sxs-lookup"><span data-stu-id="099fa-126">Quantum computing fundamentals</span></span>

* [<span data-ttu-id="099fa-127">量子ゲートの認識</span><span class="sxs-lookup"><span data-stu-id="099fa-127">Recognizing quantum gates</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/BasicGates)
* [<span data-ttu-id="099fa-128">量子重ね合わせの作成</span><span class="sxs-lookup"><span data-stu-id="099fa-128">Creating quantum superposition</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/Superposition)
* [<span data-ttu-id="099fa-129">測定を使用した量子の状態の識別</span><span class="sxs-lookup"><span data-stu-id="099fa-129">Distinguishing quantum states using measurements</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/Measurements)
* [<span data-ttu-id="099fa-130">共同測定</span><span class="sxs-lookup"><span data-stu-id="099fa-130">Joint measurements</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/JointMeasurements)

### <a name="algorithms"></a><span data-ttu-id="099fa-131">アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="099fa-131">Algorithms</span></span>

* [<span data-ttu-id="099fa-132">量子テレポーテーション</span><span class="sxs-lookup"><span data-stu-id="099fa-132">Quantum teleportation</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/Teleportation)
* [<span data-ttu-id="099fa-133">超密度符号化</span><span class="sxs-lookup"><span data-stu-id="099fa-133">Superdense coding</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)
* [<span data-ttu-id="099fa-134">Deutsch–Jozsa アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="099fa-134">Deutsch–Jozsa algorithm</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ExploringDeutschJozsaAlgorithm)
* [<span data-ttu-id="099fa-135">グローバーの検索アルゴリズムの実装</span><span class="sxs-lookup"><span data-stu-id="099fa-135">Implementing Grover's search algorithm</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/GroversAlgorithm)
* [<span data-ttu-id="099fa-136">グローバーの検索アルゴリズムの上位レベルのプロパティを探索</span><span class="sxs-lookup"><span data-stu-id="099fa-136">Exploring high-level properties of Grover's search algorithm</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ExploringGroversAlgorithm)
* <span data-ttu-id="099fa-137">グローバーのアルゴリズムを使用した実際の問題の解決: [SAT の問題](https://github.com/microsoft/QuantumKatas/tree/master/SolveSATWithGrover)および[グラフの色分けの問題](https://github.com/microsoft/QuantumKatas/tree/master/GraphColoring)</span><span class="sxs-lookup"><span data-stu-id="099fa-137">Solving real problems using Grover's algorithm: [SAT problems](https://github.com/microsoft/QuantumKatas/tree/master/SolveSATWithGrover) and [graph coloring problems](https://github.com/microsoft/QuantumKatas/tree/master/GraphColoring)</span></span>

### <a name="protocols-and-libraries"></a><span data-ttu-id="099fa-138">プロトコルとライブラリ</span><span class="sxs-lookup"><span data-stu-id="099fa-138">Protocols and libraries</span></span>

* [<span data-ttu-id="099fa-139">量子キー配布用の BB84 プロトコル</span><span class="sxs-lookup"><span data-stu-id="099fa-139">BB84 protocol for quantum key distribution</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/KeyDistribution_BB84)
* <span data-ttu-id="099fa-140">量子エラー訂正: [ビット反転エラー訂正コード](https://github.com/microsoft/QuantumKatas/tree/master/QEC_BitFlipCode)</span><span class="sxs-lookup"><span data-stu-id="099fa-140">Quantum error correction: [bit-flip error correcting code](https://github.com/microsoft/QuantumKatas/tree/master/QEC_BitFlipCode)</span></span>
* [<span data-ttu-id="099fa-141">位相推定</span><span class="sxs-lookup"><span data-stu-id="099fa-141">Phase estimation</span></span>](https://github.com/microsoft/QuantumKatas/blob/master/PhaseEstimation)
* <span data-ttu-id="099fa-142">量子の算術: [リップルキャリー加算器](https://github.com/microsoft/QuantumKatas/blob/master/RippleCarryAdder)</span><span class="sxs-lookup"><span data-stu-id="099fa-142">Quantum arithmetic: [building ripple-carry adders](https://github.com/microsoft/QuantumKatas/blob/master/RippleCarryAdder)</span></span>

### <a name="entanglement-games"></a><span data-ttu-id="099fa-143">もつれゲーム</span><span class="sxs-lookup"><span data-stu-id="099fa-143">Entanglement games</span></span>

* [<span data-ttu-id="099fa-144">CHSH ゲーム</span><span class="sxs-lookup"><span data-stu-id="099fa-144">CHSH game</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/CHSHGame)
* [<span data-ttu-id="099fa-145">GHZ ゲーム</span><span class="sxs-lookup"><span data-stu-id="099fa-145">GHZ game</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/GHZGame)
* [<span data-ttu-id="099fa-146">Mermin-Peres 魔方陣ゲーム</span><span class="sxs-lookup"><span data-stu-id="099fa-146">Mermin-Peres magic square game</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/MagicSquareGame)

## <a name="resources"></a><span data-ttu-id="099fa-147">リソース</span><span class="sxs-lookup"><span data-stu-id="099fa-147">Resources</span></span>

* <span data-ttu-id="099fa-148">[Quantum Katas](https://github.com/microsoft/QuantumKatas) の全シリーズを参照</span><span class="sxs-lookup"><span data-stu-id="099fa-148">See the full series of [Quantum Katas](https://github.com/microsoft/QuantumKatas)</span></span>
* [<span data-ttu-id="099fa-149">kata のオンライン実行</span><span class="sxs-lookup"><span data-stu-id="099fa-149">Run the katas online</span></span>](https://aka.ms/try-quantum-katas)
