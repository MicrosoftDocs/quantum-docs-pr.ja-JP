---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: IterateThroughCartesianProduct 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: e4fc71f6f707639f6f89eece8546ec2fb434a15a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716037"
---
# <a name="iteratethroughcartesianproduct-operation"></a><span data-ttu-id="78897-102">IterateThroughCartesianProduct 操作</span><span class="sxs-lookup"><span data-stu-id="78897-102">IterateThroughCartesianProduct operation</span></span>

<span data-ttu-id="78897-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="78897-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="78897-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="78897-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="78897-105">複数の範囲のデカルト積の各インデックスに対して操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="78897-105">Applies an operation for each index in the Cartesian product of several ranges.</span></span>

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="78897-106">説明</span><span class="sxs-lookup"><span data-stu-id="78897-106">Description</span></span>

<span data-ttu-id="78897-107">`0..(bounds[0] - 1)`、、 `0..(bounds[1] - 1)` ...、のデカルト積の各要素に対して、反復的に操作を適用します。`0..(bounds[Length(bounds) - 1] - 1)`</span><span class="sxs-lookup"><span data-stu-id="78897-107">Iteratively applies an operation for each element of the Cartesian product of `0..(bounds[0] - 1)`, `0..(bounds[1] - 1)`, ..., `0..(bounds[Length(bounds) - 1] - 1)`</span></span>

## <a name="input"></a><span data-ttu-id="78897-108">入力</span><span class="sxs-lookup"><span data-stu-id="78897-108">Input</span></span>

### <a name="bounds--int"></a><span data-ttu-id="78897-109">境界: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="78897-109">bounds : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="78897-110">反復処理する範囲を指定する配列。各範囲は整数長として指定されます。</span><span class="sxs-lookup"><span data-stu-id="78897-110">An array specifying the ranges to be iterated over, with each range being specified as an integer length.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="78897-111">op: [Int](xref:microsoft.quantum.lang-ref.int)[] => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="78897-111">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="78897-112">指定されたデカルト積の各要素に対して呼び出される操作。</span><span class="sxs-lookup"><span data-stu-id="78897-112">An operation to be called for each element of the given Cartesian product.</span></span>



## <a name="output--unit"></a><span data-ttu-id="78897-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="78897-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="78897-114">参照</span><span class="sxs-lookup"><span data-stu-id="78897-114">See Also</span></span>

- [<span data-ttu-id="78897-115">Microsoft. IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="78897-115">Microsoft.Quantum.Canon.IterateThroughCartesianPower</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)