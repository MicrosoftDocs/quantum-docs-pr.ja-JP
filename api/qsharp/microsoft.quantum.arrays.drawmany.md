---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 3185f2ec01a2b9d01cff82a0c4667f12483801a7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209997"
---
# <a name="drawmany-operation"></a><span data-ttu-id="f4f62-102">DrawMany 操作</span><span class="sxs-lookup"><span data-stu-id="f4f62-102">DrawMany operation</span></span>

<span data-ttu-id="f4f62-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f4f62-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f4f62-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f4f62-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f4f62-105">指定された数のサンプルに対して操作を繰り返し、配列内の出力を収集します。</span><span class="sxs-lookup"><span data-stu-id="f4f62-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="f4f62-106">入力</span><span class="sxs-lookup"><span data-stu-id="f4f62-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="f4f62-107">op: ' TInput => ' TOutput</span><span class="sxs-lookup"><span data-stu-id="f4f62-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="f4f62-108">繰り返し呼び出す操作。</span><span class="sxs-lookup"><span data-stu-id="f4f62-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="f4f62-109">nSamples: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f4f62-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f4f62-110">を呼び出して収集するサンプルの数 `op` 。</span><span class="sxs-lookup"><span data-stu-id="f4f62-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="f4f62-111">入力: ' TInput</span><span class="sxs-lookup"><span data-stu-id="f4f62-111">input : 'TInput</span></span>

<span data-ttu-id="f4f62-112">に渡される入力 `op` 。</span><span class="sxs-lookup"><span data-stu-id="f4f62-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="f4f62-113">出力: ' TOutput []</span><span class="sxs-lookup"><span data-stu-id="f4f62-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f4f62-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="f4f62-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="f4f62-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="f4f62-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="f4f62-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="f4f62-116">'TOutput</span></span>



## <a name="see-also"></a><span data-ttu-id="f4f62-117">参照</span><span class="sxs-lookup"><span data-stu-id="f4f62-117">See Also</span></span>

- [<span data-ttu-id="f4f62-118">Microsoft.................</span><span class="sxs-lookup"><span data-stu-id="f4f62-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)