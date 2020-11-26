---
uid: Microsoft.Quantum.Canon.ApplyToMostA
title: ApplyToMostA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 7c226de9b2c99d124c467175dfe65a60a89d4332
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208501"
---
# <a name="applytomosta-operation"></a><span data-ttu-id="437dc-102">ApplyToMostA 操作</span><span class="sxs-lookup"><span data-stu-id="437dc-102">ApplyToMostA operation</span></span>

<span data-ttu-id="437dc-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="437dc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="437dc-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="437dc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="437dc-105">配列の最後の要素以外のすべてに操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="437dc-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="437dc-106">説明</span><span class="sxs-lookup"><span data-stu-id="437dc-106">Description</span></span>

<span data-ttu-id="437dc-107">指定された操作 `op` とターゲットの配列が適用され `targets` `op(Most(targets))` ます。</span><span class="sxs-lookup"><span data-stu-id="437dc-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="437dc-108">入力</span><span class="sxs-lookup"><span data-stu-id="437dc-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="437dc-109">op: ' t [] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="437dc-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="437dc-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="437dc-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="437dc-111">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="437dc-111">targets : 'T[]</span></span>

<span data-ttu-id="437dc-112">ターゲットの配列。最後のすべてのが適用され `op` ます。</span><span class="sxs-lookup"><span data-stu-id="437dc-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="437dc-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="437dc-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="437dc-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="437dc-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="437dc-115">&</span><span class="sxs-lookup"><span data-stu-id="437dc-115">'T</span></span>

<span data-ttu-id="437dc-116">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="437dc-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="437dc-117">参照</span><span class="sxs-lookup"><span data-stu-id="437dc-117">See Also</span></span>

- [<span data-ttu-id="437dc-118">Microsoft...。</span><span class="sxs-lookup"><span data-stu-id="437dc-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="437dc-119">Microsoft....。</span><span class="sxs-lookup"><span data-stu-id="437dc-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="437dc-120">Microsoft. Canon. Applytoほとんどの Ca</span><span class="sxs-lookup"><span data-stu-id="437dc-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)