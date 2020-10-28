---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 601fe603a869dcf977c1ceade5819ee64f634d53
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719371"
---
# <a name="drawmany-operation"></a><span data-ttu-id="393aa-102">DrawMany 操作</span><span class="sxs-lookup"><span data-stu-id="393aa-102">DrawMany operation</span></span>

<span data-ttu-id="393aa-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="393aa-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="393aa-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="393aa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="393aa-105">指定された数のサンプルに対して操作を繰り返し、配列内の出力を収集します。</span><span class="sxs-lookup"><span data-stu-id="393aa-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="393aa-106">入力</span><span class="sxs-lookup"><span data-stu-id="393aa-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="393aa-107">op: ' TInput => ' TOutput</span><span class="sxs-lookup"><span data-stu-id="393aa-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="393aa-108">繰り返し呼び出す操作。</span><span class="sxs-lookup"><span data-stu-id="393aa-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="393aa-109">nSamples: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="393aa-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="393aa-110">を呼び出して収集するサンプルの数 `op` 。</span><span class="sxs-lookup"><span data-stu-id="393aa-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="393aa-111">入力: ' TInput</span><span class="sxs-lookup"><span data-stu-id="393aa-111">input : 'TInput</span></span>

<span data-ttu-id="393aa-112">に渡される入力 `op` 。</span><span class="sxs-lookup"><span data-stu-id="393aa-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="393aa-113">出力: ' TOutput []</span><span class="sxs-lookup"><span data-stu-id="393aa-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="393aa-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="393aa-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="393aa-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="393aa-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="393aa-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="393aa-116">'TOutput</span></span>



## <a name="see-also"></a><span data-ttu-id="393aa-117">参照</span><span class="sxs-lookup"><span data-stu-id="393aa-117">See Also</span></span>

- [<span data-ttu-id="393aa-118">Microsoft.................</span><span class="sxs-lookup"><span data-stu-id="393aa-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)