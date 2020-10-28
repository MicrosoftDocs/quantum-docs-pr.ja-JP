---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: Applytoall Ca 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 797cbd835446f31b2df60dbb184f888e6d0356aa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717166"
---
# <a name="applytomostca-operation"></a><span data-ttu-id="ea21e-102">Applytoall Ca 操作</span><span class="sxs-lookup"><span data-stu-id="ea21e-102">ApplyToMostCA operation</span></span>

<span data-ttu-id="ea21e-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ea21e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ea21e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ea21e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ea21e-105">配列の最後の要素以外のすべてに操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="ea21e-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="ea21e-106">説明</span><span class="sxs-lookup"><span data-stu-id="ea21e-106">Description</span></span>

<span data-ttu-id="ea21e-107">指定された操作 `op` とターゲットの配列が適用され `targets` `op(Most(targets))` ます。</span><span class="sxs-lookup"><span data-stu-id="ea21e-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="ea21e-108">入力</span><span class="sxs-lookup"><span data-stu-id="ea21e-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="ea21e-109">op: ' t [] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="ea21e-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="ea21e-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="ea21e-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="ea21e-111">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="ea21e-111">targets : 'T[]</span></span>

<span data-ttu-id="ea21e-112">ターゲットの配列。最後のすべてのが適用され `op` ます。</span><span class="sxs-lookup"><span data-stu-id="ea21e-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ea21e-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ea21e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ea21e-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea21e-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ea21e-115">&</span><span class="sxs-lookup"><span data-stu-id="ea21e-115">'T</span></span>

<span data-ttu-id="ea21e-116">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="ea21e-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea21e-117">参照</span><span class="sxs-lookup"><span data-stu-id="ea21e-117">See Also</span></span>

- [<span data-ttu-id="ea21e-118">Microsoft...。</span><span class="sxs-lookup"><span data-stu-id="ea21e-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="ea21e-119">Microsoft. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="ea21e-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="ea21e-120">Microsoft....。</span><span class="sxs-lookup"><span data-stu-id="ea21e-120">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)