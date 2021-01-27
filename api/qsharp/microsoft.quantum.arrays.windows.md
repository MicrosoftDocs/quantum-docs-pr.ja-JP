---
uid: Microsoft.Quantum.Arrays.Windows
title: Windows 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: adfea2b9a2f6c22446817538d29586284dba723e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842192"
---
# <a name="windows-function"></a><span data-ttu-id="77538-102">Windows 関数</span><span class="sxs-lookup"><span data-stu-id="77538-102">Windows function</span></span>

<span data-ttu-id="77538-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="77538-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="77538-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="77538-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="77538-105">長さの連続するすべてのサブを返し `size` ます。</span><span class="sxs-lookup"><span data-stu-id="77538-105">Returns all consecutive subarrays of length `size`.</span></span>

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="77538-106">説明</span><span class="sxs-lookup"><span data-stu-id="77538-106">Description</span></span>

<span data-ttu-id="77538-107">この関数 `n - size + 1` は、すべての長さのサブを返し `size` ます。ここで、 `n` はの長さ `arr` です。</span><span class="sxs-lookup"><span data-stu-id="77538-107">This function returns all `n - size + 1` subarrays of length `size` in order, where `n` is the length of `arr`.</span></span>
<span data-ttu-id="77538-108">最初のサブは、最後のサブ `arr[0..size - 1], arr[1..size], arr[2..size + 1]` 配列まで `arr[n - size..n - 1]` です。</span><span class="sxs-lookup"><span data-stu-id="77538-108">The first subarrays are `arr[0..size - 1], arr[1..size], arr[2..size + 1]` until the last subarray `arr[n - size..n - 1]`.</span></span>

<span data-ttu-id="77538-109">`size <= 0`または `size > n` の場合は、空の配列が返されます。</span><span class="sxs-lookup"><span data-stu-id="77538-109">If `size <= 0` or `size > n`, an empty array is returned.</span></span>

## <a name="input"></a><span data-ttu-id="77538-110">入力</span><span class="sxs-lookup"><span data-stu-id="77538-110">Input</span></span>

### <a name="size--int"></a><span data-ttu-id="77538-111">サイズ: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="77538-111">size : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="77538-112">サブの長さ。</span><span class="sxs-lookup"><span data-stu-id="77538-112">Length of the subarrays.</span></span>


### <a name="array--t"></a><span data-ttu-id="77538-113">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="77538-113">array : 'T[]</span></span>

<span data-ttu-id="77538-114">要素の配列。</span><span class="sxs-lookup"><span data-stu-id="77538-114">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="77538-115">出力: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="77538-115">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="77538-116">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="77538-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="77538-117">&</span><span class="sxs-lookup"><span data-stu-id="77538-117">'T</span></span>

<span data-ttu-id="77538-118">要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="77538-118">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="77538-119">例</span><span class="sxs-lookup"><span data-stu-id="77538-119">Example</span></span>

```qsharp
// same as [[1, 2, 3], [2, 3, 4], [3, 4, 5]]
let windows = Windows(3, [1, 2, 3, 4, 5]);
```