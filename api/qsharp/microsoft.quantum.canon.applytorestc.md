---
uid: Microsoft.Quantum.Canon.ApplyToRestC
title: ApplyToRestC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestC
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 1e533a9f0994b70054aeca2f9ddd97f4e200b03f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850491"
---
# <a name="applytorestc-operation"></a><span data-ttu-id="d4fbe-102">ApplyToRestC 操作</span><span class="sxs-lookup"><span data-stu-id="d4fbe-102">ApplyToRestC operation</span></span>

<span data-ttu-id="d4fbe-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d4fbe-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d4fbe-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d4fbe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d4fbe-105">配列の最初の要素以外のすべてに操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="d4fbe-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="d4fbe-106">説明</span><span class="sxs-lookup"><span data-stu-id="d4fbe-106">Description</span></span>

<span data-ttu-id="d4fbe-107">指定された操作 `op` とターゲットの配列が適用され `targets` `op(Rest(targets))` ます。</span><span class="sxs-lookup"><span data-stu-id="d4fbe-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="d4fbe-108">入力</span><span class="sxs-lookup"><span data-stu-id="d4fbe-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="d4fbe-109">op: ' t [] => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="d4fbe-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="d4fbe-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="d4fbe-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="d4fbe-111">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="d4fbe-111">targets : 'T[]</span></span>

<span data-ttu-id="d4fbe-112">ターゲットの配列。すべてのものが最初に適用され `op` ます。</span><span class="sxs-lookup"><span data-stu-id="d4fbe-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d4fbe-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d4fbe-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d4fbe-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="d4fbe-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d4fbe-115">&</span><span class="sxs-lookup"><span data-stu-id="d4fbe-115">'T</span></span>

<span data-ttu-id="d4fbe-116">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="d4fbe-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4fbe-117">参照</span><span class="sxs-lookup"><span data-stu-id="d4fbe-117">See Also</span></span>

- [<span data-ttu-id="d4fbe-118">Microsoft. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="d4fbe-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="d4fbe-119">Microsoft. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="d4fbe-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="d4fbe-120">Microsoft. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="d4fbe-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)