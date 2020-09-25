---
title: 量子コンピューティングの概要
description: 量子コンピューティングとは何か、量子コンピューターで何ができるか、および量子コンピューティングを学習する方法について説明します。
author: bradben
ms.author: v-benbra
ms.date: 05/05/2020
ms.topic: overview
uid: microsoft.quantum.overview.introduction
no-loc:
- Q#
- $$v
ms.openlocfilehash: c3374e9fae07cc38761e404be7819e7cf699ce2b
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834518"
---
# <a name="introduction-to-quantum-computing-and-the-quantum-development-kit"></a><span data-ttu-id="817ca-103">量子コンピューティングと Quantum 開発キットの概要</span><span class="sxs-lookup"><span data-stu-id="817ca-103">Introduction to quantum computing and the Quantum Development Kit</span></span>

<span data-ttu-id="817ca-104">Microsoft Quantum 開発キット (QDK) は、開発者が量子アルゴリズムを学び、量子プログラムを記述できるように設計されたオープン ソースのツール セットです。</span><span class="sxs-lookup"><span data-stu-id="817ca-104">The Microsoft Quantum Development Kit (QDK) is a set of open-source tools designed to help developers learn quantum algorithms and write quantum programs.</span></span> <span data-ttu-id="817ca-105">量子コンピューティングは、地球上の環境、農業、健康、エネルギー、気候、材料工学などの分野に関わる最大の課題や、私たちがこれまで経験したことのないその他の問題を解決することを期待されています。</span><span class="sxs-lookup"><span data-stu-id="817ca-105">Quantum computing holds the promise to solve some of our planet's biggest challenges - in the areas of environment, agriculture, health, energy, climate, materials science, and others we haven't encountered yet.</span></span>  

<span data-ttu-id="817ca-106">こうした問題の中には、最も高性能なコンピューターでも問題が発生するものがあります。</span><span class="sxs-lookup"><span data-stu-id="817ca-106">For some of these problems, even our most powerful computers run into problems.</span></span> <span data-ttu-id="817ca-107">量子テクノロジは、コンピューティングの世界に影響を与え始めたばかりですが、その範囲は広大であると考えられ、コンピューティングに関する私たちの考え方を変える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="817ca-107">While quantum technology is just beginning to impact the computing world, it could be far-reaching and change the way we think about computing.</span></span>

## <a name="what-is-quantum-computing"></a><span data-ttu-id="817ca-108">量子コンピューティングとは</span><span class="sxs-lookup"><span data-stu-id="817ca-108">What is quantum computing?</span></span>

<span data-ttu-id="817ca-109">現代の用途では、量子という言葉は、物理特性の考えられる最小の不連続の単位を意味し、通常は、原子または亜原子粒子の特性を表します。</span><span class="sxs-lookup"><span data-stu-id="817ca-109">In modern usage, the word quantum means the smallest possible discrete unit of any physical property, usually referring to properties of atomic or subatomic particles.</span></span> <span data-ttu-id="817ca-110">量子コンピューターは、実際の量子粒子、人工原子、または量子粒子の集合的特性を処理単位として使用し、大規模で複雑かつ高価な装置です。</span><span class="sxs-lookup"><span data-stu-id="817ca-110">Quantum computers use actual quantum particles, artificial atoms, or collective properties of quantum particles as processing units, and are large, complex, and expensive devices.</span></span>

<span data-ttu-id="817ca-111">量子コンピューターでは、量子物理学の固有の性質を利用し、それをコンピューティングに適用することで、従来のプログラミング方式に新しい概念をもたらし、重ね合わせ、もつれ、量子干渉などの量子物理学の性質を活用します。</span><span class="sxs-lookup"><span data-stu-id="817ca-111">Harnessing the unique behavior of quantum physics and applying it to computing, quantum computers introduce new concepts to traditional programming methods, making use of quantum physics behaviors such as superposition, entanglement, and quantum interference.</span></span>

## <a name="what-can-a-quantum-computer-do"></a><span data-ttu-id="817ca-112">量子コンピューターでできること</span><span class="sxs-lookup"><span data-stu-id="817ca-112">What can a quantum computer do?</span></span>

<span data-ttu-id="817ca-113">量子コンピューターはすべてを高速に実行できるスーパーコンピューターではありませんが、量子コンピューターが優れた能力を発揮する分野があります。</span><span class="sxs-lookup"><span data-stu-id="817ca-113">A quantum computer isn't a supercomputer that can do everything faster, but there are a few areas where quantum computers do exceptionally well.</span></span>

- [<span data-ttu-id="817ca-114">量子シミュレーション</span><span class="sxs-lookup"><span data-stu-id="817ca-114">Quantum simulation</span></span>](xref:microsoft.quantum.overview.introduction#quantum-simulation)
- [<span data-ttu-id="817ca-115">暗号化</span><span class="sxs-lookup"><span data-stu-id="817ca-115">Cryptography</span></span>](xref:microsoft.quantum.overview.introduction#cryptography-and-shors-algorithm)
- [<span data-ttu-id="817ca-116">Search</span><span class="sxs-lookup"><span data-stu-id="817ca-116">Search</span></span>](xref:microsoft.quantum.overview.introduction#search-and-grovers-algorithm)
- [<span data-ttu-id="817ca-117">最適化</span><span class="sxs-lookup"><span data-stu-id="817ca-117">Optimization</span></span>](xref:microsoft.quantum.overview.introduction#quantum-inspired-computing-and-optimization)
- [<span data-ttu-id="817ca-118">機械学習</span><span class="sxs-lookup"><span data-stu-id="817ca-118">Machine learning</span></span>](xref:microsoft.quantum.overview.introduction#quantum-machine-learning)

## <a name="quantum-simulation"></a><span data-ttu-id="817ca-119">量子シミュレーション</span><span class="sxs-lookup"><span data-stu-id="817ca-119">Quantum simulation</span></span>

<span data-ttu-id="817ca-120">量子コンピューターは、計算に量子現象が活用されるため、他の量子システムをモデル化するのに適しています。</span><span class="sxs-lookup"><span data-stu-id="817ca-120">Since quantum computers use quantum phenomena in computation, they are well suited for modeling other quantum systems.</span></span> <span data-ttu-id="817ca-121">光合成、超伝導、複雑な分子形成は、量子プログラムでシミュレートできる量子メカニズムの例です。</span><span class="sxs-lookup"><span data-stu-id="817ca-121">Photosynthesis, superconductivity, and complex molecular formations are examples of quantum mechanisms that quantum programs can simulate.</span></span>

## <a name="cryptography-and-shors-algorithm"></a><span data-ttu-id="817ca-122">暗号とショアのアルゴリズム</span><span class="sxs-lookup"><span data-stu-id="817ca-122">Cryptography and Shor’s algorithm</span></span>

<span data-ttu-id="817ca-123">1994 年、ピーター・ショアは、スケーラブルな量子コンピューターによって RSA アルゴリズムなどの広く使用されている暗号化手法を解読できることを示しました。</span><span class="sxs-lookup"><span data-stu-id="817ca-123">In 1994, Peter Shor showed that a scalable quantum computer could break widely used encryption techniques such as the RSA algorithm.</span></span> <span data-ttu-id="817ca-124">従来の暗号化は、素因数分解や離散対数など、問題解決の難しさを利用していましたが、その多くは量子コンピューターを使用することで、より効率的に解決できます。</span><span class="sxs-lookup"><span data-stu-id="817ca-124">Classical cryptography relies on the intractability of problems such as integer factorization or discrete logarithms, many of which can be solved more efficiently using quantum computers.</span></span>

## <a name="search-and-grovers-algorithm"></a><span data-ttu-id="817ca-125">検索とグローバーのアルゴリズム</span><span class="sxs-lookup"><span data-stu-id="817ca-125">Search and Grover’s algorithm</span></span>

<span data-ttu-id="817ca-126">1996 年、ロブ・グローバーは、非構造化データ検索の求解を大幅に高速化する量子アルゴリズムを開発し、従来のどのアルゴリズムよりも少ない手順で検索を実行できるようにしました。</span><span class="sxs-lookup"><span data-stu-id="817ca-126">In 1996, Lov Grover developed a quantum algorithm that dramatically sped up the solution to unstructured data searches, running the search in fewer steps than any classical algorithm could.</span></span>

## <a name="quantum-inspired-computing-and-optimization"></a><span data-ttu-id="817ca-127">量子から着想を得たコンピューティングと最適化</span><span class="sxs-lookup"><span data-stu-id="817ca-127">Quantum-inspired computing and optimization</span></span>

<span data-ttu-id="817ca-128">量子から着想を得たアルゴリズムは、速度と精度の向上のために量子の原則を利用しますが、従来型コンピューター システムに実装されます。</span><span class="sxs-lookup"><span data-stu-id="817ca-128">Quantum-inspired algorithms use quantum principles for increased speed and accuracy but implement on classical computer systems.</span></span> <span data-ttu-id="817ca-129">このアプローチを使用すると、開発者は、いまだ新興の業界である量子ハードウェアを待たなくても、新しい量子手法の力を活用できます。</span><span class="sxs-lookup"><span data-stu-id="817ca-129">This approach allows developers to leverage the power of new quantum techniques today without waiting for quantum hardware, which is still an emerging industry.</span></span>

<span data-ttu-id="817ca-130">最適化は、所望の結果と制約をふまえて、問題に対する最適な解を見つけるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="817ca-130">Optimization is the process of finding the best solution to a problem, given its desired outcome and constraints.</span></span> <span data-ttu-id="817ca-131">コスト、品質、生産時間などの要因はすべて、産業と科学で行われる重要な意思決定にかかわってきます。</span><span class="sxs-lookup"><span data-stu-id="817ca-131">Factors such as cost, quality, or production time all play into critical decisions made by industry and science.</span></span> <span data-ttu-id="817ca-132">量子から着想を得た最適化アルゴリズムを現在の従来型コンピューターで実行することで、これまで不可能だった解を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="817ca-132">Quantum-inspired optimization algorithms running on today's classical computers can find solutions that up to now have not been possible.</span></span> <span data-ttu-id="817ca-133">渋滞を軽減するための交通量の最適化に加え、飛行機のゲート割り当て、小包配送、作業の日程計画などがあります。</span><span class="sxs-lookup"><span data-stu-id="817ca-133">In addition to optimizing traffic flow to reduce congestion, there is airplane gate assignment, package delivery, job scheduling and more.</span></span> <span data-ttu-id="817ca-134">材料工学で画期的な技術が開発されると、新しい形態のエネルギー、大容量のバッテリー、軽くて耐久性に優れた素材が現れます。</span><span class="sxs-lookup"><span data-stu-id="817ca-134">With breakthroughs in materials science, there will be new forms of energy, batteries with larger capacity, and lighter and more durable materials.</span></span>

> [!NOTE]
> <span data-ttu-id="817ca-135">[材料工学](https://cloudblogs.microsoft.com/quantum/2020/01/21/oti-lumionics-accelerating-materials-design-microsoft-azure-quantum/)、[リスク管理](https://cloudblogs.microsoft.com/quantum/2019/05/22/microsoft-quantum-collaborates-with-willis-towers-watson-to-transform-risk-management-solutions/)、[医薬](https://blogs.microsoft.com/blog/2018/05/18/microsoft-quantum-helps-case-western-reserve-university-advance-mri-research/)で、量子から着想を得た Microsoft のコンピューティングがどのように利用されているかをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="817ca-135">Read more about how Microsoft quantum-inspired computing is being used in [materials science](https://cloudblogs.microsoft.com/quantum/2020/01/21/oti-lumionics-accelerating-materials-design-microsoft-azure-quantum/), [risk management](https://cloudblogs.microsoft.com/quantum/2019/05/22/microsoft-quantum-collaborates-with-willis-towers-watson-to-transform-risk-management-solutions/), and [medicine](https://blogs.microsoft.com/blog/2018/05/18/microsoft-quantum-helps-case-western-reserve-university-advance-mri-research/).</span></span>

## <a name="quantum-machine-learning"></a><span data-ttu-id="817ca-136">量子機械学習</span><span class="sxs-lookup"><span data-stu-id="817ca-136">Quantum machine learning</span></span>

<span data-ttu-id="817ca-137">従来型コンピューターでの機械学習は、科学とビジネスの世界に大きな変革をもたらしています。</span><span class="sxs-lookup"><span data-stu-id="817ca-137">Machine learning on classical computers is revolutionizing the world of science and business.</span></span> <span data-ttu-id="817ca-138">ただし、モデルのトレーニングのコンピューティング コストが高額なことが、この分野の発展と広がりの妨げになっています。</span><span class="sxs-lookup"><span data-stu-id="817ca-138">However, the high computational cost of training the models hinders the development and scope of the field.</span></span> <span data-ttu-id="817ca-139">量子機械学習の分野では、従来型コンピューターより高速に動作する機械学習を可能にする、量子ソフトウェアを考案して実装する方法を探求します。</span><span class="sxs-lookup"><span data-stu-id="817ca-139">The area of quantum machine learning explores how to devise and implement quantum software that enables machine learning that runs faster than classical computers.</span></span>

<span data-ttu-id="817ca-140">Quantum 開発キットには [Quantum Machine Learning Library](xref:microsoft.quantum.machine-learning.concepts.intro) が付属しています。これを使用すると、量子/従来型のハイブリッド機械学習の実験を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="817ca-140">The Quantum Development Kit comes with the [quantum machine learning library](xref:microsoft.quantum.machine-learning.concepts.intro) that gives you the ability to run hybrid quantum/classical machine learning experiments.</span></span> <span data-ttu-id="817ca-141">このライブラリには、サンプルとチュートリアルが含まれています。また、教師あり分類問題を解決するための新たな量子/従来型ハイブリッド アルゴリズムである回路中心量子分類器の実装に必要なツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="817ca-141">The library includes samples and tutorials, and provides the necessary tools to implement a new hybrid quantum–classical algorithm, the circuit-centric quantum classifier, to solve supervised classification problems.</span></span>

## <a name="no-locq-and-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="817ca-142">Q# と Microsoft Quantum 開発キット (QDK)</span><span class="sxs-lookup"><span data-stu-id="817ca-142">Q# and the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="817ca-143">Q# は、量子アルゴリズムを開発および実行するための Microsoft のオープンソース プログラミング言語です。</span><span class="sxs-lookup"><span data-stu-id="817ca-143">Q# is Microsoft's open-source programming language for developing and running quantum algorithms.</span></span> <span data-ttu-id="817ca-144">これは [QDK](https://docs.microsoft.com/quantum/) に含まれています。QDK は Q# 用のフル機能の開発キットであり、組み込みの全状態の量子シミュレーターなど、さまざまな環境で実行できる量子アプリケーションを開発するために、標準のツールと言語で使用できます。</span><span class="sxs-lookup"><span data-stu-id="817ca-144">It is part of the [QDK](https://docs.microsoft.com/quantum/), a full-featured development kit for Q# that you can use with standard tools and languages to develop quantum applications that you can run in various environments, including the built-in full-state quantum simulator.</span></span>

<span data-ttu-id="817ca-145">Visual Studio と VS Code 用の拡張機能と、Python と Jupyter Notebook で使用するためのパッケージが用意されています。</span><span class="sxs-lookup"><span data-stu-id="817ca-145">There are extensions for Visual Studio and VS Code, and packages for use with Python and Jupyter Notebook.</span></span>

<span data-ttu-id="817ca-146">QDK には、化学、機械学習、数値の特殊ライブラリとともに標準ライブラリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="817ca-146">The QDK includes a standard library along with specialized chemistry, machine learning, and numerics libraries.</span></span>

<span data-ttu-id="817ca-147">このドキュメントには、すぐに開始できるようにするための Q# 言語ガイド、チュートリアル、サンプル コードが含まれています。また、量子コンピューティングの概念を深く理解するのに役立つ豊富な記事が掲載されています。</span><span class="sxs-lookup"><span data-stu-id="817ca-147">The documentation includes a Q# language guide, tutorials, and sample code to get you started quickly, and rich articles to help you dive deeper into quantum computing concepts.</span></span>  

## <a name="microsoft-quantum-hardware-partners"></a><span data-ttu-id="817ca-148">Microsoft の量子ハードウェアのパートナー</span><span class="sxs-lookup"><span data-stu-id="817ca-148">Microsoft quantum hardware partners</span></span>

<span data-ttu-id="817ca-149">開発者がクラウドで量子ハードウェアにアクセスできるように、Microsoft は量子ハードウェア メーカーと提携しています。</span><span class="sxs-lookup"><span data-stu-id="817ca-149">Microsoft is partnering with quantum hardware companies to provide developers with cloud access to quantum hardware.</span></span> <span data-ttu-id="817ca-150">開発者は、[Azure Quantum](https://azure.microsoft.com/services/quantum/) プラットフォームと Q# 言語 を利用して、さまざまな種類の量子ハードウェアで量子アルゴリズムを探求し、量子プログラムを実行できます。</span><span class="sxs-lookup"><span data-stu-id="817ca-150">Leveraging the [Azure Quantum](https://azure.microsoft.com/services/quantum/) platform and the Q# language, developers will be able to explore quantum algorithms and run their quantum programs on different types of quantum hardware.</span></span>

<span data-ttu-id="817ca-151">[IonQ](https://ionq.com/news/november-4-2019-microsoft-partnership) と [Honeywell](https://www.honeywell.com/en-us/newsroom/news/2019/11/the-future-of-quantum-computing) は両方とも、**捕捉イオン ベース**のプロセッサを使用し、電子場に捕捉された個々のイオンを利用しています。それに対し、[QCI](https://quantumcircuits.com/news-and-publications/quantum-circuits-partners-with-microsoft-on-azure-quantum) では、超伝導回路を使用しています。</span><span class="sxs-lookup"><span data-stu-id="817ca-151">[IonQ](https://ionq.com/news/november-4-2019-microsoft-partnership) and [Honeywell](https://www.honeywell.com/en-us/newsroom/news/2019/11/the-future-of-quantum-computing) both use **trapped ion-based** processors, utilizing individual ions trapped in an electronic field, whereas [QCI](https://quantumcircuits.com/news-and-publications/quantum-circuits-partners-with-microsoft-on-azure-quantum) uses superconducting circuits.</span></span>

## <a name="next-steps"></a><span data-ttu-id="817ca-152">次のステップ</span><span class="sxs-lookup"><span data-stu-id="817ca-152">Next steps</span></span>

<span data-ttu-id="817ca-153">[量子コンピューティングの主要な概念](xref:microsoft.quantum.overview.understanding)
[クイックスタート](xref:microsoft.quantum.welcome)</span><span class="sxs-lookup"><span data-stu-id="817ca-153">[Key concepts for quantum computing](xref:microsoft.quantum.overview.understanding)
[Quickstarts](xref:microsoft.quantum.welcome)</span></span>