---
uid: Microsoft.Quantum.Canon.Repeat
title: 繰り返し操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Repeat
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 5aedd056b851b8d8d7c25a32eb22587292e132a8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715598"
---
# <a name="repeat-operation"></a><span data-ttu-id="82fde-102">繰り返し操作</span><span class="sxs-lookup"><span data-stu-id="82fde-102">Repeat operation</span></span>

<span data-ttu-id="82fde-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="82fde-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="82fde-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="82fde-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="82fde-105">指定された回数だけ操作を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="82fde-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation Repeat<'TInput> (op : ('TInput => Unit), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="82fde-106">入力</span><span class="sxs-lookup"><span data-stu-id="82fde-106">Input</span></span>

### <a name="op--tinput--unit"></a><span data-ttu-id="82fde-107">op: ' TInput => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="82fde-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="82fde-108">繰り返し呼び出す操作。</span><span class="sxs-lookup"><span data-stu-id="82fde-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="82fde-109">nTimes: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="82fde-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="82fde-110">を呼び出す回数 `op` 。</span><span class="sxs-lookup"><span data-stu-id="82fde-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="82fde-111">入力: ' TInput</span><span class="sxs-lookup"><span data-stu-id="82fde-111">input : 'TInput</span></span>

<span data-ttu-id="82fde-112">に渡される入力 `op` 。</span><span class="sxs-lookup"><span data-stu-id="82fde-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="82fde-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="82fde-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="82fde-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="82fde-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="82fde-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="82fde-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="82fde-116">参照</span><span class="sxs-lookup"><span data-stu-id="82fde-116">See Also</span></span>

- [<span data-ttu-id="82fde-117">Microsoft.... Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="82fde-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="82fde-118">Microsoft. RepeatA</span><span class="sxs-lookup"><span data-stu-id="82fde-118">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="82fde-119">Microsoft. RepeatC</span><span class="sxs-lookup"><span data-stu-id="82fde-119">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="82fde-120">Microsoft. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="82fde-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)