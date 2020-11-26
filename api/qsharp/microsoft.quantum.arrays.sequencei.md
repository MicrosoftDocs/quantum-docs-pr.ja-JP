---
uid: Microsoft.Quantum.Arrays.SequenceI
title: SequenceI 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 5f03e5f2baff8077c1fa3fb5f1f079528ef0e215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220299"
---
# <a name="sequencei-function"></a><span data-ttu-id="7a263-102">SequenceI 関数</span><span class="sxs-lookup"><span data-stu-id="7a263-102">SequenceI function</span></span>

<span data-ttu-id="7a263-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7a263-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7a263-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7a263-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7a263-105">指定された間隔で整数の配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="7a263-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="7a263-106">入力</span><span class="sxs-lookup"><span data-stu-id="7a263-106">Input</span></span>

### <a name="from--int"></a><span data-ttu-id="7a263-107">開始: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7a263-107">from : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7a263-108">間隔の包括開始インデックス。</span><span class="sxs-lookup"><span data-stu-id="7a263-108">An inclusive start index of the interval.</span></span>


### <a name="to--int"></a><span data-ttu-id="7a263-109">to: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7a263-109">to : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7a263-110">より小さくない間隔の包括終了インデックス `from` 。</span><span class="sxs-lookup"><span data-stu-id="7a263-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--int"></a><span data-ttu-id="7a263-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7a263-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7a263-112">数値のシーケンス ( `from` `from + 1` ,...) を `to` 格納している配列。</span><span class="sxs-lookup"><span data-stu-id="7a263-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>