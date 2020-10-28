---
uid: Microsoft.Quantum.Arrays.Interleaved
title: インターリーブ関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 8405cabca17f2dd7c2680833bfab5c3768fcf752
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719143"
---
# <a name="interleaved-function"></a><span data-ttu-id="68d80-102">インターリーブ関数</span><span class="sxs-lookup"><span data-stu-id="68d80-102">Interleaved function</span></span>

<span data-ttu-id="68d80-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="68d80-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="68d80-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="68d80-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="68d80-105">(ほぼ) 同じサイズの2つの配列を相互に保持します。</span><span class="sxs-lookup"><span data-stu-id="68d80-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="68d80-106">説明</span><span class="sxs-lookup"><span data-stu-id="68d80-106">Description</span></span>

<span data-ttu-id="68d80-107">この関数は、2つの配列のインターリーブを返します。最初の配列の最初の要素、2番目の配列の最初の要素、およびなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="68d80-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="68d80-108">最初の配列は、2番目の配列と同じ長さであるか、または1つ以上の要素を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="68d80-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="68d80-109">入力</span><span class="sxs-lookup"><span data-stu-id="68d80-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="68d80-110">最初: ' t []</span><span class="sxs-lookup"><span data-stu-id="68d80-110">first : 'T[]</span></span>

<span data-ttu-id="68d80-111">インターリーブされる最初の配列。</span><span class="sxs-lookup"><span data-stu-id="68d80-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="68d80-112">2番目: ' t []</span><span class="sxs-lookup"><span data-stu-id="68d80-112">second : 'T[]</span></span>

<span data-ttu-id="68d80-113">インターリーブする2番目の配列。</span><span class="sxs-lookup"><span data-stu-id="68d80-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="68d80-114">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="68d80-114">Output : 'T[]</span></span>

<span data-ttu-id="68d80-115">インターリーブ配列</span><span class="sxs-lookup"><span data-stu-id="68d80-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="68d80-116">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="68d80-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="68d80-117">&</span><span class="sxs-lookup"><span data-stu-id="68d80-117">'T</span></span>

<span data-ttu-id="68d80-118">およびの各要素の型 `first` `second` 。</span><span class="sxs-lookup"><span data-stu-id="68d80-118">The type of each element of `first` and `second`.</span></span>