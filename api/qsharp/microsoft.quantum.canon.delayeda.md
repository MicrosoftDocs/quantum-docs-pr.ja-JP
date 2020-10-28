---
uid: Microsoft.Quantum.Canon.DelayedA
title: DelayedA 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 11c11cdd75d80d6324666ef56930f7a522121826
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716247"
---
# <a name="delayeda-function"></a><span data-ttu-id="29b01-102">DelayedA 関数</span><span class="sxs-lookup"><span data-stu-id="29b01-102">DelayedA function</span></span>

<span data-ttu-id="29b01-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="29b01-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="29b01-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="29b01-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="29b01-105">指定された引数を使用して指定された操作を適用する操作を返します。</span><span class="sxs-lookup"><span data-stu-id="29b01-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedA<'T> (op : ('T => Unit is Adj), arg : 'T) : (Unit => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="29b01-106">入力</span><span class="sxs-lookup"><span data-stu-id="29b01-106">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="29b01-107">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="29b01-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="29b01-108">戻り値を適用した結果として適用される操作</span><span class="sxs-lookup"><span data-stu-id="29b01-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="29b01-109">arg: ' t '</span><span class="sxs-lookup"><span data-stu-id="29b01-109">arg : 'T</span></span>

<span data-ttu-id="29b01-110">操作が適用される入力 `op` 。</span><span class="sxs-lookup"><span data-stu-id="29b01-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-adj"></a><span data-ttu-id="29b01-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit) => [単位](xref:microsoft.quantum.lang-ref.unit) の調整</span><span class="sxs-lookup"><span data-stu-id="29b01-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="29b01-112">入力と共に適用される新しい操作 `op``arg`</span><span class="sxs-lookup"><span data-stu-id="29b01-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="29b01-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="29b01-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="29b01-114">&</span><span class="sxs-lookup"><span data-stu-id="29b01-114">'T</span></span>

<span data-ttu-id="29b01-115">遅延する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="29b01-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="29b01-116">参照</span><span class="sxs-lookup"><span data-stu-id="29b01-116">See Also</span></span>

- [<span data-ttu-id="29b01-117">Microsoft.........</span><span class="sxs-lookup"><span data-stu-id="29b01-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="29b01-118">Microsoft. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="29b01-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)