---
uid: Microsoft.Quantum.Canon.RepeatA
title: RepeatA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 89d34e5a30a61dee392904ce1076605432e21395
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715561"
---
# <a name="repeata-operation"></a><span data-ttu-id="4048e-102">RepeatA 操作</span><span class="sxs-lookup"><span data-stu-id="4048e-102">RepeatA operation</span></span>

<span data-ttu-id="4048e-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4048e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4048e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4048e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4048e-105">指定された回数だけ操作を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="4048e-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="4048e-106">入力</span><span class="sxs-lookup"><span data-stu-id="4048e-106">Input</span></span>

### <a name="op--tinput--unit-adj"></a><span data-ttu-id="4048e-107">op: ' TInput => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="4048e-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="4048e-108">繰り返し呼び出す操作。</span><span class="sxs-lookup"><span data-stu-id="4048e-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="4048e-109">nTimes: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4048e-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4048e-110">を呼び出す回数 `op` 。</span><span class="sxs-lookup"><span data-stu-id="4048e-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="4048e-111">入力: ' TInput</span><span class="sxs-lookup"><span data-stu-id="4048e-111">input : 'TInput</span></span>

<span data-ttu-id="4048e-112">に渡される入力 `op` 。</span><span class="sxs-lookup"><span data-stu-id="4048e-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4048e-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4048e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4048e-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="4048e-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="4048e-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="4048e-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="4048e-116">参照</span><span class="sxs-lookup"><span data-stu-id="4048e-116">See Also</span></span>

- [<span data-ttu-id="4048e-117">Microsoft.... Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="4048e-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="4048e-118">Microsoft.................</span><span class="sxs-lookup"><span data-stu-id="4048e-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="4048e-119">Microsoft. RepeatC</span><span class="sxs-lookup"><span data-stu-id="4048e-119">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="4048e-120">Microsoft. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="4048e-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)