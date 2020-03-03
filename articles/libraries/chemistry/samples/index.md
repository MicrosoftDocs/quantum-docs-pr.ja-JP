---
title: 量子化学のサンプル アプリケーション
description: Microsoft Quantum Chemistry Library のサンプル アプリケーションについて確認します。
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples
ms.openlocfilehash: 5168fc8592d34a32ba67e5a0c4793aa17599fd35
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906493"
---
# <a name="quantum-chemistry-examples"></a><span data-ttu-id="c265e-103">量子化学の例</span><span class="sxs-lookup"><span data-stu-id="c265e-103">Quantum chemistry examples</span></span>

<span data-ttu-id="c265e-104">量子化学の概念では、フェルミオン ハミルトニアンの例を手動で構築しました。</span><span class="sxs-lookup"><span data-stu-id="c265e-104">In the quantum chemistry concepts, we manually constructed example fermion Hamiltonians.</span></span> <span data-ttu-id="c265e-105">[ハミルトニアン ダイナミクスのシミュレーション](xref:microsoft.quantum.libraries.standard.algorithms)で説明した化学シミュレーション アルゴリズムは、規範ライブラリの[量子位相推定](xref:microsoft.quantum.libraries.characterization)に統合されています。</span><span class="sxs-lookup"><span data-stu-id="c265e-105">We now combine the chemistry simulation algorithms outlined in [Simulating Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms) with [quantum phase estimation](xref:microsoft.quantum.libraries.characterization) in the canon library.</span></span> <span data-ttu-id="c265e-106">この組み合わせにより、分子で表されるエネルギー レベルを推定することができます。量子コンピューターの量子化学が主に応用されているのが、分子です。</span><span class="sxs-lookup"><span data-stu-id="c265e-106">This combination allows us to obtain  estimates of energy levels in the represented molecule, which is one of the key applications of quantum chemistry on a quantum computer.</span></span> 

<span data-ttu-id="c265e-107">ハミルトニアンの用語を 1 つずつ指定する代わりに、大規模な量子化学実験の実行を可能にするいくつかの例についても説明します。</span><span class="sxs-lookup"><span data-stu-id="c265e-107">Instead of specifying terms of the Hamiltonian one-by-one, we also work through some examples that allow us to perform quantum chemistry experiments at scale.</span></span> <span data-ttu-id="c265e-108">最初に、[Broombridge スキーマ](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)でエンコードされた化学ハミルトニアンを読み込む例から始めます。</span><span class="sxs-lookup"><span data-stu-id="c265e-108">We begin with examples that load a chemistry Hamiltonian encoded in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).</span></span>

<span data-ttu-id="c265e-109">[完全状態シミュレーター](xref:microsoft.quantum.machines.full-state-simulator)でシミュレートするには大きすぎる分子でも、興味深い科学を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c265e-109">For molecules that are too large to simulate on the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), interesting science can still be performed.</span></span> <span data-ttu-id="c265e-110">たとえば、大規模な化学シミュレーションを実行するリソース コストは、[トレース シミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)を対象にすることで評価できます。</span><span class="sxs-lookup"><span data-stu-id="c265e-110">For instance, the resource costs of performing large chemistry simulations may still be evaluated by targeting the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>

<span data-ttu-id="c265e-111">提供された例のいくつかを使用して、化学シミュレーション ライブラリの興味深い応用例を説明します。</span><span class="sxs-lookup"><span data-stu-id="c265e-111">Let us now illustrate interesting applications of the chemistry simulation library through a few of the provided samples.</span></span>
