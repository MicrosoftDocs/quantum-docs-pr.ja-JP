---
uid: Microsoft.Quantum.Arrays.Chunks
title: チャンク関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: fe10999d35ed05908fd59b9dad8b5c0c51233ae6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719467"
---
# <a name="chunks-function"></a><span data-ttu-id="e8a73-102">チャンク関数</span><span class="sxs-lookup"><span data-stu-id="e8a73-102">Chunks function</span></span>

<span data-ttu-id="e8a73-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e8a73-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e8a73-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e8a73-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e8a73-105">配列を同じ長さの複数の部分に分割します。</span><span class="sxs-lookup"><span data-stu-id="e8a73-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="e8a73-106">入力</span><span class="sxs-lookup"><span data-stu-id="e8a73-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="e8a73-107">nElements: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e8a73-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e8a73-108">各チャンクの長さ。</span><span class="sxs-lookup"><span data-stu-id="e8a73-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="e8a73-109">arr: ' t []</span><span class="sxs-lookup"><span data-stu-id="e8a73-109">arr : 'T[]</span></span>

<span data-ttu-id="e8a73-110">分割する配列。</span><span class="sxs-lookup"><span data-stu-id="e8a73-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="e8a73-111">出力: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="e8a73-111">Output : 'T[][]</span></span>

<span data-ttu-id="e8a73-112">元の配列の各チャンクを格納している配列。</span><span class="sxs-lookup"><span data-stu-id="e8a73-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e8a73-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="e8a73-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e8a73-114">&</span><span class="sxs-lookup"><span data-stu-id="e8a73-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="e8a73-115">解説</span><span class="sxs-lookup"><span data-stu-id="e8a73-115">Remarks</span></span>

<span data-ttu-id="e8a73-116">`nElements`がで割り切れない場合、出力の最後の要素はよりも短い場合があることに注意 `Length(arr)` `nElements` してください。</span><span class="sxs-lookup"><span data-stu-id="e8a73-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>