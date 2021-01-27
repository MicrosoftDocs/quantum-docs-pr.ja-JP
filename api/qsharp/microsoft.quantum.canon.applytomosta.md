---
uid: Microsoft.Quantum.Canon.ApplyToMostA
title: ApplyToMostA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: eb793b3d6bc1f75a14e97420d36d0aea3038e0f5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850585"
---
# <a name="applytomosta-operation"></a><span data-ttu-id="01a85-102">ApplyToMostA 操作</span><span class="sxs-lookup"><span data-stu-id="01a85-102">ApplyToMostA operation</span></span>

<span data-ttu-id="01a85-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="01a85-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="01a85-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="01a85-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="01a85-105">配列の最後の要素以外のすべてに操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="01a85-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="01a85-106">説明</span><span class="sxs-lookup"><span data-stu-id="01a85-106">Description</span></span>

<span data-ttu-id="01a85-107">指定された操作 `op` とターゲットの配列が適用され `targets` `op(Most(targets))` ます。</span><span class="sxs-lookup"><span data-stu-id="01a85-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="01a85-108">入力</span><span class="sxs-lookup"><span data-stu-id="01a85-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="01a85-109">op: ' t [] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="01a85-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="01a85-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="01a85-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="01a85-111">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="01a85-111">targets : 'T[]</span></span>

<span data-ttu-id="01a85-112">ターゲットの配列。最後のすべてのが適用され `op` ます。</span><span class="sxs-lookup"><span data-stu-id="01a85-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="01a85-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="01a85-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="01a85-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="01a85-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="01a85-115">&</span><span class="sxs-lookup"><span data-stu-id="01a85-115">'T</span></span>

<span data-ttu-id="01a85-116">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="01a85-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="01a85-117">参照</span><span class="sxs-lookup"><span data-stu-id="01a85-117">See Also</span></span>

- [<span data-ttu-id="01a85-118">Microsoft...。</span><span class="sxs-lookup"><span data-stu-id="01a85-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="01a85-119">Microsoft....。</span><span class="sxs-lookup"><span data-stu-id="01a85-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="01a85-120">Microsoft. Canon. Applytoほとんどの Ca</span><span class="sxs-lookup"><span data-stu-id="01a85-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)