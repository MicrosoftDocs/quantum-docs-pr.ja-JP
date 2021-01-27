---
uid: Microsoft.Quantum.Canon.ApplyToHeadC
title: ApplyToHeadC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadC
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3a65ad52e0b2f8b3a921fc549c35311f24d0e189
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850621"
---
# <a name="applytoheadc-operation"></a><span data-ttu-id="d3a7e-102">ApplyToHeadC 操作</span><span class="sxs-lookup"><span data-stu-id="d3a7e-102">ApplyToHeadC operation</span></span>

<span data-ttu-id="d3a7e-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d3a7e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d3a7e-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d3a7e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d3a7e-105">配列の最初の要素に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="d3a7e-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="d3a7e-106">説明</span><span class="sxs-lookup"><span data-stu-id="d3a7e-106">Description</span></span>

<span data-ttu-id="d3a7e-107">指定された操作 `op` とターゲットの配列が適用され `targets` `op(Head(targets))` ます。</span><span class="sxs-lookup"><span data-stu-id="d3a7e-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="d3a7e-108">入力</span><span class="sxs-lookup"><span data-stu-id="d3a7e-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="d3a7e-109">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="d3a7e-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="d3a7e-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="d3a7e-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="d3a7e-111">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="d3a7e-111">targets : 'T[]</span></span>

<span data-ttu-id="d3a7e-112">最初のが適用されるターゲットの配列 `op` 。</span><span class="sxs-lookup"><span data-stu-id="d3a7e-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d3a7e-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d3a7e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d3a7e-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="d3a7e-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d3a7e-115">&</span><span class="sxs-lookup"><span data-stu-id="d3a7e-115">'T</span></span>

<span data-ttu-id="d3a7e-116">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="d3a7e-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3a7e-117">参照</span><span class="sxs-lookup"><span data-stu-id="d3a7e-117">See Also</span></span>

- [<span data-ttu-id="d3a7e-118">Microsoft. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="d3a7e-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="d3a7e-119">Microsoft. Canon. Applytoヘッド a</span><span class="sxs-lookup"><span data-stu-id="d3a7e-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="d3a7e-120">Microsoft. Canon. Applytoヘッド Ca</span><span class="sxs-lookup"><span data-stu-id="d3a7e-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)