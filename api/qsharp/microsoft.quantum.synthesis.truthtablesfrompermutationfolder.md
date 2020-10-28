---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutationFolder
title: TruthTablesFromPermutationFolder 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutationFolder
qsharp.summary: Decomposition logic for a single variable index
ms.openlocfilehash: 6b00c9e880ed7b7b3bf446dcb17dab3bab7a83a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724455"
---
# <a name="truthtablesfrompermutationfolder-function"></a><span data-ttu-id="32dbb-102">TruthTablesFromPermutationFolder 関数</span><span class="sxs-lookup"><span data-stu-id="32dbb-102">TruthTablesFromPermutationFolder function</span></span>

<span data-ttu-id="32dbb-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="32dbb-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="32dbb-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="32dbb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="32dbb-105">単一の変数インデックスの分解ロジック</span><span class="sxs-lookup"><span data-stu-id="32dbb-105">Decomposition logic for a single variable index</span></span>

```qsharp
function TruthTablesFromPermutationFolder (numVars : Int, state : Microsoft.Quantum.Synthesis.DecompositionState, index : Int) : Microsoft.Quantum.Synthesis.DecompositionState
```


## <a name="description"></a><span data-ttu-id="32dbb-106">説明</span><span class="sxs-lookup"><span data-stu-id="32dbb-106">Description</span></span>

<span data-ttu-id="32dbb-107">これは、現在の状態を取得して、更新された順列を生成し、場合によっては制御ゲート用の新しい関数を追加します。</span><span class="sxs-lookup"><span data-stu-id="32dbb-107">This takes the current state and generates an updated permutation and possibly adds new functions for controlled gates.</span></span>

## <a name="input"></a><span data-ttu-id="32dbb-108">入力</span><span class="sxs-lookup"><span data-stu-id="32dbb-108">Input</span></span>

### <a name="numvars--int"></a><span data-ttu-id="32dbb-109">numVars: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="32dbb-109">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="state--decompositionstate"></a><span data-ttu-id="32dbb-110">状態: [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="32dbb-110">state : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>




### <a name="index--int"></a><span data-ttu-id="32dbb-111">index: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="32dbb-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--decompositionstate"></a><span data-ttu-id="32dbb-112">出力: [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="32dbb-112">Output : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>

