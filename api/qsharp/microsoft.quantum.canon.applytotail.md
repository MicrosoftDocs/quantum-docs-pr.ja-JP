---
uid: Microsoft.Quantum.Canon.ApplyToTail
title: 適用操作の適用
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTail
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 6754d41e63ea0357487fa2f62bd9209843a93347
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207974"
---
# <a name="applytotail-operation"></a><span data-ttu-id="bdbf1-102">適用操作の適用</span><span class="sxs-lookup"><span data-stu-id="bdbf1-102">ApplyToTail operation</span></span>

<span data-ttu-id="bdbf1-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bdbf1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bdbf1-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bdbf1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bdbf1-105">配列の最後の要素に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="bdbf1-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTail<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="bdbf1-106">説明</span><span class="sxs-lookup"><span data-stu-id="bdbf1-106">Description</span></span>

<span data-ttu-id="bdbf1-107">指定された操作 `op` とターゲットの配列が適用され `targets` `op(Tail(targets))` ます。</span><span class="sxs-lookup"><span data-stu-id="bdbf1-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="bdbf1-108">入力</span><span class="sxs-lookup"><span data-stu-id="bdbf1-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="bdbf1-109">op: t => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bdbf1-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="bdbf1-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="bdbf1-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="bdbf1-111">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="bdbf1-111">targets : 'T[]</span></span>

<span data-ttu-id="bdbf1-112">最後のが適用されるターゲットの配列 `op` 。</span><span class="sxs-lookup"><span data-stu-id="bdbf1-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bdbf1-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bdbf1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bdbf1-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="bdbf1-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bdbf1-115">&</span><span class="sxs-lookup"><span data-stu-id="bdbf1-115">'T</span></span>

<span data-ttu-id="bdbf1-116">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="bdbf1-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="bdbf1-117">参照</span><span class="sxs-lookup"><span data-stu-id="bdbf1-117">See Also</span></span>

- [<span data-ttu-id="bdbf1-118">Microsoft.... "</span><span class="sxs-lookup"><span data-stu-id="bdbf1-118">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="bdbf1-119">Microsoft......。</span><span class="sxs-lookup"><span data-stu-id="bdbf1-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="bdbf1-120">Microsoft... の証明機関</span><span class="sxs-lookup"><span data-stu-id="bdbf1-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)