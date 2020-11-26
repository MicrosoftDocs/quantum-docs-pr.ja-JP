---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: ApplyToHead 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 35f19cbb1090e974e18f338239764c9c8b854116
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217341"
---
# <a name="applytohead-operation"></a><span data-ttu-id="5e07a-102">ApplyToHead 操作</span><span class="sxs-lookup"><span data-stu-id="5e07a-102">ApplyToHead operation</span></span>

<span data-ttu-id="5e07a-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5e07a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5e07a-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5e07a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5e07a-105">配列の最初の要素に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="5e07a-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="5e07a-106">説明</span><span class="sxs-lookup"><span data-stu-id="5e07a-106">Description</span></span>

<span data-ttu-id="5e07a-107">指定された操作 `op` とターゲットの配列が適用され `targets` `op(Head(targets))` ます。</span><span class="sxs-lookup"><span data-stu-id="5e07a-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="5e07a-108">入力</span><span class="sxs-lookup"><span data-stu-id="5e07a-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="5e07a-109">op: t => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5e07a-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="5e07a-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="5e07a-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="5e07a-111">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="5e07a-111">targets : 'T[]</span></span>

<span data-ttu-id="5e07a-112">最初のが適用されるターゲットの配列 `op` 。</span><span class="sxs-lookup"><span data-stu-id="5e07a-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5e07a-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5e07a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5e07a-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="5e07a-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5e07a-115">&</span><span class="sxs-lookup"><span data-stu-id="5e07a-115">'T</span></span>

<span data-ttu-id="5e07a-116">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="5e07a-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e07a-117">参照</span><span class="sxs-lookup"><span data-stu-id="5e07a-117">See Also</span></span>

- [<span data-ttu-id="5e07a-118">Microsoft. Canon. Applytoヘッド a</span><span class="sxs-lookup"><span data-stu-id="5e07a-118">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="5e07a-119">Microsoft. Canon. Applytoヘッド c</span><span class="sxs-lookup"><span data-stu-id="5e07a-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="5e07a-120">Microsoft. Canon. Applytoヘッド Ca</span><span class="sxs-lookup"><span data-stu-id="5e07a-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)