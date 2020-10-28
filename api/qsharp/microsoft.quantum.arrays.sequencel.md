---
uid: Microsoft.Quantum.Arrays.SequenceL
title: SequenceL 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5ce63575e703341fce42c0be393765c342bbd89
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718879"
---
# <a name="sequencel-function"></a><span data-ttu-id="5d5de-102">SequenceL 関数</span><span class="sxs-lookup"><span data-stu-id="5d5de-102">SequenceL function</span></span>

<span data-ttu-id="5d5de-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5d5de-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5d5de-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5d5de-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5d5de-105">指定された間隔で整数の配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="5d5de-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a><span data-ttu-id="5d5de-106">入力</span><span class="sxs-lookup"><span data-stu-id="5d5de-106">Input</span></span>

### <a name="from--bigint"></a><span data-ttu-id="5d5de-107">開始: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5d5de-107">from : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5d5de-108">間隔の包括開始インデックス。</span><span class="sxs-lookup"><span data-stu-id="5d5de-108">An inclusive start index of the interval.</span></span>


### <a name="to--bigint"></a><span data-ttu-id="5d5de-109">to: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5d5de-109">to : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5d5de-110">より小さくない間隔の包括終了インデックス `from` 。</span><span class="sxs-lookup"><span data-stu-id="5d5de-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="5d5de-111">出力: [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span><span class="sxs-lookup"><span data-stu-id="5d5de-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span></span>

<span data-ttu-id="5d5de-112">数値のシーケンス ( `from` `from + 1` ,...) を `to` 格納している配列。</span><span class="sxs-lookup"><span data-stu-id="5d5de-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5d5de-113">解説</span><span class="sxs-lookup"><span data-stu-id="5d5de-113">Remarks</span></span>

<span data-ttu-id="5d5de-114">との差は、 `from` `to` 値に適合する必要があり `Int` ます。</span><span class="sxs-lookup"><span data-stu-id="5d5de-114">The difference between `from` and `to` must fit into an `Int` value.</span></span>