---
title: 量子開発手法
description: Q# プログラム開発の基礎を学び、演算、関数、変数、量子ビットを操作し、簡単な量子プログラムを作成します。
keywords: SEO チャンプを確認せずに、キーワードを追加または編集しないでください。
author: QuantumWriter
ms.author: MSFT-alias-person-or-DL
ms.date: 9/20/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.techniques.intro
ms.openlocfilehash: e5b7fbde18afbc0333d89f70c5e4596848e30f4f
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2020
ms.locfileid: "77907717"
---
# <a name="quantum-development-techniques"></a><span data-ttu-id="af450-104">量子開発手法</span><span class="sxs-lookup"><span data-stu-id="af450-104">Quantum Development Techniques</span></span>

<span data-ttu-id="af450-105">ドキュメントのこのセクションでは、Q# で量子プログラムを作成するために使用される主な概念と、従来のアプリケーションからこのようなプログラムを扱う方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="af450-105">This section of our documentation details the core concepts used to create quantum programs in Q#, and to interact with those programs from classical applications.</span></span>
<span data-ttu-id="af450-106">[量子コンピューティングの概念](xref:microsoft.quantum.concepts.intro)に関する記事で説明されている内容のような、量子コンピューティングの概念に関する "*ある程度の*" 知識が想定されていますが、量子コンピューティングの専門家でなくてもこれらのセクションから多くを学ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="af450-106">We assume *some* knowledge of quantum computing concepts, like those described in [Quantum computing concepts](xref:microsoft.quantum.concepts.intro), but you need not be an expert in quantum computing to get a lot from these sections.</span></span>

<span data-ttu-id="af450-107">その内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="af450-107">Their contents are as follows.</span></span>

- <span data-ttu-id="af450-108">「[Q# プログラムの概要](xref:microsoft.quantum.techniques.file-structure)」では、Q# プログラミング言語の目的と機能に関する概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="af450-108">[Q# program overview](xref:microsoft.quantum.techniques.file-structure) provides an overview of the purpose and functionality of the Q# programming language.</span></span> 
    <span data-ttu-id="af450-109">具体的には、Q# が量子力学のシミュレーションを行うためだけの言語では "*ない*" ことが明確に説明されます (もちろんその機能も、完全状態シミュレーターによって提供されています)。</span><span class="sxs-lookup"><span data-stu-id="af450-109">In particular, it clarifies how Q# is *not* a language for merely simulating quantum mechanics---though that functionality is of course provided by our full state simulator.</span></span> 
    <span data-ttu-id="af450-110">代わりに、Q# は将来を見据えて設計されており、そのプログラムでは、古典制御のコンピューターによって量子ビットを "*操作する*" 方法を記述することができます。</span><span class="sxs-lookup"><span data-stu-id="af450-110">Rather, Q# was designed with an eye on the future, and its programs describe how a classical control computer *interacts* with qubits.</span></span> 

- <span data-ttu-id="af450-111">[演算と関数](xref:microsoft.quantum.techniques.opsandfunctions)に関する記事では、Q# 言語の 2 つの呼び出し可能な型について詳しく説明します。すなわち、"*演算*" (量子ビットと量子システムに対するアクションを含みます) と "*関数*" (従来の情報と厳密に連携して機能します) です。</span><span class="sxs-lookup"><span data-stu-id="af450-111">[Operations and functions](xref:microsoft.quantum.techniques.opsandfunctions) details the two callable types of the Q# language: *operations*, which include action on qubits and quantum systems; and *functions*, which strictly work with classical information.</span></span> 
    <span data-ttu-id="af450-112">従来の情報と量子情報の両方が連携して動作することがなければ、量子コンピューティングの利用は難しいままになるでしょう。</span><span class="sxs-lookup"><span data-stu-id="af450-112">Without both classical and quantum information working in tandem, quantum computing would remain out of reach.</span></span> 
    <span data-ttu-id="af450-113">このセクションでは、Q# プログラムの制御フロー内で、これらの呼び出し可能な型を定義および使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="af450-113">This section describes how to define and use these callables within the control flow of a Q# program.</span></span>

- <span data-ttu-id="af450-114">「[ローカル変数](xref:microsoft.quantum.techniques.local-variables)」では、Q# プログラム内における変数の役割と、それらを効果的に活用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="af450-114">[Local variables](xref:microsoft.quantum.techniques.local-variables) describes the role of variables within Q# programs and how to leverage them effectively.</span></span> 
    <span data-ttu-id="af450-115">特に、変更不可の変数と変更可能な変数の違いと、それらを割り当ておよび再割り当てする方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="af450-115">In particular, you will learn the difference between immutable/mutable variables and how to assign/re-assign them.</span></span>

- <span data-ttu-id="af450-116">「[量子ビットの操作](xref:microsoft.quantum.techniques.qubits)」では、個別の量子ビットと量子ビットのシステムに対処するために使用できる Q# の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="af450-116">[Working with qubits](xref:microsoft.quantum.techniques.qubits) describes the features of Q# that you can use to address individual qubits and systems of qubits.</span></span> 
    <span data-ttu-id="af450-117">具体的には、それらの割り当て、それらに対する演算の実行、そして最終的にそれらの測定を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="af450-117">Specifically, that entails their allocation, performing operations on them, and ultimately their measurement.</span></span> 
    <span data-ttu-id="af450-118">さらに、いくつかの有用な制御フローの手法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="af450-118">Additionally, you will learn some useful control flow techniques.</span></span>

- <span data-ttu-id="af450-119">[まとめ](xref:microsoft.quantum.techniques.puttingittogether)に関する記事では、上記のセクションの手法を活用して、**量子テレポーテーション**を実行するプログラムを作成します。つまり、2 つの従来のビットを使用して、1 つの量子ビットの完全状態を別の量子ビットに "テレポート" させます。</span><span class="sxs-lookup"><span data-stu-id="af450-119">In [Putting it all together](xref:microsoft.quantum.techniques.puttingittogether), you will leverage the techniques from the sections above to create a program which performs **quantum teleportation**: using two classical bits to "teleport" the full state of one qubit onto another.</span></span>

- <span data-ttu-id="af450-120">「[さらに進める](xref:microsoft.quantum.techniques.going-further)」では、より複雑な量子プログラミングに移行する際に役立つことがわかる高度な手法を紹介します。</span><span class="sxs-lookup"><span data-stu-id="af450-120">[Going further](xref:microsoft.quantum.techniques.going-further) introduces advanced techniques that can prove helpful as you move toward more complex quantum programming.</span></span> 
    <span data-ttu-id="af450-121">具体的には、Q# の "*型パラメーター化された*" 演算と関数の使用について説明します。これを使用すると、その入出力を特定の型に依存させないことによる上位の制御フローと、量子ビットを "*借りること*" が可能になります。</span><span class="sxs-lookup"><span data-stu-id="af450-121">In particular, we discuss the use of *type-parameterized* operations and functions in Q#, which enable higher-order control flow by remaining agnostic to the specific types of their input/output, as well as *borrowing* qubits.</span></span> 
    <span data-ttu-id="af450-122">後者は基本的な量子ビットの割り当てとは異なります。つまり、Q# の演算で、計算を支援するために "ダーティな" 量子ビット (必ずしも既知の状態に初期化されていない量子ビット) が使用されることがあります。</span><span class="sxs-lookup"><span data-stu-id="af450-122">The latter differs from basic qubit allocation in that a Q# operation may use "dirty" qubits---qubits not necessarily initialized to a known state---to assist computations.</span></span>

- <span data-ttu-id="af450-123">「[テストとデバッグ](xref:microsoft.quantum.techniques.testing-and-debugging)」では、自分のコードが想定どおりに動作していることを確かめるためのいくつかの手法について説明します。</span><span class="sxs-lookup"><span data-stu-id="af450-123">[Testing and debugging](xref:microsoft.quantum.techniques.testing-and-debugging) details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="af450-124">量子情報の一般的な不透明性により、量子プログラムのデバッグには特殊な手法が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="af450-124">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="af450-125">さいわい、Q# では、プログラマーが慣れている従来のデバッグ手法の多くと、量子特有の手法がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="af450-125">Fortunately, Q# supports many of the classical debugging techniques programmers are used to, as well as those that are quantum-specific.</span></span> <span data-ttu-id="af450-126">これには、Q# での単体テストの作成や実行、コード内の値と確率に対する "*アサーション*" の埋め込み、ターゲット コンピューターの状態を出力する `Dump` 関数などが含まれています。</span><span class="sxs-lookup"><span data-stu-id="af450-126">These include creating/running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the state of target machine.</span></span> 
    <span data-ttu-id="af450-127">その後者を完全状態シミュレーターと共に使用して、いくつかの量子限界を回避することで計算の特定の部分をデバッグすることができます (例: 量子複製不可能定理)。</span><span class="sxs-lookup"><span data-stu-id="af450-127">The latter can be used alongside our full state simulator to debug certain parts of computations by skirting some quantum limitations (e.g. the no-cloning theorem).</span></span>


![量子](~/media/mobius_strip_preview.png)
