---
uid: Microsoft.Quantum.Canon.ApplyToTailC
title: Applya c 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailC
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 5a68cae3fd122416cfd064e0078e03f5c00ab492
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217290"
---
# <a name="applytotailc-operation"></a><span data-ttu-id="25d95-102">Applya c 操作</span><span class="sxs-lookup"><span data-stu-id="25d95-102">ApplyToTailC operation</span></span>

<span data-ttu-id="25d95-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="25d95-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="25d95-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="25d95-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="25d95-105">配列の最後の要素に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="25d95-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="25d95-106">説明</span><span class="sxs-lookup"><span data-stu-id="25d95-106">Description</span></span>

<span data-ttu-id="25d95-107">指定された操作 `op` とターゲットの配列が適用され `targets` `op(Tail(targets))` ます。</span><span class="sxs-lookup"><span data-stu-id="25d95-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="25d95-108">入力</span><span class="sxs-lookup"><span data-stu-id="25d95-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="25d95-109">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="25d95-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="25d95-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="25d95-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="25d95-111">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="25d95-111">targets : 'T[]</span></span>

<span data-ttu-id="25d95-112">最後のが適用されるターゲットの配列 `op` 。</span><span class="sxs-lookup"><span data-stu-id="25d95-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="25d95-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="25d95-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="25d95-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="25d95-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="25d95-115">&</span><span class="sxs-lookup"><span data-stu-id="25d95-115">'T</span></span>

<span data-ttu-id="25d95-116">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="25d95-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="25d95-117">参照</span><span class="sxs-lookup"><span data-stu-id="25d95-117">See Also</span></span>

- [<span data-ttu-id="25d95-118">Microsoft. Canon. 適用</span><span class="sxs-lookup"><span data-stu-id="25d95-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="25d95-119">Microsoft.... "</span><span class="sxs-lookup"><span data-stu-id="25d95-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="25d95-120">Microsoft... の証明機関</span><span class="sxs-lookup"><span data-stu-id="25d95-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)