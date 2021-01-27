---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 3748d3fb79597fb526c86a91bc28290155189014
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858421"
---
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="6f90a-102">GeneratorSystem ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="6f90a-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="6f90a-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="6f90a-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="6f90a-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6f90a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6f90a-105">Es のコレクションを表し `GeneratorIndex` ます。</span><span class="sxs-lookup"><span data-stu-id="6f90a-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="6f90a-106">このコレクションを1つのインデックス整数を使用して繰り返し処理します。コレクションのサイズは既知であると見なされます。</span><span class="sxs-lookup"><span data-stu-id="6f90a-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="6f90a-107">解説</span><span class="sxs-lookup"><span data-stu-id="6f90a-107">Remarks</span></span>

<span data-ttu-id="6f90a-108">`GeneratorSystem`関数を使用すると、のインスタンスを簡単に定義でき <xref:microsoft.quantum.arrays.lookupfunction> ます。</span><span class="sxs-lookup"><span data-stu-id="6f90a-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f90a-109">参照</span><span class="sxs-lookup"><span data-stu-id="6f90a-109">See Also</span></span>

- [<span data-ttu-id="6f90a-110">Microsoft. Quantum. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="6f90a-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)