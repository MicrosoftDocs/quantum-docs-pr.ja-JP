---
uid: Microsoft.Quantum.Arrays.Prefixes
title: プレフィックス関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 1576e57e9dc64a605eb65cb841640e72a3b126ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718939"
---
# <a name="prefixes-function"></a><span data-ttu-id="4b41b-102">プレフィックス関数</span><span class="sxs-lookup"><span data-stu-id="4b41b-102">Prefixes function</span></span>

<span data-ttu-id="4b41b-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4b41b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4b41b-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4b41b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4b41b-105">配列を指定すると、そのすべてのプレフィックスが返されます。</span><span class="sxs-lookup"><span data-stu-id="4b41b-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="4b41b-106">説明</span><span class="sxs-lookup"><span data-stu-id="4b41b-106">Description</span></span>

<span data-ttu-id="4b41b-107">すべてのプレフィックスの配列を返します。最初の要素が配列全体になるまで、最初の要素のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b41b-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="4b41b-108">入力</span><span class="sxs-lookup"><span data-stu-id="4b41b-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="4b41b-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="4b41b-109">array : 'T[]</span></span>

<span data-ttu-id="4b41b-110">要素の配列。</span><span class="sxs-lookup"><span data-stu-id="4b41b-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="4b41b-111">出力: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="4b41b-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4b41b-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="4b41b-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4b41b-113">&</span><span class="sxs-lookup"><span data-stu-id="4b41b-113">'T</span></span>

<span data-ttu-id="4b41b-114">要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="4b41b-114">The type of `array` elements.</span></span>