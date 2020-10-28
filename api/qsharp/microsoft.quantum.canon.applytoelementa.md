---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: ApplyToElementA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: f34089c2a45de281507cb79bde8a8cb9d2fefe47
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717488"
---
# <a name="applytoelementa-operation"></a><span data-ttu-id="57d96-102">ApplyToElementA 操作</span><span class="sxs-lookup"><span data-stu-id="57d96-102">ApplyToElementA operation</span></span>

<span data-ttu-id="57d96-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="57d96-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="57d96-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="57d96-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="57d96-105">配列の特定の要素に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="57d96-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="57d96-106">説明</span><span class="sxs-lookup"><span data-stu-id="57d96-106">Description</span></span>

<span data-ttu-id="57d96-107">指定された操作 `op` 、インデックス `index` 、およびターゲットの配列が適用され `targets` `op(targets[index])` ます。</span><span class="sxs-lookup"><span data-stu-id="57d96-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="57d96-108">入力</span><span class="sxs-lookup"><span data-stu-id="57d96-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="57d96-109">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="57d96-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="57d96-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="57d96-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="57d96-111">index: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="57d96-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="57d96-112">ターゲットの配列のインデックス。</span><span class="sxs-lookup"><span data-stu-id="57d96-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="57d96-113">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="57d96-113">targets : 'T[]</span></span>

<span data-ttu-id="57d96-114">に対して可能なターゲットの配列 `op` 。</span><span class="sxs-lookup"><span data-stu-id="57d96-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="57d96-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="57d96-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="57d96-116">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="57d96-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="57d96-117">&</span><span class="sxs-lookup"><span data-stu-id="57d96-117">'T</span></span>

<span data-ttu-id="57d96-118">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="57d96-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="57d96-119">参照</span><span class="sxs-lookup"><span data-stu-id="57d96-119">See Also</span></span>

- [<span data-ttu-id="57d96-120">"Microsoft....."</span><span class="sxs-lookup"><span data-stu-id="57d96-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="57d96-121">Microsoft. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="57d96-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="57d96-122">Microsoft. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="57d96-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)