---
uid: Microsoft.Quantum.Canon.ApplyToTail
title: 適用操作の適用
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTail
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 72b55ec7161d5f6af5e4cb512c648078516c3b4e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716984"
---
# <a name="applytotail-operation"></a><span data-ttu-id="37cc3-102">適用操作の適用</span><span class="sxs-lookup"><span data-stu-id="37cc3-102">ApplyToTail operation</span></span>

<span data-ttu-id="37cc3-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="37cc3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="37cc3-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="37cc3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="37cc3-105">配列の最後の要素に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="37cc3-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTail<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="37cc3-106">説明</span><span class="sxs-lookup"><span data-stu-id="37cc3-106">Description</span></span>

<span data-ttu-id="37cc3-107">指定された操作 `op` とターゲットの配列が適用され `targets` `op(Tail(targets))` ます。</span><span class="sxs-lookup"><span data-stu-id="37cc3-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="37cc3-108">入力</span><span class="sxs-lookup"><span data-stu-id="37cc3-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="37cc3-109">op: t => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="37cc3-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="37cc3-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="37cc3-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="37cc3-111">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="37cc3-111">targets : 'T[]</span></span>

<span data-ttu-id="37cc3-112">最後のが適用されるターゲットの配列 `op` 。</span><span class="sxs-lookup"><span data-stu-id="37cc3-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="37cc3-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="37cc3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="37cc3-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="37cc3-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="37cc3-115">&</span><span class="sxs-lookup"><span data-stu-id="37cc3-115">'T</span></span>

<span data-ttu-id="37cc3-116">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="37cc3-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="37cc3-117">参照</span><span class="sxs-lookup"><span data-stu-id="37cc3-117">See Also</span></span>

- [<span data-ttu-id="37cc3-118">Microsoft.... "</span><span class="sxs-lookup"><span data-stu-id="37cc3-118">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="37cc3-119">Microsoft......。</span><span class="sxs-lookup"><span data-stu-id="37cc3-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="37cc3-120">Microsoft... の証明機関</span><span class="sxs-lookup"><span data-stu-id="37cc3-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)