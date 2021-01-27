---
uid: Microsoft.Quantum.Canon.RepeatA
title: RepeatA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 9ae3123a64b2a886df3b7575b2840522f9b011ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852218"
---
# <a name="repeata-operation"></a><span data-ttu-id="0fa78-102">RepeatA 操作</span><span class="sxs-lookup"><span data-stu-id="0fa78-102">RepeatA operation</span></span>

<span data-ttu-id="0fa78-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0fa78-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0fa78-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0fa78-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0fa78-105">指定された回数だけ操作を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0fa78-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="0fa78-106">入力</span><span class="sxs-lookup"><span data-stu-id="0fa78-106">Input</span></span>

### <a name="op--tinput--unit--is-adj"></a><span data-ttu-id="0fa78-107">op: ' TInput => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="0fa78-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="0fa78-108">繰り返し呼び出す操作。</span><span class="sxs-lookup"><span data-stu-id="0fa78-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="0fa78-109">nTimes: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0fa78-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0fa78-110">を呼び出す回数 `op` 。</span><span class="sxs-lookup"><span data-stu-id="0fa78-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="0fa78-111">入力: ' TInput</span><span class="sxs-lookup"><span data-stu-id="0fa78-111">input : 'TInput</span></span>

<span data-ttu-id="0fa78-112">に渡される入力 `op` 。</span><span class="sxs-lookup"><span data-stu-id="0fa78-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0fa78-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0fa78-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0fa78-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="0fa78-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="0fa78-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="0fa78-115">'TInput</span></span>



## <a name="example"></a><span data-ttu-id="0fa78-116">例</span><span class="sxs-lookup"><span data-stu-id="0fa78-116">Example</span></span>

<span data-ttu-id="0fa78-117">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="0fa78-117">The following are equivalent:</span></span>

```qsharp
RepeatA(U, 17, target);
(BoundA(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a><span data-ttu-id="0fa78-118">参照</span><span class="sxs-lookup"><span data-stu-id="0fa78-118">See Also</span></span>

- [<span data-ttu-id="0fa78-119">Microsoft.... Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="0fa78-119">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="0fa78-120">Microsoft.................</span><span class="sxs-lookup"><span data-stu-id="0fa78-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="0fa78-121">Microsoft. RepeatC</span><span class="sxs-lookup"><span data-stu-id="0fa78-121">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="0fa78-122">Microsoft. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="0fa78-122">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)