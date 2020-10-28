---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: N誤分類関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 9e356d68233519978e007e5a2999ca1be8cb7f83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709737"
---
# <a name="nmisclassifications-function"></a><span data-ttu-id="c201f-102">N誤分類関数</span><span class="sxs-lookup"><span data-stu-id="c201f-102">NMisclassifications function</span></span>

<span data-ttu-id="c201f-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c201f-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="c201f-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c201f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c201f-105">一連の推定ラベルと一連の正しいラベルが指定されると、によって、各ラベルのセットが異なるインデックスの数が返されます。</span><span class="sxs-lookup"><span data-stu-id="c201f-105">Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.</span></span>

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a><span data-ttu-id="c201f-106">入力</span><span class="sxs-lookup"><span data-stu-id="c201f-106">Input</span></span>

### <a name="proposed--int"></a><span data-ttu-id="c201f-107">提案済み: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c201f-107">proposed : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="actual--int"></a><span data-ttu-id="c201f-108">実際: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c201f-108">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--int"></a><span data-ttu-id="c201f-109">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c201f-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c201f-110">などのインデックスの数 `idx` `inferredLabels[idx] != actualLabels[idx]` 。</span><span class="sxs-lookup"><span data-stu-id="c201f-110">The number of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>