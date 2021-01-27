---
uid: Microsoft.Quantum.Canon.ApplyToElement
title: ApplyToElement 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElement
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 5159eee07f7398cc6194c9907a37b78a63aaf263
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850786"
---
# <a name="applytoelement-operation"></a><span data-ttu-id="ec06d-102">ApplyToElement 操作</span><span class="sxs-lookup"><span data-stu-id="ec06d-102">ApplyToElement operation</span></span>

<span data-ttu-id="ec06d-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ec06d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ec06d-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ec06d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ec06d-105">配列の特定の要素に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="ec06d-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElement<'T> (op : ('T => Unit), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="ec06d-106">説明</span><span class="sxs-lookup"><span data-stu-id="ec06d-106">Description</span></span>

<span data-ttu-id="ec06d-107">指定された操作 `op` 、インデックス `index` 、およびターゲットの配列が適用され `targets` `op(targets[index])` ます。</span><span class="sxs-lookup"><span data-stu-id="ec06d-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="ec06d-108">入力</span><span class="sxs-lookup"><span data-stu-id="ec06d-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="ec06d-109">op: t => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ec06d-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ec06d-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="ec06d-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="ec06d-111">index: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ec06d-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ec06d-112">ターゲットの配列のインデックス。</span><span class="sxs-lookup"><span data-stu-id="ec06d-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="ec06d-113">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="ec06d-113">targets : 'T[]</span></span>

<span data-ttu-id="ec06d-114">に対して可能なターゲットの配列 `op` 。</span><span class="sxs-lookup"><span data-stu-id="ec06d-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ec06d-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ec06d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ec06d-116">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="ec06d-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ec06d-117">&</span><span class="sxs-lookup"><span data-stu-id="ec06d-117">'T</span></span>

<span data-ttu-id="ec06d-118">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="ec06d-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec06d-119">参照</span><span class="sxs-lookup"><span data-stu-id="ec06d-119">See Also</span></span>

- [<span data-ttu-id="ec06d-120">Microsoft. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="ec06d-120">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="ec06d-121">Microsoft. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="ec06d-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="ec06d-122">Microsoft. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="ec06d-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)