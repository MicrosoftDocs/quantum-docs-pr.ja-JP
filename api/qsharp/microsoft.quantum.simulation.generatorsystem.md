---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: c03caf99b197410c7fa15021c8acaaf55a728781
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724562"
---
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="b2cc1-102">GeneratorSystem ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="b2cc1-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="b2cc1-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="b2cc1-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="b2cc1-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b2cc1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b2cc1-105">Es のコレクションを表し `GeneratorIndex` ます。</span><span class="sxs-lookup"><span data-stu-id="b2cc1-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="b2cc1-106">このコレクションを1つのインデックス整数を使用して繰り返し処理します。コレクションのサイズは既知であると見なされます。</span><span class="sxs-lookup"><span data-stu-id="b2cc1-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="b2cc1-107">解説</span><span class="sxs-lookup"><span data-stu-id="b2cc1-107">Remarks</span></span>

<span data-ttu-id="b2cc1-108">`GeneratorSystem`関数を使用すると、のインスタンスを簡単に定義でき <xref:microsoft.quantum.arrays.lookupfunction> ます。</span><span class="sxs-lookup"><span data-stu-id="b2cc1-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2cc1-109">参照</span><span class="sxs-lookup"><span data-stu-id="b2cc1-109">See Also</span></span>

- [<span data-ttu-id="b2cc1-110">Microsoft. Quantum. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="b2cc1-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)