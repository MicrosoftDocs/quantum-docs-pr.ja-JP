---
uid: Microsoft.Quantum.Canon.ApplyToTailCA
title: Ca の適用操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailCA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: afb9eaa277814d7434b00a5c853a0c002190c1ae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207855"
---
# <a name="applytotailca-operation"></a><span data-ttu-id="e85b2-102">Ca の適用操作</span><span class="sxs-lookup"><span data-stu-id="e85b2-102">ApplyToTailCA operation</span></span>

<span data-ttu-id="e85b2-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e85b2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e85b2-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e85b2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e85b2-105">配列の最後の要素に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="e85b2-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="e85b2-106">説明</span><span class="sxs-lookup"><span data-stu-id="e85b2-106">Description</span></span>

<span data-ttu-id="e85b2-107">指定された操作 `op` とターゲットの配列が適用され `targets` `op(Tail(targets))` ます。</span><span class="sxs-lookup"><span data-stu-id="e85b2-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="e85b2-108">入力</span><span class="sxs-lookup"><span data-stu-id="e85b2-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="e85b2-109">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="e85b2-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="e85b2-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="e85b2-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="e85b2-111">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="e85b2-111">targets : 'T[]</span></span>

<span data-ttu-id="e85b2-112">最後のが適用されるターゲットの配列 `op` 。</span><span class="sxs-lookup"><span data-stu-id="e85b2-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e85b2-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e85b2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e85b2-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="e85b2-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e85b2-115">&</span><span class="sxs-lookup"><span data-stu-id="e85b2-115">'T</span></span>

<span data-ttu-id="e85b2-116">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="e85b2-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="e85b2-117">参照</span><span class="sxs-lookup"><span data-stu-id="e85b2-117">See Also</span></span>

- [<span data-ttu-id="e85b2-118">Microsoft. Canon. 適用</span><span class="sxs-lookup"><span data-stu-id="e85b2-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="e85b2-119">Microsoft.... "</span><span class="sxs-lookup"><span data-stu-id="e85b2-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="e85b2-120">Microsoft......。</span><span class="sxs-lookup"><span data-stu-id="e85b2-120">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)