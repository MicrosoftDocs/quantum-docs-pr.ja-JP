---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample ユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: a7c7dae5cd9e82d66bb98313f4200838006ca291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196329"
---
# <a name="labeledsample-user-defined-type"></a><span data-ttu-id="2b71a-102">LabeledSample ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="2b71a-102">LabeledSample user defined type</span></span>

<span data-ttu-id="2b71a-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2b71a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="2b71a-104">パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2b71a-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="2b71a-105">このサンプルが属するクラスでラベル付けされたサンプル。</span><span class="sxs-lookup"><span data-stu-id="2b71a-105">A sample, labeled with a class to which that sample belongs.</span></span>

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a><span data-ttu-id="2b71a-106">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="2b71a-106">Named Items</span></span>

### <a name="features--double"></a><span data-ttu-id="2b71a-107">特徴: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="2b71a-107">Features : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="2b71a-108">指定されたサンプルの特徴のベクター。</span><span class="sxs-lookup"><span data-stu-id="2b71a-108">A vector of features for the given sample.</span></span>
### <a name="label--int"></a><span data-ttu-id="2b71a-109">ラベル: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2b71a-109">Label : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2b71a-110">このサンプルが属するクラスの整数ラベル。</span><span class="sxs-lookup"><span data-stu-id="2b71a-110">An integer label for the class to which this sample belongs.</span></span>