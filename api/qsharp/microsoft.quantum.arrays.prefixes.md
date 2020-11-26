---
uid: Microsoft.Quantum.Arrays.Prefixes
title: プレフィックス関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 3501c11437534b1623bffba272a4517487e5634a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220392"
---
# <a name="prefixes-function"></a><span data-ttu-id="de1e6-102">プレフィックス関数</span><span class="sxs-lookup"><span data-stu-id="de1e6-102">Prefixes function</span></span>

<span data-ttu-id="de1e6-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="de1e6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="de1e6-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="de1e6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="de1e6-105">配列を指定すると、そのすべてのプレフィックスが返されます。</span><span class="sxs-lookup"><span data-stu-id="de1e6-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="de1e6-106">説明</span><span class="sxs-lookup"><span data-stu-id="de1e6-106">Description</span></span>

<span data-ttu-id="de1e6-107">すべてのプレフィックスの配列を返します。最初の要素が配列全体になるまで、最初の要素のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="de1e6-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="de1e6-108">入力</span><span class="sxs-lookup"><span data-stu-id="de1e6-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="de1e6-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="de1e6-109">array : 'T[]</span></span>

<span data-ttu-id="de1e6-110">要素の配列。</span><span class="sxs-lookup"><span data-stu-id="de1e6-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="de1e6-111">出力: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="de1e6-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="de1e6-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="de1e6-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="de1e6-113">&</span><span class="sxs-lookup"><span data-stu-id="de1e6-113">'T</span></span>

<span data-ttu-id="de1e6-114">要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="de1e6-114">The type of `array` elements.</span></span>