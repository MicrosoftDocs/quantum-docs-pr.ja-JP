---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: ヘッド Andrest 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 9af4ba48a21d3cdf932b2f702051a70a6108db1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719179"
---
# <a name="headandrest-function"></a><span data-ttu-id="e118c-102">ヘッド Andrest 関数</span><span class="sxs-lookup"><span data-stu-id="e118c-102">HeadAndRest function</span></span>

<span data-ttu-id="e118c-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e118c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e118c-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e118c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e118c-105">配列の最初の要素と残りのすべての要素の組を返します。</span><span class="sxs-lookup"><span data-stu-id="e118c-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="e118c-106">入力</span><span class="sxs-lookup"><span data-stu-id="e118c-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="e118c-107">配列: ' A []</span><span class="sxs-lookup"><span data-stu-id="e118c-107">array : 'A[]</span></span>

<span data-ttu-id="e118c-108">少なくとも1つの要素を含む配列。</span><span class="sxs-lookup"><span data-stu-id="e118c-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="e118c-109">出力: (' A, ' A [])</span><span class="sxs-lookup"><span data-stu-id="e118c-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="e118c-110">配列の最初の要素と残りのすべての要素のタプル。</span><span class="sxs-lookup"><span data-stu-id="e118c-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e118c-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="e118c-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="e118c-112">' A</span><span class="sxs-lookup"><span data-stu-id="e118c-112">'A</span></span>

<span data-ttu-id="e118c-113">配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="e118c-113">The type of the array elements.</span></span>