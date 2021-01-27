---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: b357aae20b5bddb968ce1906fed3c1001efbfde7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846978"
---
# <a name="labeledsample-user-defined-type"></a><span data-ttu-id="16009-102">LabeledSample ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="16009-102">LabeledSample user defined type</span></span>

<span data-ttu-id="16009-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="16009-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="16009-104">パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="16009-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="16009-105">このサンプルが属するクラスでラベル付けされたサンプル。</span><span class="sxs-lookup"><span data-stu-id="16009-105">A sample, labeled with a class to which that sample belongs.</span></span>

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a><span data-ttu-id="16009-106">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="16009-106">Named Items</span></span>

### <a name="features--double"></a><span data-ttu-id="16009-107">特徴: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="16009-107">Features : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="16009-108">指定されたサンプルの特徴のベクター。</span><span class="sxs-lookup"><span data-stu-id="16009-108">A vector of features for the given sample.</span></span>
### <a name="label--int"></a><span data-ttu-id="16009-109">ラベル: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="16009-109">Label : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="16009-110">このサンプルが属するクラスの整数ラベル。</span><span class="sxs-lookup"><span data-stu-id="16009-110">An integer label for the class to which this sample belongs.</span></span>