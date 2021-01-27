---
uid: Microsoft.Quantum.Canon.ApplyToMostC
title: Applyto最も c 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostC
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 14de9f367aa7d19f64f13186d402239ae1fef3c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850555"
---
# <a name="applytomostc-operation"></a><span data-ttu-id="50cc0-102">Applyto最も c 操作</span><span class="sxs-lookup"><span data-stu-id="50cc0-102">ApplyToMostC operation</span></span>

<span data-ttu-id="50cc0-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="50cc0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="50cc0-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="50cc0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="50cc0-105">配列の最後の要素以外のすべてに操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="50cc0-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="50cc0-106">説明</span><span class="sxs-lookup"><span data-stu-id="50cc0-106">Description</span></span>

<span data-ttu-id="50cc0-107">指定された操作 `op` とターゲットの配列が適用され `targets` `op(Most(targets))` ます。</span><span class="sxs-lookup"><span data-stu-id="50cc0-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="50cc0-108">入力</span><span class="sxs-lookup"><span data-stu-id="50cc0-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="50cc0-109">op: ' t [] => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="50cc0-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="50cc0-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="50cc0-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="50cc0-111">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="50cc0-111">targets : 'T[]</span></span>

<span data-ttu-id="50cc0-112">ターゲットの配列。最後のすべてのが適用され `op` ます。</span><span class="sxs-lookup"><span data-stu-id="50cc0-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="50cc0-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="50cc0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="50cc0-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="50cc0-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="50cc0-115">&</span><span class="sxs-lookup"><span data-stu-id="50cc0-115">'T</span></span>

<span data-ttu-id="50cc0-116">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="50cc0-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="50cc0-117">参照</span><span class="sxs-lookup"><span data-stu-id="50cc0-117">See Also</span></span>

- [<span data-ttu-id="50cc0-118">Microsoft...。</span><span class="sxs-lookup"><span data-stu-id="50cc0-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="50cc0-119">Microsoft. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="50cc0-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="50cc0-120">Microsoft. Canon. Applytoほとんどの Ca</span><span class="sxs-lookup"><span data-stu-id="50cc0-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)