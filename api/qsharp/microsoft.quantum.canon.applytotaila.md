---
uid: Microsoft.Quantum.Canon.ApplyToTailA
title: 操作の適用
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: a84fa6c53f3e11bef82b8b83fffa1451a8299511
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716975"
---
# <a name="applytotaila-operation"></a><span data-ttu-id="fac29-102">操作の適用</span><span class="sxs-lookup"><span data-stu-id="fac29-102">ApplyToTailA operation</span></span>

<span data-ttu-id="fac29-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fac29-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fac29-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fac29-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fac29-105">配列の最後の要素に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="fac29-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="fac29-106">説明</span><span class="sxs-lookup"><span data-stu-id="fac29-106">Description</span></span>

<span data-ttu-id="fac29-107">指定された操作 `op` とターゲットの配列が適用され `targets` `op(Tail(targets))` ます。</span><span class="sxs-lookup"><span data-stu-id="fac29-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="fac29-108">入力</span><span class="sxs-lookup"><span data-stu-id="fac29-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="fac29-109">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="fac29-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="fac29-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="fac29-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="fac29-111">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="fac29-111">targets : 'T[]</span></span>

<span data-ttu-id="fac29-112">最後のが適用されるターゲットの配列 `op` 。</span><span class="sxs-lookup"><span data-stu-id="fac29-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fac29-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fac29-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fac29-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="fac29-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fac29-115">&</span><span class="sxs-lookup"><span data-stu-id="fac29-115">'T</span></span>

<span data-ttu-id="fac29-116">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="fac29-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="fac29-117">参照</span><span class="sxs-lookup"><span data-stu-id="fac29-117">See Also</span></span>

- [<span data-ttu-id="fac29-118">Microsoft. Canon. 適用</span><span class="sxs-lookup"><span data-stu-id="fac29-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="fac29-119">Microsoft......。</span><span class="sxs-lookup"><span data-stu-id="fac29-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="fac29-120">Microsoft... の証明機関</span><span class="sxs-lookup"><span data-stu-id="fac29-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)