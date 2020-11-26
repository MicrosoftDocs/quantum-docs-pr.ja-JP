---
uid: Microsoft.Quantum.Arrays.Where
title: Where 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 97598aa25d2d085aaab94f3d60ee64db9e2b89d6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219925"
---
# <a name="where-function"></a><span data-ttu-id="cfaae-102">Where 関数</span><span class="sxs-lookup"><span data-stu-id="cfaae-102">Where function</span></span>

<span data-ttu-id="cfaae-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="cfaae-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="cfaae-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cfaae-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cfaae-105">述語と配列が指定されている場合、述語が true である配列のインデックスを返します。</span><span class="sxs-lookup"><span data-stu-id="cfaae-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="cfaae-106">入力</span><span class="sxs-lookup"><span data-stu-id="cfaae-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="cfaae-107">述語: > [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cfaae-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cfaae-108">`'T`要素をフィルター処理するために使用されるブール値からブール型への関数。</span><span class="sxs-lookup"><span data-stu-id="cfaae-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="cfaae-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="cfaae-109">array : 'T[]</span></span>

<span data-ttu-id="cfaae-110">上の要素の配列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="cfaae-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="cfaae-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="cfaae-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="cfaae-112">が true であるインデックスの配列。 `predicate`</span><span class="sxs-lookup"><span data-stu-id="cfaae-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="cfaae-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="cfaae-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cfaae-114">&</span><span class="sxs-lookup"><span data-stu-id="cfaae-114">'T</span></span>

<span data-ttu-id="cfaae-115">要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="cfaae-115">The type of `array` elements.</span></span>