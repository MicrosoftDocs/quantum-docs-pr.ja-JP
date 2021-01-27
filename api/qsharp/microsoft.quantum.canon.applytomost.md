---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: ApplyToMost の操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: a3918233e101f3d8956601dcc7d85edcf6196ac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850589"
---
# <a name="applytomost-operation"></a><span data-ttu-id="f3713-102">ApplyToMost の操作</span><span class="sxs-lookup"><span data-stu-id="f3713-102">ApplyToMost operation</span></span>

<span data-ttu-id="f3713-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f3713-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f3713-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f3713-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f3713-105">配列の最後の要素以外のすべてに操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="f3713-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="f3713-106">説明</span><span class="sxs-lookup"><span data-stu-id="f3713-106">Description</span></span>

<span data-ttu-id="f3713-107">指定された操作 `op` とターゲットの配列が適用され `targets` `op(Most(targets))` ます。</span><span class="sxs-lookup"><span data-stu-id="f3713-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="f3713-108">入力</span><span class="sxs-lookup"><span data-stu-id="f3713-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="f3713-109">op: ' t [] => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f3713-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f3713-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="f3713-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="f3713-111">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="f3713-111">targets : 'T[]</span></span>

<span data-ttu-id="f3713-112">ターゲットの配列。最後のすべてのが適用され `op` ます。</span><span class="sxs-lookup"><span data-stu-id="f3713-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f3713-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f3713-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f3713-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="f3713-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f3713-115">&</span><span class="sxs-lookup"><span data-stu-id="f3713-115">'T</span></span>

<span data-ttu-id="f3713-116">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="f3713-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="f3713-117">例</span><span class="sxs-lookup"><span data-stu-id="f3713-117">Example</span></span>

<span data-ttu-id="f3713-118">次の Q # スニペットは同等です。</span><span class="sxs-lookup"><span data-stu-id="f3713-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToMost(ApplyCNOTChain, register);
ApplyCNOTChain(Most(register));
```

## <a name="see-also"></a><span data-ttu-id="f3713-119">参照</span><span class="sxs-lookup"><span data-stu-id="f3713-119">See Also</span></span>

- [<span data-ttu-id="f3713-120">Microsoft. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="f3713-120">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="f3713-121">Microsoft....。</span><span class="sxs-lookup"><span data-stu-id="f3713-121">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="f3713-122">Microsoft. Canon. Applytoほとんどの Ca</span><span class="sxs-lookup"><span data-stu-id="f3713-122">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)