---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: ValidationResults ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 1e54a5a086035f5f8d36d777badb306156d99600
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720427"
---
# <a name="validationresults-user-defined-type"></a><span data-ttu-id="25d6a-102">ValidationResults ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="25d6a-102">ValidationResults user defined type</span></span>

<span data-ttu-id="25d6a-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="25d6a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="25d6a-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="25d6a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="25d6a-105">一連のサンプルに対して分類子が検証された結果。</span><span class="sxs-lookup"><span data-stu-id="25d6a-105">The results from having validated a classifier against a set of samples.</span></span>

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a><span data-ttu-id="25d6a-106">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="25d6a-106">Named Items</span></span>

### <a name="nmisclassifications--int"></a><span data-ttu-id="25d6a-107">N 誤分類: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="25d6a-107">NMisclassifications : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="25d6a-108">検証中に観察された誤分類の数。</span><span class="sxs-lookup"><span data-stu-id="25d6a-108">The number of misclassifications observed during validation.</span></span>
### <a name="nvalidationsamples--int"></a><span data-ttu-id="25d6a-109">NValidationSamples: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="25d6a-109">NValidationSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>
