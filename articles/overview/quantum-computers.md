---
title: 量子コンピューターでできること
description: 新しい量子アルゴリズムから、従来のコンピューター上で実行される量子から着想を得たアルゴリズムまで、量子コンピューティングの影響について説明します。
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: article
uid: microsoft.quantum.overview.computers
ms.openlocfilehash: 9d8ba90a504f298f9465ebf564c43625a4d43168
ms.sourcegitcommit: edcf15044d7bdf4f8b21fb8f6af4bde475eb13a0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2019
ms.locfileid: "73529949"
---
# <a name="what-can-a-quantum-computer-do"></a><span data-ttu-id="1e6e3-103">量子コンピューターでできること</span><span class="sxs-lookup"><span data-stu-id="1e6e3-103">What can a quantum computer do?</span></span>

<span data-ttu-id="1e6e3-104">従来のコンピューターでは実行できない、量子コンピューターで実行できること</span><span class="sxs-lookup"><span data-stu-id="1e6e3-104">What can we do with a quantum computer that can't be done with a classical one?</span></span>

<span data-ttu-id="1e6e3-105">世界中の最も困難ないくつかの問題を解決します。ここでは、現在のコンピューターでは数十億年かかるところ、量子コンピューターでは数日、数時間、あるいは数分で解決策が見つかります。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-105">To solve some of the world's most challenging problems, where finding a solution would take current computers billions of years, a quantum computer could do so in days, hours, or even minutes.</span></span>

<span data-ttu-id="1e6e3-106">量子コンピューティングにより、研究者は、新しい触媒や材料の開発、医薬の向上、人工知能の進歩の加速を実現し、宇宙の起源に関する根本的な質問に解答することができます。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-106">Quantum computing will enable researchers to develop new catalysts and materials, improve medicines, accelerate advances in artificial intelligence, and answer fundamental questions about the origins of our universe.</span></span>

## <a name="quantum-simulation"></a><span data-ttu-id="1e6e3-107">量子シミュレーション</span><span class="sxs-lookup"><span data-stu-id="1e6e3-107">Quantum simulation</span></span>

<span data-ttu-id="1e6e3-108">量子プログラムを使用して量子システム自体をモデル化することには、さまざまな業界でイノベーションにつながる分析情報を解き明かす大きな可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-108">Using quantum programs to model quantum systems themselves has vast potential for unlocking insights leading to innovations across many industries.</span></span> <span data-ttu-id="1e6e3-109">量子プログラムを使用してシミュレーションを実行できる量子システムの例として、光合成、超伝導、複合分子が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-109">Photosynthesis, superconductors, and complex molecules are examples of quantum systems that can be simulated using quantum programs.</span></span>

<span data-ttu-id="1e6e3-110">量子力学の法則に従って動作する微細なシステムのシミュレーションは、計算コストが高くなります。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-110">Simulating microscopic systems that behave according to the laws of quantum mechanics is computationally expensive.</span></span> <span data-ttu-id="1e6e3-111">重ね合わせで起こりうるすべての状態と、システムのサイズにより指数関数的に増加する状態の数を考慮する必要があります</span><span class="sxs-lookup"><span data-stu-id="1e6e3-111">We need to take into account all the possible states that can be in superposition and the number of states grows exponentially with the size of the system.</span></span> <span data-ttu-id="1e6e3-112">量子コンピューターでは、システムのすべての状態をモデル化する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-112">In a quantum computer, we don’t need to model all of the states of the system.</span></span> <span data-ttu-id="1e6e3-113">代わりに、コンピューター自体の量子ビットで、シミュレートしたいシステムの量子状態を埋め込み、量子ゲートの特定のセットによりシミュレーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-113">Instead, we embed the quantum state of the system that we want to simulate in the qubits of the computer itself, and run the simulation with a specific set of quantum gates.</span></span> <span data-ttu-id="1e6e3-114">つまり、量子コンピューターを使用して、量子システムをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-114">In other words, we use a quantum computer to simulate a quantum system.</span></span>

<span data-ttu-id="1e6e3-115">化学分子は量子システムであるため、この方法で分析できます。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-115">Chemical molecules are quantum systems and therefore can be analyzed in this way.</span></span> <span data-ttu-id="1e6e3-116">このような特定の化学に "_ニトロゲナーゼ_" 酵素があります。その性質を深く理解すると、これには、現在の肥料によるエネルギー消費と温室効果ガスの排出を削減できる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-116">One such specific chemical is the _nitrogenase_ enzyme, which, with a better understanding of its properties, could have the potential to reduce the energy consumption and greenhouse gas emission of current fertilizers.</span></span>

## <a name="cryptography"></a><span data-ttu-id="1e6e3-117">暗号化</span><span class="sxs-lookup"><span data-stu-id="1e6e3-117">Cryptography</span></span>

<span data-ttu-id="1e6e3-118">量子コンピューターの応用で最も有名なものはおそらく暗号化です。1994 年に Peter Shor が、広く利用されているあらゆる暗号化手法をスケーラブルな量子コンピューターで破れることを見せました。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-118">Perhaps the most famous application of quantum computers is in cryptography, where Peter Shor showed in 1994 that a scalable quantum computer can break every widely used encryption technique.</span></span>  <span data-ttu-id="1e6e3-119">古典的な暗号化手法は、大きな数を 2 つの素数に因数分解するなど、大きな数に対する演算の至難性に依存します。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-119">Classical cryptography relies on the intractability of operations on large numbers, such as factorization of large numbers into two prime numbers.</span></span>

<span data-ttu-id="1e6e3-120">量子コンピューティングでは (Shor のアルゴリズムにより) このような演算が理論的に扱えるようになります。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-120">Quantum computing makes these operations theoretically tractable (via Shor's algorithm).</span></span> <span data-ttu-id="1e6e3-121">このアルゴリズムの実装は量子ハードウェアの現在のスケールでは物理的に不可能である一方で、データ セキュリティを将来も使い続けるための抗量子アルゴリズムの開発を引き起こしました (暗号化や暗号化キー配布用の新しい量子アルゴリズムを含む)。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-121">Whilst implementation of this algorithm is not physically possible with the current scale of quantum hardware, it has spawned development of quantum-resistant algorithms to future-proof data security, including novel quantum algorithms for encryption and cryptographic key distribution.</span></span>

<span data-ttu-id="1e6e3-122">Microsoft には、ポスト量子暗号とセキュリティを上げる量子耐性アルゴリズムで世界をリードするチームがあります。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-122">Here at Microsoft, we have the world's leading team in post-quantum cryptography and security developing quantum-resistant algorithms.</span></span>

## <a name="optimization"></a><span data-ttu-id="1e6e3-123">最適化</span><span class="sxs-lookup"><span data-stu-id="1e6e3-123">Optimization</span></span>

<span data-ttu-id="1e6e3-124">最適化は、特定の費用関数を最小限に抑えるソリューションを探して、高次元空間で大規模な検索を実行するタスクです。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-124">Optimization is the task of performing a large search over a high-dimensional space for a solution that minimizes a given cost function.</span></span>   <span data-ttu-id="1e6e3-125">量子コンピューターでは、最適化アルゴリズムを高速化し、他の方法では不可能な解決策を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-125">On a quantum computer, we can speed up optimization algorithms, enabling finding solutions that otherwise were not possible.</span></span> <span data-ttu-id="1e6e3-126">応用範囲には、輸送とロジスティクス、医療、診断、材料工学などがあります。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-126">Applications range from transportation and logistics, healthcare, diagnostics, and material science.</span></span> <span data-ttu-id="1e6e3-127">このような産業で効率性を上げる方法に大きな影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-127">There can be a profound impact on how these industries can become more efficient.</span></span>

<span data-ttu-id="1e6e3-128">量子コンピューターによる最適化を利用すれば、現在の古典的システムでは不可能な方法で輸送やロジスティクスのイノベーションが実現します。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-128">Optimization with quantum computing allows us to innovate around transportation and logistics in a way that is not possible with today’s classical systems.</span></span>

<span data-ttu-id="1e6e3-129">交通の流れを最適化することで、渋滞を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-129">Optimizing traffic flow can reduce congestion.</span></span>  <span data-ttu-id="1e6e3-130">経路指定計画に加え、飛行機のゲート割り当て、小包配達、作業の日程計画などがあります。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-130">In addition to route planning, there is airplane gate assignment, package delivery, job scheduling and more.</span></span> <span data-ttu-id="1e6e3-131">材料工学で画期的な技術が開発されると、新しい形態のエネルギー、大容量のバッテリー、軽くて強い素材が現れます。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-131">With breakthroughs in materials science, there will be new forms of energy, batteries with greater capacity, lighter and stronger materials.</span></span>

## <a name="machine-learning"></a><span data-ttu-id="1e6e3-132">機械学習</span><span class="sxs-lookup"><span data-stu-id="1e6e3-132">Machine learning</span></span>

<span data-ttu-id="1e6e3-133">従来型のコンピューティングでの数値計算の多くは、主に線形方程式系を解くことで構成されています。これは特に、計算コストの大半が大きな行列の逆行列の計算に使われる機械学習の分野に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-133">A great number of numerical calculations on classical computing consist mainly in solving linear systems of equations, especially true in the field of machine learning where most of the computation cost goes into calculating the inverse of huge matrices.</span></span>

<span data-ttu-id="1e6e3-134">幸いなことに、従来のコンピューターよりも指数関数的に速くシステムを近似解析できる量子アルゴリズムが存在します。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-134">Fortunately, there is a quantum algorithm that allows us to approximately solve the system exponentially faster than a classical computer.</span></span> <span data-ttu-id="1e6e3-135">このアルゴリズムにより、線形方程式系に対するソリューションが必要なすべての問題のより迅速な解決が実現されます。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-135">The algorithm opens the door to great speedups in every problem that needs the solution to linear systems of equations.</span></span>

<span data-ttu-id="1e6e3-136">このような領域で問題を解決できれば、エネルギー危機、気候変化、食糧不足、個人の精確な医療診断に対する取り組みにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-136">Solutions to problems in these areas will help address the energy crisis, climate change, food scarcity, and personal and precise medical diagnosis.</span></span>

## <a name="quantum-inspired-computing"></a><span data-ttu-id="1e6e3-137">量子から着想を得たコンピューティング</span><span class="sxs-lookup"><span data-stu-id="1e6e3-137">Quantum-inspired computing</span></span>

<span data-ttu-id="1e6e3-138">量子の影響を受けたアルゴリズムは、従来のソフトウェアで実装されますが、速度と正確性の向上のため量子の原則が使用されます。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-138">Quantum-inspired algorithms are implemented with classical software, but use quantum principles for increased speed and accuracy.</span></span>

<span data-ttu-id="1e6e3-139">量子の影響を受けたアルゴリズムは、医療研究に適用されつつあります。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-139">Quantum-inspired algorithms are being applied to medical research.</span></span> <span data-ttu-id="1e6e3-140">たとえば、核磁気共鳴画像法 (MRI) の精度を高めるために使用されています。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-140">For example, to improve the accuracy of Magnetic Resonance Imaging (MRI) scans.</span></span> <span data-ttu-id="1e6e3-141">量子の影響を受けたコンピューティングは、特定の病気の識別のため、MRI マシンの構成を最適化するために採用されています。</span><span class="sxs-lookup"><span data-stu-id="1e6e3-141">Quantum-inspired computing is being used to optimize the configuration of the MRI machines for identification of specific diseases.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1e6e3-142">次の手順</span><span class="sxs-lookup"><span data-stu-id="1e6e3-142">Next steps</span></span>

* [<span data-ttu-id="1e6e3-143">量子コンピューティングを学習する理由</span><span class="sxs-lookup"><span data-stu-id="1e6e3-143">Why should I learn quantum computing?</span></span>](xref:microsoft.quantum.overview.why)
* [<span data-ttu-id="1e6e3-144">Microsoft Quantum 開発キットの概要</span><span class="sxs-lookup"><span data-stu-id="1e6e3-144">Get started with the Microsoft Quantum Development Kit</span></span>](xref:microsoft.quantum.welcome)
