---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: Moスタンドテール関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 8786250cf2f78ce2e9ff8baddc856d0bc07cb9a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718994"
---
# <a name="mostandtail-function"></a><span data-ttu-id="43fac-102">Moスタンドテール関数</span><span class="sxs-lookup"><span data-stu-id="43fac-102">MostAndTail function</span></span>

<span data-ttu-id="43fac-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="43fac-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="43fac-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="43fac-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="43fac-105">配列の最後の要素以外のすべてのタプルを返します。</span><span class="sxs-lookup"><span data-stu-id="43fac-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="43fac-106">入力</span><span class="sxs-lookup"><span data-stu-id="43fac-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="43fac-107">配列: ' A []</span><span class="sxs-lookup"><span data-stu-id="43fac-107">array : 'A[]</span></span>

<span data-ttu-id="43fac-108">少なくとも1つの要素を含む配列。</span><span class="sxs-lookup"><span data-stu-id="43fac-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="43fac-109">出力: (' A [], ' A)</span><span class="sxs-lookup"><span data-stu-id="43fac-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="43fac-110">配列の1つ以上の最後の要素のタプル。</span><span class="sxs-lookup"><span data-stu-id="43fac-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="43fac-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="43fac-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="43fac-112">' A</span><span class="sxs-lookup"><span data-stu-id="43fac-112">'A</span></span>

<span data-ttu-id="43fac-113">配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="43fac-113">The type of the array elements.</span></span>