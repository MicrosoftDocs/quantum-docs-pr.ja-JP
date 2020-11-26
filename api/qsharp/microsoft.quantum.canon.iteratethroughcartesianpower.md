---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: IterateThroughCartesianPower 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 2883e7cb30633afe51d380befe806665207c5abd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206478"
---
# <a name="iteratethroughcartesianpower-operation"></a><span data-ttu-id="0f3ec-102">IterateThroughCartesianPower 操作</span><span class="sxs-lookup"><span data-stu-id="0f3ec-102">IterateThroughCartesianPower operation</span></span>

<span data-ttu-id="0f3ec-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0f3ec-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0f3ec-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0f3ec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0f3ec-105">整数範囲のデカルト乗の各インデックスに演算を適用します。</span><span class="sxs-lookup"><span data-stu-id="0f3ec-105">Applies an operation for each index in the Cartesian power of an integer range.</span></span>

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="0f3ec-106">説明</span><span class="sxs-lookup"><span data-stu-id="0f3ec-106">Description</span></span>

<span data-ttu-id="0f3ec-107">範囲のデカルト乗の各要素に対して、反復的に操作を適用 `0..(bound - 1)` します。</span><span class="sxs-lookup"><span data-stu-id="0f3ec-107">Iteratively applies an operation for each element of a Cartesian power of the range `0..(bound - 1)`.</span></span>

## <a name="input"></a><span data-ttu-id="0f3ec-108">入力</span><span class="sxs-lookup"><span data-stu-id="0f3ec-108">Input</span></span>

### <a name="power--int"></a><span data-ttu-id="0f3ec-109">power: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0f3ec-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0f3ec-110">範囲が発生する必要があるデカルト指数 `0..(bound - 1)` 。</span><span class="sxs-lookup"><span data-stu-id="0f3ec-110">The Cartesian power to which the range `0..(bound - 1)` should be raised.</span></span>


### <a name="bound--int"></a><span data-ttu-id="0f3ec-111">バインド済み: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0f3ec-111">bound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0f3ec-112">反復処理する範囲を指定します。範囲の長さとして指定します。</span><span class="sxs-lookup"><span data-stu-id="0f3ec-112">A specification of the range to be iterated over, given as the length of the range.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="0f3ec-113">op: [Int](xref:microsoft.quantum.lang-ref.int)[] => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f3ec-113">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0f3ec-114">指定されたデカルト乗の各要素に対して呼び出される操作。</span><span class="sxs-lookup"><span data-stu-id="0f3ec-114">An operation to be called for each element of the given Cartesian power.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0f3ec-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f3ec-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="0f3ec-116">参照</span><span class="sxs-lookup"><span data-stu-id="0f3ec-116">See Also</span></span>

- [<span data-ttu-id="0f3ec-117">Microsoft. IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="0f3ec-117">Microsoft.Quantum.Canon.IterateThroughCartesianProduct</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)