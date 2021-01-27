---
uid: Microsoft.Quantum.Canon.ApplyToRestCA
title: ApplyToRestCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestCA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: e64eeaae2151a28c289e3e71e47f897d6c378b36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841241"
---
# <a name="applytorestca-operation"></a><span data-ttu-id="9f431-102">ApplyToRestCA 操作</span><span class="sxs-lookup"><span data-stu-id="9f431-102">ApplyToRestCA operation</span></span>

<span data-ttu-id="9f431-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9f431-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9f431-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9f431-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9f431-105">配列の最初の要素以外のすべてに操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="9f431-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="9f431-106">説明</span><span class="sxs-lookup"><span data-stu-id="9f431-106">Description</span></span>

<span data-ttu-id="9f431-107">指定された操作 `op` とターゲットの配列が適用され `targets` `op(Rest(targets))` ます。</span><span class="sxs-lookup"><span data-stu-id="9f431-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="9f431-108">入力</span><span class="sxs-lookup"><span data-stu-id="9f431-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="9f431-109">op: ' t [] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="9f431-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="9f431-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="9f431-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="9f431-111">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="9f431-111">targets : 'T[]</span></span>

<span data-ttu-id="9f431-112">ターゲットの配列。すべてのものが最初に適用され `op` ます。</span><span class="sxs-lookup"><span data-stu-id="9f431-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9f431-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9f431-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9f431-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="9f431-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9f431-115">&</span><span class="sxs-lookup"><span data-stu-id="9f431-115">'T</span></span>

<span data-ttu-id="9f431-116">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="9f431-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="9f431-117">参照</span><span class="sxs-lookup"><span data-stu-id="9f431-117">See Also</span></span>

- [<span data-ttu-id="9f431-118">Microsoft. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="9f431-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="9f431-119">Microsoft. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="9f431-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="9f431-120">Microsoft....。</span><span class="sxs-lookup"><span data-stu-id="9f431-120">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)