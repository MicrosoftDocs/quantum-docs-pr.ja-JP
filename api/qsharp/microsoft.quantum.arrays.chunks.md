---
uid: Microsoft.Quantum.Arrays.Chunks
title: チャンク関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: 977594839a7d2fe09de8138d32a4a50e8a752390
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842875"
---
# <a name="chunks-function"></a><span data-ttu-id="d3fff-102">チャンク関数</span><span class="sxs-lookup"><span data-stu-id="d3fff-102">Chunks function</span></span>

<span data-ttu-id="d3fff-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d3fff-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d3fff-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d3fff-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d3fff-105">配列を同じ長さの複数の部分に分割します。</span><span class="sxs-lookup"><span data-stu-id="d3fff-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="d3fff-106">入力</span><span class="sxs-lookup"><span data-stu-id="d3fff-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="d3fff-107">nElements: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d3fff-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d3fff-108">各チャンクの長さ。</span><span class="sxs-lookup"><span data-stu-id="d3fff-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="d3fff-109">arr: ' t []</span><span class="sxs-lookup"><span data-stu-id="d3fff-109">arr : 'T[]</span></span>

<span data-ttu-id="d3fff-110">分割する配列。</span><span class="sxs-lookup"><span data-stu-id="d3fff-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="d3fff-111">出力: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="d3fff-111">Output : 'T[][]</span></span>

<span data-ttu-id="d3fff-112">元の配列の各チャンクを格納している配列。</span><span class="sxs-lookup"><span data-stu-id="d3fff-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d3fff-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="d3fff-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d3fff-114">&</span><span class="sxs-lookup"><span data-stu-id="d3fff-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="d3fff-115">解説</span><span class="sxs-lookup"><span data-stu-id="d3fff-115">Remarks</span></span>

<span data-ttu-id="d3fff-116">`nElements`がで割り切れない場合、出力の最後の要素はよりも短い場合があることに注意 `Length(arr)` `nElements` してください。</span><span class="sxs-lookup"><span data-stu-id="d3fff-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>