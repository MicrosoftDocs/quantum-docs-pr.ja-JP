---
uid: Microsoft.Quantum.Canon.ApplyToMostC
title: Applyto最も c 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostC
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: a5927f6b296dd50afec8979c8e8ac22979b8a082
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717171"
---
# <a name="applytomostc-operation"></a><span data-ttu-id="8c8c5-102">Applyto最も c 操作</span><span class="sxs-lookup"><span data-stu-id="8c8c5-102">ApplyToMostC operation</span></span>

<span data-ttu-id="8c8c5-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8c8c5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8c8c5-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8c8c5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8c8c5-105">配列の最後の要素以外のすべてに操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="8c8c5-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="8c8c5-106">説明</span><span class="sxs-lookup"><span data-stu-id="8c8c5-106">Description</span></span>

<span data-ttu-id="8c8c5-107">指定された操作 `op` とターゲットの配列が適用され `targets` `op(Most(targets))` ます。</span><span class="sxs-lookup"><span data-stu-id="8c8c5-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="8c8c5-108">入力</span><span class="sxs-lookup"><span data-stu-id="8c8c5-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="8c8c5-109">op: ' t [] => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="8c8c5-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="8c8c5-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="8c8c5-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="8c8c5-111">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="8c8c5-111">targets : 'T[]</span></span>

<span data-ttu-id="8c8c5-112">ターゲットの配列。最後のすべてのが適用され `op` ます。</span><span class="sxs-lookup"><span data-stu-id="8c8c5-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8c8c5-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8c8c5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8c8c5-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="8c8c5-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8c8c5-115">&</span><span class="sxs-lookup"><span data-stu-id="8c8c5-115">'T</span></span>

<span data-ttu-id="8c8c5-116">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="8c8c5-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c8c5-117">参照</span><span class="sxs-lookup"><span data-stu-id="8c8c5-117">See Also</span></span>

- [<span data-ttu-id="8c8c5-118">Microsoft...。</span><span class="sxs-lookup"><span data-stu-id="8c8c5-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="8c8c5-119">Microsoft. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="8c8c5-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="8c8c5-120">Microsoft. Canon. Applytoほとんどの Ca</span><span class="sxs-lookup"><span data-stu-id="8c8c5-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)