---
title: 量子化学ライブラリの概要
description: Microsoft Quantum Chemistry Library と、それを使用して量子コンピューターの電子構造問題をシミュレートする方法について説明します。
author: QuantumWriter
ms.author: ageller
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 15439a34933bd561dc011acf48e669abeb031e33
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835793"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a><span data-ttu-id="df3ee-103">量子化学ライブラリの概要</span><span class="sxs-lookup"><span data-stu-id="df3ee-103">Introduction to the Quantum Chemistry Library</span></span>

<span data-ttu-id="df3ee-104">物理システムのシミュレーションは、量子コンピューティングにおいて中心的な役割を果たしています。</span><span class="sxs-lookup"><span data-stu-id="df3ee-104">Simulation of physical systems has long played a central role in quantum computing.</span></span>  <span data-ttu-id="df3ee-105">これは、量子ダイナミクスが量子コンピューターでのシミュレーションでは難しいと広く信じられているためです。つまり、システムのシミュレーションの複雑さは、対象となる量子システムのサイズに応じて指数関数的に拡大します。</span><span class="sxs-lookup"><span data-stu-id="df3ee-105">This is because quantum dynamics are widely believed to be intractable to simulate on quantum computers, meaning that the complexity of simulating the system scales exponentially with the size of the quantum system in question.</span></span>  <span data-ttu-id="df3ee-106">化学および材料工学の問題のシミュレーションは、今でもおそらく量子コンピューティングで最も刺激的な応用であり、これまで測定やシミュレーションができないとされていた化学反応のメカニズムの探査を可能にしています。</span><span class="sxs-lookup"><span data-stu-id="df3ee-106">Simulating problems in chemistry and material science remains perhaps the most evocative application of quantum computing and would allow us to probe chemical reaction mechanisms that hitherto were beyond our ability to measure or simulate.</span></span>  <span data-ttu-id="df3ee-107">また、高温の超電導のような相関する電子材料もシミュレートできるようになります。</span><span class="sxs-lookup"><span data-stu-id="df3ee-107">It would also allow us to simulate correlated electronic materials such as high-temperature superconductors.</span></span> <span data-ttu-id="df3ee-108">この分野の応用例は多岐にわたります。</span><span class="sxs-lookup"><span data-stu-id="df3ee-108">The list of applications in this space is vast.</span></span>

<span data-ttu-id="df3ee-109">このドキュメントの目的は、ハミルトニアン シミュレーション ライブラリの多くの要素が空間内で果たす役割を読者が理解できるように、量子コンピューターでの電子構造の問題のシミュレーションに関する簡潔な概要を提供することです。</span><span class="sxs-lookup"><span data-stu-id="df3ee-109">The purpose of this documentation is to provide a concise introduction to simulating electronic structure problems on quantum computers in order to help the reader understand the role that many aspects of the Hamiltonian simulation library play within the space.</span></span>  <span data-ttu-id="df3ee-110">まず、量子力学について簡単に紹介してから、そこで電子システムがどのようにモデル化されているかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="df3ee-110">We begin with a brief introduction to quantum mechanics and then proceed to discuss how electronic systems are modeled in it.</span></span>  <span data-ttu-id="df3ee-111">次に、量子コンピューターを使用してそのような量子ダイナミクスをエミュレートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="df3ee-111">We will then discuss how such quantum dynamics can be emulated using a quantum computer.</span></span>  <span data-ttu-id="df3ee-112">それが終わったら、量子ダイナミクスをわかりやすく説明するために使用する 2 つの方法を取り上げます。それが、鈴木トロッター分解と、量子ビット化です。</span><span class="sxs-lookup"><span data-stu-id="df3ee-112">Once this is complete we will discuss two methods used to compile the quantum dynamics to sequences of elementary gates: Trotter-Suzuki decompositions and qubitization.</span></span>
