---
uid: Microsoft.Quantum.Canon.ApplyToHeadA
title: 操作の Applytoヘッド
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 290347ff54492c4291db540e82cedcdd822a354e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850651"
---
# <a name="applytoheada-operation"></a><span data-ttu-id="4793f-102">操作の Applytoヘッド</span><span class="sxs-lookup"><span data-stu-id="4793f-102">ApplyToHeadA operation</span></span>

<span data-ttu-id="4793f-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4793f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4793f-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4793f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4793f-105">配列の最初の要素に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="4793f-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="4793f-106">説明</span><span class="sxs-lookup"><span data-stu-id="4793f-106">Description</span></span>

<span data-ttu-id="4793f-107">指定された操作 `op` とターゲットの配列が適用され `targets` `op(Head(targets))` ます。</span><span class="sxs-lookup"><span data-stu-id="4793f-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="4793f-108">入力</span><span class="sxs-lookup"><span data-stu-id="4793f-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="4793f-109">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="4793f-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="4793f-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="4793f-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="4793f-111">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="4793f-111">targets : 'T[]</span></span>

<span data-ttu-id="4793f-112">最初のが適用されるターゲットの配列 `op` 。</span><span class="sxs-lookup"><span data-stu-id="4793f-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4793f-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4793f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4793f-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="4793f-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4793f-115">&</span><span class="sxs-lookup"><span data-stu-id="4793f-115">'T</span></span>

<span data-ttu-id="4793f-116">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="4793f-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="4793f-117">参照</span><span class="sxs-lookup"><span data-stu-id="4793f-117">See Also</span></span>

- [<span data-ttu-id="4793f-118">Microsoft. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="4793f-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="4793f-119">Microsoft. Canon. Applytoヘッド c</span><span class="sxs-lookup"><span data-stu-id="4793f-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="4793f-120">Microsoft. Canon. Applytoヘッド Ca</span><span class="sxs-lookup"><span data-stu-id="4793f-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)