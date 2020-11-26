---
uid: Microsoft.Quantum.Canon.RepeatA
title: RepeatA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 5f418f67d7265d4cb39b3636906c74d33d80f472
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205560"
---
# <a name="repeata-operation"></a><span data-ttu-id="65839-102">RepeatA 操作</span><span class="sxs-lookup"><span data-stu-id="65839-102">RepeatA operation</span></span>

<span data-ttu-id="65839-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="65839-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="65839-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="65839-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="65839-105">指定された回数だけ操作を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="65839-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="65839-106">入力</span><span class="sxs-lookup"><span data-stu-id="65839-106">Input</span></span>

### <a name="op--tinput--unit--is-adj"></a><span data-ttu-id="65839-107">op: ' TInput => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="65839-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="65839-108">繰り返し呼び出す操作。</span><span class="sxs-lookup"><span data-stu-id="65839-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="65839-109">nTimes: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="65839-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="65839-110">を呼び出す回数 `op` 。</span><span class="sxs-lookup"><span data-stu-id="65839-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="65839-111">入力: ' TInput</span><span class="sxs-lookup"><span data-stu-id="65839-111">input : 'TInput</span></span>

<span data-ttu-id="65839-112">に渡される入力 `op` 。</span><span class="sxs-lookup"><span data-stu-id="65839-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="65839-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="65839-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="65839-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="65839-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="65839-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="65839-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="65839-116">参照</span><span class="sxs-lookup"><span data-stu-id="65839-116">See Also</span></span>

- [<span data-ttu-id="65839-117">Microsoft.... Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="65839-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="65839-118">Microsoft.................</span><span class="sxs-lookup"><span data-stu-id="65839-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="65839-119">Microsoft. RepeatC</span><span class="sxs-lookup"><span data-stu-id="65839-119">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="65839-120">Microsoft. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="65839-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)