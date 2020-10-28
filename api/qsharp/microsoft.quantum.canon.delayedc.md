---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 7cfd77b0bb2d91c5a1c4bb5bc84e052421d733a9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716214"
---
# <a name="delayedc-function"></a><span data-ttu-id="6c42c-102">DelayedC 関数</span><span class="sxs-lookup"><span data-stu-id="6c42c-102">DelayedC function</span></span>

<span data-ttu-id="6c42c-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6c42c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6c42c-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6c42c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6c42c-105">指定された引数を使用して指定された操作を適用する操作を返します。</span><span class="sxs-lookup"><span data-stu-id="6c42c-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="6c42c-106">入力</span><span class="sxs-lookup"><span data-stu-id="6c42c-106">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="6c42c-107">op: ' t => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="6c42c-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="6c42c-108">戻り値を適用した結果として適用される操作</span><span class="sxs-lookup"><span data-stu-id="6c42c-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="6c42c-109">arg: ' t '</span><span class="sxs-lookup"><span data-stu-id="6c42c-109">arg : 'T</span></span>

<span data-ttu-id="6c42c-110">操作が適用される入力 `op` 。</span><span class="sxs-lookup"><span data-stu-id="6c42c-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-ctl"></a><span data-ttu-id="6c42c-111">出力: [ユニット](xref:microsoft.quantum.lang-ref.unit) => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="6c42c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="6c42c-112">入力と共に適用される新しい操作 `op``arg`</span><span class="sxs-lookup"><span data-stu-id="6c42c-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6c42c-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="6c42c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6c42c-114">&</span><span class="sxs-lookup"><span data-stu-id="6c42c-114">'T</span></span>

<span data-ttu-id="6c42c-115">遅延する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="6c42c-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c42c-116">参照</span><span class="sxs-lookup"><span data-stu-id="6c42c-116">See Also</span></span>

- [<span data-ttu-id="6c42c-117">Microsoft.........</span><span class="sxs-lookup"><span data-stu-id="6c42c-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="6c42c-118">Microsoft. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="6c42c-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)