---
uid: Microsoft.Quantum.Canon.ApplyToRestA
title: ApplyToRestA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 69001f6c8d65806e7259f2d2f2741d48866daa84
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841260"
---
# <a name="applytoresta-operation"></a><span data-ttu-id="acbe8-102">ApplyToRestA 操作</span><span class="sxs-lookup"><span data-stu-id="acbe8-102">ApplyToRestA operation</span></span>

<span data-ttu-id="acbe8-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="acbe8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="acbe8-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="acbe8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="acbe8-105">配列の最初の要素以外のすべてに操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="acbe8-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="acbe8-106">説明</span><span class="sxs-lookup"><span data-stu-id="acbe8-106">Description</span></span>

<span data-ttu-id="acbe8-107">指定された操作 `op` とターゲットの配列が適用され `targets` `op(Rest(targets))` ます。</span><span class="sxs-lookup"><span data-stu-id="acbe8-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="acbe8-108">入力</span><span class="sxs-lookup"><span data-stu-id="acbe8-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="acbe8-109">op: ' t [] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="acbe8-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="acbe8-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="acbe8-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="acbe8-111">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="acbe8-111">targets : 'T[]</span></span>

<span data-ttu-id="acbe8-112">ターゲットの配列。すべてのものが最初に適用され `op` ます。</span><span class="sxs-lookup"><span data-stu-id="acbe8-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="acbe8-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="acbe8-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="acbe8-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="acbe8-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="acbe8-115">&</span><span class="sxs-lookup"><span data-stu-id="acbe8-115">'T</span></span>

<span data-ttu-id="acbe8-116">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="acbe8-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="acbe8-117">参照</span><span class="sxs-lookup"><span data-stu-id="acbe8-117">See Also</span></span>

- [<span data-ttu-id="acbe8-118">Microsoft. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="acbe8-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="acbe8-119">Microsoft....。</span><span class="sxs-lookup"><span data-stu-id="acbe8-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="acbe8-120">Microsoft. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="acbe8-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)