---
uid: Microsoft.Quantum.Arrays.SequenceL
title: SequenceL 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 7e3c5c31428f9be152e28afbe478a3d15eb0a56c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850982"
---
# <a name="sequencel-function"></a><span data-ttu-id="5327b-102">SequenceL 関数</span><span class="sxs-lookup"><span data-stu-id="5327b-102">SequenceL function</span></span>

<span data-ttu-id="5327b-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5327b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5327b-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5327b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5327b-105">指定された間隔で整数の配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="5327b-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a><span data-ttu-id="5327b-106">入力</span><span class="sxs-lookup"><span data-stu-id="5327b-106">Input</span></span>

### <a name="from--bigint"></a><span data-ttu-id="5327b-107">開始: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5327b-107">from : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5327b-108">間隔の包括開始インデックス。</span><span class="sxs-lookup"><span data-stu-id="5327b-108">An inclusive start index of the interval.</span></span>


### <a name="to--bigint"></a><span data-ttu-id="5327b-109">to: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5327b-109">to : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5327b-110">より小さくない間隔の包括終了インデックス `from` 。</span><span class="sxs-lookup"><span data-stu-id="5327b-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="5327b-111">出力: [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span><span class="sxs-lookup"><span data-stu-id="5327b-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span></span>

<span data-ttu-id="5327b-112">数値のシーケンス ( `from` `from + 1` ,...) を `to` 格納している配列。</span><span class="sxs-lookup"><span data-stu-id="5327b-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>

## <a name="example"></a><span data-ttu-id="5327b-113">例</span><span class="sxs-lookup"><span data-stu-id="5327b-113">Example</span></span>

```qsharp
let arr1 = SequenceL(0L, 3L); // [0L, 1L, 2L, 3L]
let arr2 = SequenceL(23L, 29L); // [23L, 24L, 25L, 26L, 27L, 28L, 29L]
let arr3 = SequenceL(-5L, -2L); // [-5L, -4L, -3L, -2L]
```

## <a name="remarks"></a><span data-ttu-id="5327b-114">解説</span><span class="sxs-lookup"><span data-stu-id="5327b-114">Remarks</span></span>

<span data-ttu-id="5327b-115">との差は、 `from` `to` 値に適合する必要があり `Int` ます。</span><span class="sxs-lookup"><span data-stu-id="5327b-115">The difference between `from` and `to` must fit into an `Int` value.</span></span>