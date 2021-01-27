---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: ValidationResults ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 923fd80333b6bf77daeaac2bf205db620e61cfd0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846091"
---
# <a name="validationresults-user-defined-type"></a><span data-ttu-id="87c9a-102">ValidationResults ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="87c9a-102">ValidationResults user defined type</span></span>

<span data-ttu-id="87c9a-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="87c9a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="87c9a-104">パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="87c9a-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="87c9a-105">一連のサンプルに対して分類子が検証された結果。</span><span class="sxs-lookup"><span data-stu-id="87c9a-105">The results from having validated a classifier against a set of samples.</span></span>

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a><span data-ttu-id="87c9a-106">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="87c9a-106">Named Items</span></span>

### <a name="nmisclassifications--int"></a><span data-ttu-id="87c9a-107">N 誤分類: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="87c9a-107">NMisclassifications : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="87c9a-108">検証中に観察された誤分類の数。</span><span class="sxs-lookup"><span data-stu-id="87c9a-108">The number of misclassifications observed during validation.</span></span>
### <a name="nvalidationsamples--int"></a><span data-ttu-id="87c9a-109">NValidationSamples: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="87c9a-109">NValidationSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

