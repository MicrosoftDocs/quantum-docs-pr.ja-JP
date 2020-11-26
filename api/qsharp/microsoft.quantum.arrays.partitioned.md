---
uid: Microsoft.Quantum.Arrays.Partitioned
title: パーティション関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: bce46262e3ef64a43e578098d81c5dd39225915e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220503"
---
# <a name="partitioned-function"></a><span data-ttu-id="93be9-102">パーティション関数</span><span class="sxs-lookup"><span data-stu-id="93be9-102">Partitioned function</span></span>

<span data-ttu-id="93be9-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="93be9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="93be9-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="93be9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="93be9-105">配列を複数の部分に分割します。</span><span class="sxs-lookup"><span data-stu-id="93be9-105">Splits an array into multiple parts.</span></span>

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="93be9-106">入力</span><span class="sxs-lookup"><span data-stu-id="93be9-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="93be9-107">nElements: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="93be9-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="93be9-108">配列の各部分に含まれる要素の数</span><span class="sxs-lookup"><span data-stu-id="93be9-108">Number of elements in each part of array</span></span>


### <a name="arr--t"></a><span data-ttu-id="93be9-109">arr: ' t []</span><span class="sxs-lookup"><span data-stu-id="93be9-109">arr : 'T[]</span></span>

<span data-ttu-id="93be9-110">分割する入力配列。</span><span class="sxs-lookup"><span data-stu-id="93be9-110">Input array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="93be9-111">出力: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="93be9-111">Output : 'T[][]</span></span>

<span data-ttu-id="93be9-112">1番目の配列がの最初の配列で、 `nElements[0]` `arr` 2 番目の配列が次の配列である場合は、複数 `nElements[1]` の配列 `arr` 。最後の配列には、残りのすべての要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="93be9-112">Multiple arrays where the first array is the first `nElements[0]` of `arr` and the second array are the next `nElements[1]` of `arr` etc. The last array will contain all remaining elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="93be9-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="93be9-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="93be9-114">&</span><span class="sxs-lookup"><span data-stu-id="93be9-114">'T</span></span>

