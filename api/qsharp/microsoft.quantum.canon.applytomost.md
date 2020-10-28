---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: ApplyToMost の操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 2c6c8873859439e71436f6beb0de40dfd1e21f43
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717227"
---
# <a name="applytomost-operation"></a><span data-ttu-id="46acb-102">ApplyToMost の操作</span><span class="sxs-lookup"><span data-stu-id="46acb-102">ApplyToMost operation</span></span>

<span data-ttu-id="46acb-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="46acb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="46acb-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="46acb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="46acb-105">配列の最後の要素以外のすべてに操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="46acb-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="46acb-106">説明</span><span class="sxs-lookup"><span data-stu-id="46acb-106">Description</span></span>

<span data-ttu-id="46acb-107">指定された操作 `op` とターゲットの配列が適用され `targets` `op(Most(targets))` ます。</span><span class="sxs-lookup"><span data-stu-id="46acb-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="46acb-108">入力</span><span class="sxs-lookup"><span data-stu-id="46acb-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="46acb-109">op: ' t [] => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="46acb-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="46acb-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="46acb-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="46acb-111">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="46acb-111">targets : 'T[]</span></span>

<span data-ttu-id="46acb-112">ターゲットの配列。最後のすべてのが適用され `op` ます。</span><span class="sxs-lookup"><span data-stu-id="46acb-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="46acb-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="46acb-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="46acb-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="46acb-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="46acb-115">&</span><span class="sxs-lookup"><span data-stu-id="46acb-115">'T</span></span>

<span data-ttu-id="46acb-116">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="46acb-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="46acb-117">参照</span><span class="sxs-lookup"><span data-stu-id="46acb-117">See Also</span></span>

- [<span data-ttu-id="46acb-118">Microsoft. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="46acb-118">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="46acb-119">Microsoft....。</span><span class="sxs-lookup"><span data-stu-id="46acb-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="46acb-120">Microsoft. Canon. Applytoほとんどの Ca</span><span class="sxs-lookup"><span data-stu-id="46acb-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)