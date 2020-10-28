---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: 8b4afa1eaf7ca69938b2606163cd1ec17a1ad80f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711333"
---
# <a name="labeledsample-user-defined-type"></a><span data-ttu-id="43128-102">LabeledSample ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="43128-102">LabeledSample user defined type</span></span>

<span data-ttu-id="43128-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="43128-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="43128-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="43128-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="43128-105">このサンプルが属するクラスでラベル付けされたサンプル。</span><span class="sxs-lookup"><span data-stu-id="43128-105">A sample, labeled with a class to which that sample belongs.</span></span>

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a><span data-ttu-id="43128-106">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="43128-106">Named Items</span></span>

### <a name="features--double"></a><span data-ttu-id="43128-107">特徴: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="43128-107">Features : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="43128-108">指定されたサンプルの特徴のベクター。</span><span class="sxs-lookup"><span data-stu-id="43128-108">A vector of features for the given sample.</span></span>
### <a name="label--int"></a><span data-ttu-id="43128-109">ラベル: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="43128-109">Label : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="43128-110">このサンプルが属するクラスの整数ラベル。</span><span class="sxs-lookup"><span data-stu-id="43128-110">An integer label for the class to which this sample belongs.</span></span>