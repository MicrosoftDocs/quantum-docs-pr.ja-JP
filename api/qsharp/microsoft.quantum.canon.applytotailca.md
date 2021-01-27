---
uid: Microsoft.Quantum.Canon.ApplyToTailCA
title: Ca の適用操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailCA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 4c702a9d310adae7a4ec404f3cf12893547623b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841195"
---
# <a name="applytotailca-operation"></a><span data-ttu-id="70cfb-102">Ca の適用操作</span><span class="sxs-lookup"><span data-stu-id="70cfb-102">ApplyToTailCA operation</span></span>

<span data-ttu-id="70cfb-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="70cfb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="70cfb-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="70cfb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="70cfb-105">配列の最後の要素に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="70cfb-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="70cfb-106">説明</span><span class="sxs-lookup"><span data-stu-id="70cfb-106">Description</span></span>

<span data-ttu-id="70cfb-107">指定された操作 `op` とターゲットの配列が適用され `targets` `op(Tail(targets))` ます。</span><span class="sxs-lookup"><span data-stu-id="70cfb-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="70cfb-108">入力</span><span class="sxs-lookup"><span data-stu-id="70cfb-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="70cfb-109">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="70cfb-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="70cfb-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="70cfb-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="70cfb-111">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="70cfb-111">targets : 'T[]</span></span>

<span data-ttu-id="70cfb-112">最後のが適用されるターゲットの配列 `op` 。</span><span class="sxs-lookup"><span data-stu-id="70cfb-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="70cfb-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="70cfb-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="70cfb-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="70cfb-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="70cfb-115">&</span><span class="sxs-lookup"><span data-stu-id="70cfb-115">'T</span></span>

<span data-ttu-id="70cfb-116">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="70cfb-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="70cfb-117">参照</span><span class="sxs-lookup"><span data-stu-id="70cfb-117">See Also</span></span>

- [<span data-ttu-id="70cfb-118">Microsoft. Canon. 適用</span><span class="sxs-lookup"><span data-stu-id="70cfb-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="70cfb-119">Microsoft.... "</span><span class="sxs-lookup"><span data-stu-id="70cfb-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="70cfb-120">Microsoft......。</span><span class="sxs-lookup"><span data-stu-id="70cfb-120">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)