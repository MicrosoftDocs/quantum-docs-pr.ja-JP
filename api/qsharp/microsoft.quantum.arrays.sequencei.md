---
uid: Microsoft.Quantum.Arrays.SequenceI
title: SequenceI 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5dc4377c696e14b505c63701c2f5ca0dadca672
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718898"
---
# <a name="sequencei-function"></a><span data-ttu-id="e1462-102">SequenceI 関数</span><span class="sxs-lookup"><span data-stu-id="e1462-102">SequenceI function</span></span>

<span data-ttu-id="e1462-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e1462-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e1462-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e1462-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e1462-105">指定された間隔で整数の配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="e1462-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="e1462-106">入力</span><span class="sxs-lookup"><span data-stu-id="e1462-106">Input</span></span>

### <a name="from--int"></a><span data-ttu-id="e1462-107">開始: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e1462-107">from : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e1462-108">間隔の包括開始インデックス。</span><span class="sxs-lookup"><span data-stu-id="e1462-108">An inclusive start index of the interval.</span></span>


### <a name="to--int"></a><span data-ttu-id="e1462-109">to: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e1462-109">to : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e1462-110">より小さくない間隔の包括終了インデックス `from` 。</span><span class="sxs-lookup"><span data-stu-id="e1462-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--int"></a><span data-ttu-id="e1462-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e1462-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e1462-112">数値のシーケンス ( `from` `from + 1` ,...) を `to` 格納している配列。</span><span class="sxs-lookup"><span data-stu-id="e1462-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>