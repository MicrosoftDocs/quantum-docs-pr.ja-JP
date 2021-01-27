---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: IterateThroughCartesianProduct 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: a0aaa8ef6aa6798d31c810254c92820f8136800c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840276"
---
# <a name="iteratethroughcartesianproduct-operation"></a><span data-ttu-id="1d98c-102">IterateThroughCartesianProduct 操作</span><span class="sxs-lookup"><span data-stu-id="1d98c-102">IterateThroughCartesianProduct operation</span></span>

<span data-ttu-id="1d98c-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1d98c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1d98c-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1d98c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1d98c-105">複数の範囲のデカルト積の各インデックスに対して操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="1d98c-105">Applies an operation for each index in the Cartesian product of several ranges.</span></span>

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="1d98c-106">説明</span><span class="sxs-lookup"><span data-stu-id="1d98c-106">Description</span></span>

<span data-ttu-id="1d98c-107">`0..(bounds[0] - 1)`、、 `0..(bounds[1] - 1)` ...、のデカルト積の各要素に対して、反復的に操作を適用します。`0..(bounds[Length(bounds) - 1] - 1)`</span><span class="sxs-lookup"><span data-stu-id="1d98c-107">Iteratively applies an operation for each element of the Cartesian product of `0..(bounds[0] - 1)`, `0..(bounds[1] - 1)`, ..., `0..(bounds[Length(bounds) - 1] - 1)`</span></span>

## <a name="input"></a><span data-ttu-id="1d98c-108">入力</span><span class="sxs-lookup"><span data-stu-id="1d98c-108">Input</span></span>

### <a name="bounds--int"></a><span data-ttu-id="1d98c-109">境界: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="1d98c-109">bounds : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="1d98c-110">反復処理する範囲を指定する配列。各範囲は整数長として指定されます。</span><span class="sxs-lookup"><span data-stu-id="1d98c-110">An array specifying the ranges to be iterated over, with each range being specified as an integer length.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="1d98c-111">op: [Int](xref:microsoft.quantum.lang-ref.int)[] => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1d98c-111">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="1d98c-112">指定されたデカルト積の各要素に対して呼び出される操作。</span><span class="sxs-lookup"><span data-stu-id="1d98c-112">An operation to be called for each element of the given Cartesian product.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1d98c-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1d98c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="1d98c-114">例</span><span class="sxs-lookup"><span data-stu-id="1d98c-114">Example</span></span>

<span data-ttu-id="1d98c-115">操作を指定した `op` 場合、次の2つのスニペットは同等です。</span><span class="sxs-lookup"><span data-stu-id="1d98c-115">Given an operation `op`, the following two snippets are equivalent:</span></span>

```qsharp
IterateThroughCartesianProduct([3, 4, 5], op);
```

```qsharp
op([0, 0, 0]);
op([1, 0, 0]);
op([2, 0, 0]);
op([0, 1, 0]);
// ...
op([0, 3, 0]);
op([0, 0, 1]);
//
op([2, 3, 4]);
```

## <a name="see-also"></a><span data-ttu-id="1d98c-116">参照</span><span class="sxs-lookup"><span data-stu-id="1d98c-116">See Also</span></span>

- [<span data-ttu-id="1d98c-117">Microsoft. IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="1d98c-117">Microsoft.Quantum.Canon.IterateThroughCartesianPower</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)