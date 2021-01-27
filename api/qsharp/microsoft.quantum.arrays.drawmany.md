---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: bf63ce308679cef97c776d3383ff732ed4d4e500
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846203"
---
# <a name="drawmany-operation"></a><span data-ttu-id="afd87-102">DrawMany 操作</span><span class="sxs-lookup"><span data-stu-id="afd87-102">DrawMany operation</span></span>

<span data-ttu-id="afd87-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="afd87-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="afd87-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="afd87-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="afd87-105">指定された数のサンプルに対して操作を繰り返し、配列内の出力を収集します。</span><span class="sxs-lookup"><span data-stu-id="afd87-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="afd87-106">入力</span><span class="sxs-lookup"><span data-stu-id="afd87-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="afd87-107">op: ' TInput => ' TOutput</span><span class="sxs-lookup"><span data-stu-id="afd87-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="afd87-108">繰り返し呼び出す操作。</span><span class="sxs-lookup"><span data-stu-id="afd87-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="afd87-109">nSamples: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="afd87-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="afd87-110">を呼び出して収集するサンプルの数 `op` 。</span><span class="sxs-lookup"><span data-stu-id="afd87-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="afd87-111">入力: ' TInput</span><span class="sxs-lookup"><span data-stu-id="afd87-111">input : 'TInput</span></span>

<span data-ttu-id="afd87-112">に渡される入力 `op` 。</span><span class="sxs-lookup"><span data-stu-id="afd87-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="afd87-113">出力: ' TOutput []</span><span class="sxs-lookup"><span data-stu-id="afd87-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="afd87-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="afd87-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="afd87-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="afd87-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="afd87-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="afd87-116">'TOutput</span></span>



## <a name="example"></a><span data-ttu-id="afd87-117">例</span><span class="sxs-lookup"><span data-stu-id="afd87-117">Example</span></span>

<span data-ttu-id="afd87-118">次の例では、一度に1ビットをサンプリングする操作を指定して、整数を示します。</span><span class="sxs-lookup"><span data-stu-id="afd87-118">The following samples an integer, given an operation that samples a single bit at a time.</span></span>

```qsharp
let randomInteger = BoolArrayAsInt(DrawMany(SampleRandomBit, 16, ()));
```

## <a name="see-also"></a><span data-ttu-id="afd87-119">参照</span><span class="sxs-lookup"><span data-stu-id="afd87-119">See Also</span></span>

- [<span data-ttu-id="afd87-120">Microsoft.................</span><span class="sxs-lookup"><span data-stu-id="afd87-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)