---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: d8036397559b1587b806f701d89e892eea2da8f9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207015"
---
# <a name="delayedc-function"></a><span data-ttu-id="bd626-102">DelayedC 関数</span><span class="sxs-lookup"><span data-stu-id="bd626-102">DelayedC function</span></span>

<span data-ttu-id="bd626-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bd626-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bd626-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bd626-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bd626-105">指定された引数を使用して指定された操作を適用する操作を返します。</span><span class="sxs-lookup"><span data-stu-id="bd626-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="bd626-106">入力</span><span class="sxs-lookup"><span data-stu-id="bd626-106">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="bd626-107">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="bd626-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="bd626-108">戻り値を適用した結果として適用される操作</span><span class="sxs-lookup"><span data-stu-id="bd626-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="bd626-109">arg: ' t '</span><span class="sxs-lookup"><span data-stu-id="bd626-109">arg : 'T</span></span>

<span data-ttu-id="bd626-110">操作が適用される入力 `op` 。</span><span class="sxs-lookup"><span data-stu-id="bd626-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-ctl"></a><span data-ttu-id="bd626-111">出力: [ユニット](xref:microsoft.quantum.lang-ref.unit) => [ユニット](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="bd626-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="bd626-112">入力と共に適用される新しい操作 `op``arg`</span><span class="sxs-lookup"><span data-stu-id="bd626-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bd626-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="bd626-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bd626-114">&</span><span class="sxs-lookup"><span data-stu-id="bd626-114">'T</span></span>

<span data-ttu-id="bd626-115">遅延する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="bd626-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd626-116">参照</span><span class="sxs-lookup"><span data-stu-id="bd626-116">See Also</span></span>

- [<span data-ttu-id="bd626-117">Microsoft.........</span><span class="sxs-lookup"><span data-stu-id="bd626-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="bd626-118">Microsoft. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="bd626-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)