---
uid: Microsoft.Quantum.Canon.ApplyToRestCA
title: ApplyToRestCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestCA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: d2dc10803044980d53f80f0577d16cb14a2eb301
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717068"
---
# <a name="applytorestca-operation"></a><span data-ttu-id="17342-102">ApplyToRestCA 操作</span><span class="sxs-lookup"><span data-stu-id="17342-102">ApplyToRestCA operation</span></span>

<span data-ttu-id="17342-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="17342-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="17342-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="17342-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="17342-105">配列の最初の要素以外のすべてに操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="17342-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="17342-106">説明</span><span class="sxs-lookup"><span data-stu-id="17342-106">Description</span></span>

<span data-ttu-id="17342-107">指定された操作 `op` とターゲットの配列が適用され `targets` `op(Rest(targets))` ます。</span><span class="sxs-lookup"><span data-stu-id="17342-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="17342-108">入力</span><span class="sxs-lookup"><span data-stu-id="17342-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="17342-109">op: ' t [] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="17342-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="17342-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="17342-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="17342-111">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="17342-111">targets : 'T[]</span></span>

<span data-ttu-id="17342-112">ターゲットの配列。すべてのものが最初に適用され `op` ます。</span><span class="sxs-lookup"><span data-stu-id="17342-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="17342-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="17342-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="17342-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="17342-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="17342-115">&</span><span class="sxs-lookup"><span data-stu-id="17342-115">'T</span></span>

<span data-ttu-id="17342-116">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="17342-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="17342-117">参照</span><span class="sxs-lookup"><span data-stu-id="17342-117">See Also</span></span>

- [<span data-ttu-id="17342-118">Microsoft. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="17342-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="17342-119">Microsoft. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="17342-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="17342-120">Microsoft....。</span><span class="sxs-lookup"><span data-stu-id="17342-120">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)