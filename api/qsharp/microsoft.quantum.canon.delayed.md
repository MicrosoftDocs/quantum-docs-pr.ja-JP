---
uid: Microsoft.Quantum.Canon.Delayed
title: 遅延関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 40fcc7d0a178fdb18437b4d6c96542db593347b4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840584"
---
# <a name="delayed-function"></a><span data-ttu-id="9f4a6-102">遅延関数</span><span class="sxs-lookup"><span data-stu-id="9f4a6-102">Delayed function</span></span>

<span data-ttu-id="9f4a6-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9f4a6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9f4a6-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9f4a6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9f4a6-105">指定された引数を使用して指定された操作を適用する操作を返します。</span><span class="sxs-lookup"><span data-stu-id="9f4a6-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a><span data-ttu-id="9f4a6-106">入力</span><span class="sxs-lookup"><span data-stu-id="9f4a6-106">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="9f4a6-107">op: t => ' U</span><span class="sxs-lookup"><span data-stu-id="9f4a6-107">op : 'T => 'U</span></span> 

<span data-ttu-id="9f4a6-108">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="9f4a6-108">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="9f4a6-109">arg: ' t '</span><span class="sxs-lookup"><span data-stu-id="9f4a6-109">arg : 'T</span></span>

<span data-ttu-id="9f4a6-110">操作が適用される入力。</span><span class="sxs-lookup"><span data-stu-id="9f4a6-110">The input to which the operation is applied.</span></span>



## <a name="output--unit--u"></a><span data-ttu-id="9f4a6-111">出力: [Unit](xref:microsoft.quantum.lang-ref.unit) => ' U</span><span class="sxs-lookup"><span data-stu-id="9f4a6-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => 'U</span></span> 

<span data-ttu-id="9f4a6-112">入力と共に適用される新しい操作 `op``arg`</span><span class="sxs-lookup"><span data-stu-id="9f4a6-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9f4a6-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="9f4a6-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9f4a6-114">&</span><span class="sxs-lookup"><span data-stu-id="9f4a6-114">'T</span></span>

<span data-ttu-id="9f4a6-115">遅延する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="9f4a6-115">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="9f4a6-116">' U</span><span class="sxs-lookup"><span data-stu-id="9f4a6-116">'U</span></span>

<span data-ttu-id="9f4a6-117">遅延する操作の戻り値の型。</span><span class="sxs-lookup"><span data-stu-id="9f4a6-117">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="9f4a6-118">参照</span><span class="sxs-lookup"><span data-stu-id="9f4a6-118">See Also</span></span>

- [<span data-ttu-id="9f4a6-119">Microsoft.. Canon. DelayedC</span><span class="sxs-lookup"><span data-stu-id="9f4a6-119">Microsoft.Quantum.Canon.DelayedC</span></span>](xref:Microsoft.Quantum.Canon.DelayedC)
- [<span data-ttu-id="9f4a6-120">Microsoft.. Canon. DelayedA</span><span class="sxs-lookup"><span data-stu-id="9f4a6-120">Microsoft.Quantum.Canon.DelayedA</span></span>](xref:Microsoft.Quantum.Canon.DelayedA)
- [<span data-ttu-id="9f4a6-121">Microsoft.. Canon. DelayedCA</span><span class="sxs-lookup"><span data-stu-id="9f4a6-121">Microsoft.Quantum.Canon.DelayedCA</span></span>](xref:Microsoft.Quantum.Canon.DelayedCA)
- [<span data-ttu-id="9f4a6-122">Microsoft. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="9f4a6-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)