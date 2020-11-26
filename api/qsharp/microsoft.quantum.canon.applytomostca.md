---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: Applytoall Ca 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 2ce76d2a86665fbfa5f5d91df23220c7c80981e3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208416"
---
# <a name="applytomostca-operation"></a><span data-ttu-id="63a44-102">Applytoall Ca 操作</span><span class="sxs-lookup"><span data-stu-id="63a44-102">ApplyToMostCA operation</span></span>

<span data-ttu-id="63a44-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="63a44-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="63a44-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="63a44-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="63a44-105">配列の最後の要素以外のすべてに操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="63a44-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="63a44-106">説明</span><span class="sxs-lookup"><span data-stu-id="63a44-106">Description</span></span>

<span data-ttu-id="63a44-107">指定された操作 `op` とターゲットの配列が適用され `targets` `op(Most(targets))` ます。</span><span class="sxs-lookup"><span data-stu-id="63a44-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="63a44-108">入力</span><span class="sxs-lookup"><span data-stu-id="63a44-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="63a44-109">op: ' t [] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="63a44-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="63a44-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="63a44-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="63a44-111">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="63a44-111">targets : 'T[]</span></span>

<span data-ttu-id="63a44-112">ターゲットの配列。最後のすべてのが適用され `op` ます。</span><span class="sxs-lookup"><span data-stu-id="63a44-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="63a44-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="63a44-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="63a44-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="63a44-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="63a44-115">&</span><span class="sxs-lookup"><span data-stu-id="63a44-115">'T</span></span>

<span data-ttu-id="63a44-116">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="63a44-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="63a44-117">参照</span><span class="sxs-lookup"><span data-stu-id="63a44-117">See Also</span></span>

- [<span data-ttu-id="63a44-118">Microsoft...。</span><span class="sxs-lookup"><span data-stu-id="63a44-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="63a44-119">Microsoft. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="63a44-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="63a44-120">Microsoft....。</span><span class="sxs-lookup"><span data-stu-id="63a44-120">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)