---
uid: Microsoft.Quantum.Canon.RepeatC
title: RepeatC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatC
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 30fd172584b36601c4b81deff494cf55964518f2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205441"
---
# <a name="repeatc-operation"></a><span data-ttu-id="685e6-102">RepeatC 操作</span><span class="sxs-lookup"><span data-stu-id="685e6-102">RepeatC operation</span></span>

<span data-ttu-id="685e6-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="685e6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="685e6-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="685e6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="685e6-105">指定された回数だけ操作を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="685e6-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatC<'TInput> (op : ('TInput => Unit is Ctl), nTimes : Int, input : 'TInput) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="685e6-106">入力</span><span class="sxs-lookup"><span data-stu-id="685e6-106">Input</span></span>

### <a name="op--tinput--unit--is-ctl"></a><span data-ttu-id="685e6-107">op: ' TInput => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="685e6-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="685e6-108">繰り返し呼び出す操作。</span><span class="sxs-lookup"><span data-stu-id="685e6-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="685e6-109">nTimes: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="685e6-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="685e6-110">を呼び出す回数 `op` 。</span><span class="sxs-lookup"><span data-stu-id="685e6-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="685e6-111">入力: ' TInput</span><span class="sxs-lookup"><span data-stu-id="685e6-111">input : 'TInput</span></span>

<span data-ttu-id="685e6-112">に渡される入力 `op` 。</span><span class="sxs-lookup"><span data-stu-id="685e6-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="685e6-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="685e6-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="685e6-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="685e6-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="685e6-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="685e6-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="685e6-116">参照</span><span class="sxs-lookup"><span data-stu-id="685e6-116">See Also</span></span>

- [<span data-ttu-id="685e6-117">Microsoft.... Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="685e6-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="685e6-118">Microsoft.................</span><span class="sxs-lookup"><span data-stu-id="685e6-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="685e6-119">Microsoft. RepeatA</span><span class="sxs-lookup"><span data-stu-id="685e6-119">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="685e6-120">Microsoft. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="685e6-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)