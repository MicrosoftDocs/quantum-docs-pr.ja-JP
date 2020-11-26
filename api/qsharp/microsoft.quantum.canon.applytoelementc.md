---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: ApplyToElementC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: c8d7841e3846ab435671f7959c724f987d8ad5a0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217579"
---
# <a name="applytoelementc-operation"></a><span data-ttu-id="63e49-102">ApplyToElementC 操作</span><span class="sxs-lookup"><span data-stu-id="63e49-102">ApplyToElementC operation</span></span>

<span data-ttu-id="63e49-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="63e49-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="63e49-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="63e49-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="63e49-105">配列の特定の要素に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="63e49-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="63e49-106">説明</span><span class="sxs-lookup"><span data-stu-id="63e49-106">Description</span></span>

<span data-ttu-id="63e49-107">指定された操作 `op` 、インデックス `index` 、およびターゲットの配列が適用され `targets` `op(targets[index])` ます。</span><span class="sxs-lookup"><span data-stu-id="63e49-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="63e49-108">入力</span><span class="sxs-lookup"><span data-stu-id="63e49-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="63e49-109">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="63e49-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="63e49-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="63e49-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="63e49-111">index: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="63e49-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="63e49-112">ターゲットの配列のインデックス。</span><span class="sxs-lookup"><span data-stu-id="63e49-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="63e49-113">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="63e49-113">targets : 'T[]</span></span>

<span data-ttu-id="63e49-114">に対して可能なターゲットの配列 `op` 。</span><span class="sxs-lookup"><span data-stu-id="63e49-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="63e49-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="63e49-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="63e49-116">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="63e49-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="63e49-117">&</span><span class="sxs-lookup"><span data-stu-id="63e49-117">'T</span></span>

<span data-ttu-id="63e49-118">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="63e49-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="63e49-119">参照</span><span class="sxs-lookup"><span data-stu-id="63e49-119">See Also</span></span>

- [<span data-ttu-id="63e49-120">"Microsoft....."</span><span class="sxs-lookup"><span data-stu-id="63e49-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="63e49-121">Microsoft. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="63e49-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="63e49-122">Microsoft. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="63e49-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)