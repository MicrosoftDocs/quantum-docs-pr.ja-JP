---
uid: Microsoft.Quantum.Canon.ApplyToElement
title: ApplyToElement 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElement
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 5c321d95c9b79bc50827c2b50c406b164e143dc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717507"
---
# <a name="applytoelement-operation"></a><span data-ttu-id="ab382-102">ApplyToElement 操作</span><span class="sxs-lookup"><span data-stu-id="ab382-102">ApplyToElement operation</span></span>

<span data-ttu-id="ab382-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ab382-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ab382-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ab382-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ab382-105">配列の特定の要素に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="ab382-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElement<'T> (op : ('T => Unit), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="ab382-106">説明</span><span class="sxs-lookup"><span data-stu-id="ab382-106">Description</span></span>

<span data-ttu-id="ab382-107">指定された操作 `op` 、インデックス `index` 、およびターゲットの配列が適用され `targets` `op(targets[index])` ます。</span><span class="sxs-lookup"><span data-stu-id="ab382-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="ab382-108">入力</span><span class="sxs-lookup"><span data-stu-id="ab382-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="ab382-109">op: t => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ab382-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ab382-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="ab382-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="ab382-111">index: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ab382-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ab382-112">ターゲットの配列のインデックス。</span><span class="sxs-lookup"><span data-stu-id="ab382-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="ab382-113">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="ab382-113">targets : 'T[]</span></span>

<span data-ttu-id="ab382-114">に対して可能なターゲットの配列 `op` 。</span><span class="sxs-lookup"><span data-stu-id="ab382-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ab382-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ab382-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ab382-116">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="ab382-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ab382-117">&</span><span class="sxs-lookup"><span data-stu-id="ab382-117">'T</span></span>

<span data-ttu-id="ab382-118">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="ab382-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab382-119">参照</span><span class="sxs-lookup"><span data-stu-id="ab382-119">See Also</span></span>

- [<span data-ttu-id="ab382-120">Microsoft. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="ab382-120">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="ab382-121">Microsoft. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="ab382-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="ab382-122">Microsoft. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="ab382-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)