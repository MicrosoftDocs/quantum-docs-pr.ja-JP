---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: ApplyToElementA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 57d870c7fbd099212b13f75bd85e57c046280d73
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850764"
---
# <a name="applytoelementa-operation"></a><span data-ttu-id="0862b-102">ApplyToElementA 操作</span><span class="sxs-lookup"><span data-stu-id="0862b-102">ApplyToElementA operation</span></span>

<span data-ttu-id="0862b-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0862b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0862b-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0862b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0862b-105">配列の特定の要素に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="0862b-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="0862b-106">説明</span><span class="sxs-lookup"><span data-stu-id="0862b-106">Description</span></span>

<span data-ttu-id="0862b-107">指定された操作 `op` 、インデックス `index` 、およびターゲットの配列が適用され `targets` `op(targets[index])` ます。</span><span class="sxs-lookup"><span data-stu-id="0862b-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="0862b-108">入力</span><span class="sxs-lookup"><span data-stu-id="0862b-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="0862b-109">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="0862b-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="0862b-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="0862b-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="0862b-111">index: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0862b-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0862b-112">ターゲットの配列のインデックス。</span><span class="sxs-lookup"><span data-stu-id="0862b-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="0862b-113">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="0862b-113">targets : 'T[]</span></span>

<span data-ttu-id="0862b-114">に対して可能なターゲットの配列 `op` 。</span><span class="sxs-lookup"><span data-stu-id="0862b-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0862b-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0862b-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0862b-116">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="0862b-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0862b-117">&</span><span class="sxs-lookup"><span data-stu-id="0862b-117">'T</span></span>

<span data-ttu-id="0862b-118">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="0862b-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="0862b-119">参照</span><span class="sxs-lookup"><span data-stu-id="0862b-119">See Also</span></span>

- [<span data-ttu-id="0862b-120">"Microsoft....."</span><span class="sxs-lookup"><span data-stu-id="0862b-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="0862b-121">Microsoft. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="0862b-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="0862b-122">Microsoft. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="0862b-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)