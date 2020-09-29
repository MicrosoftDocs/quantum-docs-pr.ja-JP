---
title: 量子コンピューターと量子シミュレータ
description: 量子ハードウェア、量子シミュレーター、量子演算のしくみについて説明します。
author: bradben
ms.author: v-benbra
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.simulators
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8691838b2d6c54baa40042245eee8c901a7ca965
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835011"
---
# <a name="quantum-computers-and-quantum-simulators"></a><span data-ttu-id="ba1a7-103">量子コンピューターと量子シミュレータ</span><span class="sxs-lookup"><span data-stu-id="ba1a7-103">Quantum computers and quantum simulators</span></span>

<span data-ttu-id="ba1a7-104">量子コンピューターは依然として開発の初期段階にあります。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-104">Quantum computers are still in the infancy of their development.</span></span> <span data-ttu-id="ba1a7-105">ハードウェアとメンテナンスは高価であり、ほとんどのシステムは大学と研究所に置かれています。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-105">The hardware and maintenance are expensive, and most systems are located in universities and research labs.</span></span> <span data-ttu-id="ba1a7-106">ただし、テクノロジは進化していて、一部のシステムへの限定公開アクセスも可能になっています。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-106">The technology is advancing, though, and limited public access to some systems is available.</span></span>

<span data-ttu-id="ba1a7-107">量子シミュレーターは従来型コンピューターで実行されるソフトウェア プログラムであり、量子プログラムをある環境で実行して、さまざまな演算に量子ビットがどのように反応するかを予測するためのテストを行えるようにします。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-107">Quantum simulators are software programs that run on classical computers and make it possible to run and test quantum programs in an environment that predicts how qubits will react to different operations.</span></span>

## <a name="quantum-hardware"></a><span data-ttu-id="ba1a7-108">量子ハードウェア</span><span class="sxs-lookup"><span data-stu-id="ba1a7-108">Quantum hardware</span></span>

<span data-ttu-id="ba1a7-109">量子コンピューターは 3 つの主要部分 (量子ビットを格納する場所、シグナルを量子ビットに転送する手段、プログラムを実行して命令を送信するための従来型コンピューター) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-109">A quantum computer has three primary parts: an area that houses the qubits, a method for transferring signals to the qubits, and a classical computer to run a program and send instructions.</span></span>

- <span data-ttu-id="ba1a7-110">量子ビットに使用される量子マテリアルは壊れやすく、環境による干渉に非常に敏感です。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-110">The quantum material used for qubits is fragile and highly sensitive to environmental interferences.</span></span> <span data-ttu-id="ba1a7-111">量子ビットの格納方法の中には、量子ビットを収容するユニットが、コヒーレンスを最大にするために絶対零度をわずかに超える温度に保たれるものがあります。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-111">For some methods of qubit storage, the unit that houses the qubits is kept at a temperature just above absolute zero to maximize their coherence.</span></span> <span data-ttu-id="ba1a7-112">量子ビットの他の種類の格納場所では、振動を最小限に抑え、量子ビットを安定させるために真空槽が使用されています。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-112">Other types of qubit housing use a vacuum chamber to help minimize vibrations and stabilize the qubits.</span></span>  
- <span data-ttu-id="ba1a7-113">信号は、マイクロ波、レーザー、電圧などのさまざまな方法で量子ビットに送信できます。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-113">Signals can be sent to the qubits using a variety of methods including microwaves, laser, and voltage.</span></span>

<span data-ttu-id="ba1a7-114">量子コンピューターを正常に動作させるためには、多くの課題があります。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-114">Quantum computers face a multitude of challenges to operate correctly.</span></span> <span data-ttu-id="ba1a7-115">量子コンピューターでのエラー修正は重大な問題であり、スケールアップ (量子ビットの追加) によってエラーの発生率が増加します。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-115">Error correction in quantum computers is a significant issue, and scaling up (adding more qubits) increases the error rate.</span></span> <span data-ttu-id="ba1a7-116">こうした制限があるため、デスクトップ用の量子コンピューターの実用化にはまだ時間がかかりますが、研究所ベースの量子コンピューターはそれより近い将来に商業的に実用可能になります。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-116">Because of these limitations, a quantum PC for your desktop is far in the future, but a commercially-viable lab-based quantum computer is closer.</span></span>

## <a name="quantum-simulators"></a><span data-ttu-id="ba1a7-117">量子シミュレーター</span><span class="sxs-lookup"><span data-stu-id="ba1a7-117">Quantum simulators</span></span>

<span data-ttu-id="ba1a7-118">従来型コンピューターで実行される量子シミュレーターを使用すると、量子システムでの量子アルゴリズムの計算をシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-118">Quantum simulators that run on classical computers allow you to simulate the computation of quantum algorithms on a quantum system.</span></span>  <span data-ttu-id="ba1a7-119">Microsoft の Quantum 開発キット (QDK) には、全状態ベクトル シミュレーターが、他の特殊な量子シミュレーターとともに含まれています。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-119">Microsoft’s Quantum Development Kit (QDK) includes a full-state vector simulator along with other specialized quantum simulators.</span></span>

## <a name="topological-qubit"></a><span data-ttu-id="ba1a7-120">トポロジカル量子ビット</span><span class="sxs-lookup"><span data-stu-id="ba1a7-120">Topological qubit</span></span>

<span data-ttu-id="ba1a7-121">Microsoft では、トポロジカル量子ビットをベースに、量子コンピューターを開発しています。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-121">Microsoft is developing a quantum computer based on topological qubits.</span></span> <span data-ttu-id="ba1a7-122">トポロジカル量子ビットは環境変化の影響を受けづらいため、必要な外部エラー修正の度合いが少なくなります。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-122">A topological qubit will be less impacted by changes in its environment, therefore reducing the degree of external error correction required.</span></span>

<span data-ttu-id="ba1a7-123">トロポジカル量子ビットには高い安定性と環境ノイズに対する抵抗力が備わっているため、すぐにスケーリング可能でより長い期間にわたって高い信頼性を維持できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-123">Topological qubits feature increased stability and resistance to environmental noise, which means they can more readily scale and remain reliable longer.</span></span>

## <a name="microsoft-and-quantum-hardware-partnerships"></a><span data-ttu-id="ba1a7-124">Microsoft と量子ハードウェアのパートナー</span><span class="sxs-lookup"><span data-stu-id="ba1a7-124">Microsoft and quantum hardware partnerships</span></span>

<span data-ttu-id="ba1a7-125">開発者が量子コンピューターを将来利用できるように、Microsoft は、量子ハードウェア メーカー IonQ、Honeywell、QCI と提携しています。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-125">Microsoft is partnering with quantum hardware manufacturers IonQ, Honeywell, and QCI to make quantum computers accessible to developers in the future.</span></span> <span data-ttu-id="ba1a7-126">開発者は Azure Quantum プラットフォームを活用することで、Microsoft の Quantum 開発キット (QDK) と Q# を使用して、量子プログラムを作成し、リモートで実行できます。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-126">Leveraging the Azure Quantum platform, developers will be able to use Microsoft’s Quantum Development Kit (QDK) and Q# to write quantum programs and run them remotely.</span></span>

## <a name="quantum-computations"></a><span data-ttu-id="ba1a7-127">量子計算</span><span class="sxs-lookup"><span data-stu-id="ba1a7-127">Quantum computations</span></span>

<span data-ttu-id="ba1a7-128">量子コンピューターまたは量子シミュレーターで計算を実行する際の基本的なプロセスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-128">Performing computations on a quantum computer or quantum simulator follow a basic process:</span></span>

- <span data-ttu-id="ba1a7-129">量子ビットにアクセスする</span><span class="sxs-lookup"><span data-stu-id="ba1a7-129">Access the qubits</span></span>
- <span data-ttu-id="ba1a7-130">量子ビットを必要な状態に初期化する</span><span class="sxs-lookup"><span data-stu-id="ba1a7-130">Initialize the qubits to the desired state</span></span>
- <span data-ttu-id="ba1a7-131">量子ビットの状態を変換する演算を実行する</span><span class="sxs-lookup"><span data-stu-id="ba1a7-131">Perform operations to transform the states of the qubits</span></span>
- <span data-ttu-id="ba1a7-132">量子ビットの新しい状態を測定する</span><span class="sxs-lookup"><span data-stu-id="ba1a7-132">Measure the new states of the qubits</span></span>

<span data-ttu-id="ba1a7-133">量子ビットの初期化と変換は、**量子演算** (量子ゲートとも呼ばれる) を使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-133">Initializing and transforming qubits is done using **quantum operations** (sometimes called quantum gates).</span></span> <span data-ttu-id="ba1a7-134">量子演算は、AND、OR、NOT、XOR など、従来のコンピューティングの論理演算に似ています。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-134">Quantum operations are similar to logic operations in classical computing, such as AND, OR, NOT, and XOR.</span></span> <span data-ttu-id="ba1a7-135">演算には、量子ビットの状態を 1 から 0 に反転することや量子ビット ペアをもつれ状態にするといった基本的なものから、複数の演算を連続して使用して、重ね合わされた量子ビットがどちらかの方向に収縮する確率に影響を与えるものなどもあります。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-135">An operation can be as basic as flipping a qubit's state from 1 to 0 or entangling a pair of qubits, to using multiple operations in series to affect the probability of a superposed qubit collapsing one way or the other.</span></span>

> [!NOTE] 
> <span data-ttu-id="ba1a7-136">[Q# ライブラリ](xref:microsoft.quantum.libraries)には、低レベルの量子演算の複雑な組み合わせを定義する組み込みの演算が用意されています。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-136">The [Q# libraries](xref:microsoft.quantum.libraries) provide built-in operations that define complex combinations of lower-level quantum operations.</span></span> <span data-ttu-id="ba1a7-137">このライブラリの演算を使用することで、量子ビットを変換したり、より複雑なユーザー定義演算を作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-137">You can use the library operations to transform qubits and to create more complex user-defined operations.</span></span>  

<span data-ttu-id="ba1a7-138">計算の結果を測定すると答えが得られますが、一部の量子アルゴリズムでは、必ずしも正しい答えが得られるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-138">Measuring the result of the computation tells us an answer, but for some quantum algorithms, not necessarily the correct answer.</span></span> <span data-ttu-id="ba1a7-139">一部の量子アルゴリズムの結果は、量子演算によって構成された確率に基づいているため、これらの計算を複数回実行して確率分布を得ることで、結果の精度を向上させます。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-139">Because the result of some quantum algorithms is based on the probability that was configured by the quantum operations, these computations are run multiple times to get a probability distribution and refine the accuracy of the results.</span></span>  <span data-ttu-id="ba1a7-140">演算で正しい答えが返されたかどうかの確認は量子検証と呼ばれ、量子コンピューティングにおける重大な課題です。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-140">Assurance that an operation returned a correct answer is known as quantum verification and is a significant challenge in quantum computing.</span></span>

## <a name="summary"></a><span data-ttu-id="ba1a7-141">まとめ</span><span class="sxs-lookup"><span data-stu-id="ba1a7-141">Summary</span></span>

<span data-ttu-id="ba1a7-142">量子コンピューティングでは、従来のコンピューティングと同じ概念が一部共有されていますが、新しい傾向もいくつか加わっています。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-142">Quantum computing shares some of the same concepts as classical computing but adds a few new twists.</span></span> <span data-ttu-id="ba1a7-143">以下に重要な点を示します。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-143">Here are some key takeaways:</span></span>

- <span data-ttu-id="ba1a7-144">量子ハードウェアは高価で壊れやすいため、プログラムの作成とテストには量子シミュレーターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-144">Quantum hardware is expensive and fragile to work with, so quantum simulators are used to write and test programs.</span></span>
- <span data-ttu-id="ba1a7-145">従来型コンピューターと量子コンピューターではどちらも、論理演算 (ゲート) を使用して計算が準備されます。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-145">Both classical and quantum computers use logic operations (or gates) to prepare computations.</span></span>
- <span data-ttu-id="ba1a7-146">量子計算では確率が返されます。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-146">Quantum computations return probabilities.</span></span>

<span data-ttu-id="ba1a7-147">量子ハードウェアと手法の進歩によって、この分野が急速に変化しています。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-147">Advancements in quantum hardware and techniques is rapidly changing the field.</span></span> <span data-ttu-id="ba1a7-148">[現在開発されているもの](https://phys.org/search/?search=quantum+computer&s=0)をいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="ba1a7-148">Here are just a few of the [current developments](https://phys.org/search/?search=quantum+computer&s=0).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ba1a7-149">次のステップ</span><span class="sxs-lookup"><span data-stu-id="ba1a7-149">Next steps</span></span>

[<span data-ttu-id="ba1a7-150">Q# プログラミング言語と QDK とは</span><span class="sxs-lookup"><span data-stu-id="ba1a7-150">What are the Q# programming language and QDK?</span></span>](xref:microsoft.quantum.overview.q-sharp)
