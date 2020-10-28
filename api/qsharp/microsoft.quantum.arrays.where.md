---
uid: Microsoft.Quantum.Arrays.Where
title: Where 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 1c9fa0463ed49788d12502257d735b965565d1ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718754"
---
# <a name="where-function"></a><span data-ttu-id="f8329-102">Where 関数</span><span class="sxs-lookup"><span data-stu-id="f8329-102">Where function</span></span>

<span data-ttu-id="f8329-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f8329-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f8329-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f8329-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f8329-105">述語と配列が指定されている場合、述語が true である配列のインデックスを返します。</span><span class="sxs-lookup"><span data-stu-id="f8329-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="f8329-106">入力</span><span class="sxs-lookup"><span data-stu-id="f8329-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="f8329-107">述語: > [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f8329-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f8329-108">`'T`要素をフィルター処理するために使用されるブール値からブール型への関数。</span><span class="sxs-lookup"><span data-stu-id="f8329-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="f8329-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="f8329-109">array : 'T[]</span></span>

<span data-ttu-id="f8329-110">上の要素の配列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="f8329-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="f8329-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f8329-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f8329-112">が true であるインデックスの配列。 `predicate`</span><span class="sxs-lookup"><span data-stu-id="f8329-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f8329-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="f8329-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f8329-114">&</span><span class="sxs-lookup"><span data-stu-id="f8329-114">'T</span></span>

<span data-ttu-id="f8329-115">要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="f8329-115">The type of `array` elements.</span></span>