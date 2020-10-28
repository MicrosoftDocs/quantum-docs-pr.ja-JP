---
uid: Microsoft.Quantum.Canon.ApplyToHeadC
title: ApplyToHeadC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadC
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3ff6c25837f1219dd456bf1739a2953ff72e2df9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717250"
---
# <a name="applytoheadc-operation"></a><span data-ttu-id="bd837-102">ApplyToHeadC 操作</span><span class="sxs-lookup"><span data-stu-id="bd837-102">ApplyToHeadC operation</span></span>

<span data-ttu-id="bd837-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bd837-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bd837-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bd837-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bd837-105">配列の最初の要素に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="bd837-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="bd837-106">説明</span><span class="sxs-lookup"><span data-stu-id="bd837-106">Description</span></span>

<span data-ttu-id="bd837-107">指定された操作 `op` とターゲットの配列が適用され `targets` `op(Head(targets))` ます。</span><span class="sxs-lookup"><span data-stu-id="bd837-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="bd837-108">入力</span><span class="sxs-lookup"><span data-stu-id="bd837-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="bd837-109">op: ' t => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="bd837-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="bd837-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="bd837-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="bd837-111">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="bd837-111">targets : 'T[]</span></span>

<span data-ttu-id="bd837-112">最初のが適用されるターゲットの配列 `op` 。</span><span class="sxs-lookup"><span data-stu-id="bd837-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bd837-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bd837-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bd837-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="bd837-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bd837-115">&</span><span class="sxs-lookup"><span data-stu-id="bd837-115">'T</span></span>

<span data-ttu-id="bd837-116">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="bd837-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd837-117">参照</span><span class="sxs-lookup"><span data-stu-id="bd837-117">See Also</span></span>

- [<span data-ttu-id="bd837-118">Microsoft. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="bd837-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="bd837-119">Microsoft. Canon. Applytoヘッド a</span><span class="sxs-lookup"><span data-stu-id="bd837-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="bd837-120">Microsoft. Canon. Applytoヘッド Ca</span><span class="sxs-lookup"><span data-stu-id="bd837-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)