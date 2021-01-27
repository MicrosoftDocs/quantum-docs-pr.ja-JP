---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: IterateThroughCartesianPower 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 3a303d13c4a6f102dab92d814e24df9d90213fbe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840296"
---
# <a name="iteratethroughcartesianpower-operation"></a><span data-ttu-id="0bc02-102">IterateThroughCartesianPower 操作</span><span class="sxs-lookup"><span data-stu-id="0bc02-102">IterateThroughCartesianPower operation</span></span>

<span data-ttu-id="0bc02-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0bc02-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0bc02-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0bc02-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0bc02-105">整数範囲のデカルト乗の各インデックスに演算を適用します。</span><span class="sxs-lookup"><span data-stu-id="0bc02-105">Applies an operation for each index in the Cartesian power of an integer range.</span></span>

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="0bc02-106">説明</span><span class="sxs-lookup"><span data-stu-id="0bc02-106">Description</span></span>

<span data-ttu-id="0bc02-107">範囲のデカルト乗の各要素に対して、反復的に操作を適用 `0..(bound - 1)` します。</span><span class="sxs-lookup"><span data-stu-id="0bc02-107">Iteratively applies an operation for each element of a Cartesian power of the range `0..(bound - 1)`.</span></span>

## <a name="input"></a><span data-ttu-id="0bc02-108">入力</span><span class="sxs-lookup"><span data-stu-id="0bc02-108">Input</span></span>

### <a name="power--int"></a><span data-ttu-id="0bc02-109">power: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0bc02-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0bc02-110">範囲が発生する必要があるデカルト指数 `0..(bound - 1)` 。</span><span class="sxs-lookup"><span data-stu-id="0bc02-110">The Cartesian power to which the range `0..(bound - 1)` should be raised.</span></span>


### <a name="bound--int"></a><span data-ttu-id="0bc02-111">バインド済み: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0bc02-111">bound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0bc02-112">反復処理する範囲を指定します。範囲の長さとして指定します。</span><span class="sxs-lookup"><span data-stu-id="0bc02-112">A specification of the range to be iterated over, given as the length of the range.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="0bc02-113">op: [Int](xref:microsoft.quantum.lang-ref.int)[] => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0bc02-113">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0bc02-114">指定されたデカルト乗の各要素に対して呼び出される操作。</span><span class="sxs-lookup"><span data-stu-id="0bc02-114">An operation to be called for each element of the given Cartesian power.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0bc02-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0bc02-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="0bc02-116">例</span><span class="sxs-lookup"><span data-stu-id="0bc02-116">Example</span></span>

<span data-ttu-id="0bc02-117">操作を指定した `op` 場合、次の2つのスニペットは同等です。</span><span class="sxs-lookup"><span data-stu-id="0bc02-117">Given an operation `op`, the following two snippets are equivalent:</span></span>

```qsharp
IterateThroughCartesianPower(2, 3, op);
```

```qsharp
op([0, 0]);
op([1, 0]);
op([2, 0]);
op([0, 1]);
// ..
op([2, 2]);
```

## <a name="see-also"></a><span data-ttu-id="0bc02-118">参照</span><span class="sxs-lookup"><span data-stu-id="0bc02-118">See Also</span></span>

- [<span data-ttu-id="0bc02-119">Microsoft. IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="0bc02-119">Microsoft.Quantum.Canon.IterateThroughCartesianProduct</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)