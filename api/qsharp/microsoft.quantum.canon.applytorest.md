---
uid: Microsoft.Quantum.Canon.ApplyToRest
title: ApplyToRest 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRest
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: fe49361f3c2259960eaa58d47df9b69b30b572a8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208269"
---
# <a name="applytorest-operation"></a><span data-ttu-id="9d2f7-102">ApplyToRest 操作</span><span class="sxs-lookup"><span data-stu-id="9d2f7-102">ApplyToRest operation</span></span>

<span data-ttu-id="9d2f7-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9d2f7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9d2f7-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9d2f7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9d2f7-105">配列の最初の要素以外のすべてに操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="9d2f7-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRest<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="9d2f7-106">説明</span><span class="sxs-lookup"><span data-stu-id="9d2f7-106">Description</span></span>

<span data-ttu-id="9d2f7-107">指定された操作 `op` とターゲットの配列が適用され `targets` `op(Rest(targets))` ます。</span><span class="sxs-lookup"><span data-stu-id="9d2f7-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="9d2f7-108">入力</span><span class="sxs-lookup"><span data-stu-id="9d2f7-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="9d2f7-109">op: ' t [] => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9d2f7-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9d2f7-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="9d2f7-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="9d2f7-111">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="9d2f7-111">targets : 'T[]</span></span>

<span data-ttu-id="9d2f7-112">ターゲットの配列。すべてのものが最初に適用され `op` ます。</span><span class="sxs-lookup"><span data-stu-id="9d2f7-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9d2f7-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9d2f7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9d2f7-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="9d2f7-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9d2f7-115">&</span><span class="sxs-lookup"><span data-stu-id="9d2f7-115">'T</span></span>

<span data-ttu-id="9d2f7-116">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="9d2f7-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d2f7-117">参照</span><span class="sxs-lookup"><span data-stu-id="9d2f7-117">See Also</span></span>

- [<span data-ttu-id="9d2f7-118">Microsoft. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="9d2f7-118">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="9d2f7-119">Microsoft....。</span><span class="sxs-lookup"><span data-stu-id="9d2f7-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="9d2f7-120">Microsoft. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="9d2f7-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)