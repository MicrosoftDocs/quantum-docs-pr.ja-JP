---
uid: Microsoft.Quantum.Canon.ApplyToHeadCA
title: ApplyToHeadCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadCA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 5bb016373040b1b66984405ea2bda0b8cb0c5102
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717236"
---
# <a name="applytoheadca-operation"></a><span data-ttu-id="c3d96-102">ApplyToHeadCA 操作</span><span class="sxs-lookup"><span data-stu-id="c3d96-102">ApplyToHeadCA operation</span></span>

<span data-ttu-id="c3d96-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c3d96-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c3d96-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c3d96-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c3d96-105">配列の最初の要素に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="c3d96-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="c3d96-106">説明</span><span class="sxs-lookup"><span data-stu-id="c3d96-106">Description</span></span>

<span data-ttu-id="c3d96-107">指定された操作 `op` とターゲットの配列が適用され `targets` `op(Head(targets))` ます。</span><span class="sxs-lookup"><span data-stu-id="c3d96-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="c3d96-108">入力</span><span class="sxs-lookup"><span data-stu-id="c3d96-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="c3d96-109">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="c3d96-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="c3d96-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="c3d96-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="c3d96-111">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="c3d96-111">targets : 'T[]</span></span>

<span data-ttu-id="c3d96-112">最初のが適用されるターゲットの配列 `op` 。</span><span class="sxs-lookup"><span data-stu-id="c3d96-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c3d96-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c3d96-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c3d96-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="c3d96-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c3d96-115">&</span><span class="sxs-lookup"><span data-stu-id="c3d96-115">'T</span></span>

<span data-ttu-id="c3d96-116">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="c3d96-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3d96-117">参照</span><span class="sxs-lookup"><span data-stu-id="c3d96-117">See Also</span></span>

- [<span data-ttu-id="c3d96-118">Microsoft. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="c3d96-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="c3d96-119">Microsoft. Canon. Applytoヘッド a</span><span class="sxs-lookup"><span data-stu-id="c3d96-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="c3d96-120">Microsoft. Canon. Applytoヘッド c</span><span class="sxs-lookup"><span data-stu-id="c3d96-120">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)