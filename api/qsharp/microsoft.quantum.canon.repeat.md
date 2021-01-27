---
uid: Microsoft.Quantum.Canon.Repeat
title: 繰り返し操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Repeat
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 40ee191e8d9044f33aa1621303c70f7e0847e8f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852239"
---
# <a name="repeat-operation"></a><span data-ttu-id="8435f-102">繰り返し操作</span><span class="sxs-lookup"><span data-stu-id="8435f-102">Repeat operation</span></span>

<span data-ttu-id="8435f-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8435f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8435f-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8435f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8435f-105">指定された回数だけ操作を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="8435f-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation Repeat<'TInput> (op : ('TInput => Unit), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="8435f-106">入力</span><span class="sxs-lookup"><span data-stu-id="8435f-106">Input</span></span>

### <a name="op--tinput--unit"></a><span data-ttu-id="8435f-107">op: ' TInput => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8435f-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="8435f-108">繰り返し呼び出す操作。</span><span class="sxs-lookup"><span data-stu-id="8435f-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="8435f-109">nTimes: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8435f-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8435f-110">を呼び出す回数 `op` 。</span><span class="sxs-lookup"><span data-stu-id="8435f-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="8435f-111">入力: ' TInput</span><span class="sxs-lookup"><span data-stu-id="8435f-111">input : 'TInput</span></span>

<span data-ttu-id="8435f-112">に渡される入力 `op` 。</span><span class="sxs-lookup"><span data-stu-id="8435f-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8435f-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8435f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8435f-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="8435f-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="8435f-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="8435f-115">'TInput</span></span>



## <a name="example"></a><span data-ttu-id="8435f-116">例</span><span class="sxs-lookup"><span data-stu-id="8435f-116">Example</span></span>

<span data-ttu-id="8435f-117">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="8435f-117">The following are equivalent:</span></span>

```qsharp
Repeat(U, 17, target);
(Bound(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a><span data-ttu-id="8435f-118">参照</span><span class="sxs-lookup"><span data-stu-id="8435f-118">See Also</span></span>

- [<span data-ttu-id="8435f-119">Microsoft.... Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="8435f-119">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="8435f-120">Microsoft. RepeatA</span><span class="sxs-lookup"><span data-stu-id="8435f-120">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="8435f-121">Microsoft. RepeatC</span><span class="sxs-lookup"><span data-stu-id="8435f-121">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="8435f-122">Microsoft. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="8435f-122">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)