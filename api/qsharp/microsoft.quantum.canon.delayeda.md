---
uid: Microsoft.Quantum.Canon.DelayedA
title: DelayedA 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 33ff4dab36a6c6e17b9496a623f70b814c9f2fed
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207073"
---
# <a name="delayeda-function"></a><span data-ttu-id="57cd8-102">DelayedA 関数</span><span class="sxs-lookup"><span data-stu-id="57cd8-102">DelayedA function</span></span>

<span data-ttu-id="57cd8-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="57cd8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="57cd8-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="57cd8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="57cd8-105">指定された引数を使用して指定された操作を適用する操作を返します。</span><span class="sxs-lookup"><span data-stu-id="57cd8-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedA<'T> (op : ('T => Unit is Adj), arg : 'T) : (Unit => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="57cd8-106">入力</span><span class="sxs-lookup"><span data-stu-id="57cd8-106">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="57cd8-107">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="57cd8-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="57cd8-108">戻り値を適用した結果として適用される操作</span><span class="sxs-lookup"><span data-stu-id="57cd8-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="57cd8-109">arg: ' t '</span><span class="sxs-lookup"><span data-stu-id="57cd8-109">arg : 'T</span></span>

<span data-ttu-id="57cd8-110">操作が適用される入力 `op` 。</span><span class="sxs-lookup"><span data-stu-id="57cd8-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-adj"></a><span data-ttu-id="57cd8-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="57cd8-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="57cd8-112">入力と共に適用される新しい操作 `op``arg`</span><span class="sxs-lookup"><span data-stu-id="57cd8-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="57cd8-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="57cd8-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="57cd8-114">&</span><span class="sxs-lookup"><span data-stu-id="57cd8-114">'T</span></span>

<span data-ttu-id="57cd8-115">遅延する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="57cd8-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="57cd8-116">参照</span><span class="sxs-lookup"><span data-stu-id="57cd8-116">See Also</span></span>

- [<span data-ttu-id="57cd8-117">Microsoft.........</span><span class="sxs-lookup"><span data-stu-id="57cd8-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="57cd8-118">Microsoft. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="57cd8-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)