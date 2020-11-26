---
uid: Microsoft.Quantum.Arrays.Chunks
title: チャンク関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: b323fdab1b207c72a4f46d5ca4cb368ecf0df818
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221608"
---
# <a name="chunks-function"></a><span data-ttu-id="c6f99-102">チャンク関数</span><span class="sxs-lookup"><span data-stu-id="c6f99-102">Chunks function</span></span>

<span data-ttu-id="c6f99-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c6f99-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c6f99-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c6f99-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c6f99-105">配列を同じ長さの複数の部分に分割します。</span><span class="sxs-lookup"><span data-stu-id="c6f99-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="c6f99-106">入力</span><span class="sxs-lookup"><span data-stu-id="c6f99-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="c6f99-107">nElements: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c6f99-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c6f99-108">各チャンクの長さ。</span><span class="sxs-lookup"><span data-stu-id="c6f99-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="c6f99-109">arr: ' t []</span><span class="sxs-lookup"><span data-stu-id="c6f99-109">arr : 'T[]</span></span>

<span data-ttu-id="c6f99-110">分割する配列。</span><span class="sxs-lookup"><span data-stu-id="c6f99-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="c6f99-111">出力: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="c6f99-111">Output : 'T[][]</span></span>

<span data-ttu-id="c6f99-112">元の配列の各チャンクを格納している配列。</span><span class="sxs-lookup"><span data-stu-id="c6f99-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c6f99-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="c6f99-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c6f99-114">&</span><span class="sxs-lookup"><span data-stu-id="c6f99-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="c6f99-115">解説</span><span class="sxs-lookup"><span data-stu-id="c6f99-115">Remarks</span></span>

<span data-ttu-id="c6f99-116">`nElements`がで割り切れない場合、出力の最後の要素はよりも短い場合があることに注意 `Length(arr)` `nElements` してください。</span><span class="sxs-lookup"><span data-stu-id="c6f99-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>