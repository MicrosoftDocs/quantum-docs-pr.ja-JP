---
uid: Microsoft.Quantum.Arrays.Where
title: Where 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 4a938114689177f7a9ee182e6e5f36debe4edac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842216"
---
# <a name="where-function"></a><span data-ttu-id="9a305-102">Where 関数</span><span class="sxs-lookup"><span data-stu-id="9a305-102">Where function</span></span>

<span data-ttu-id="9a305-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9a305-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9a305-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9a305-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9a305-105">述語と配列が指定されている場合、述語が true である配列のインデックスを返します。</span><span class="sxs-lookup"><span data-stu-id="9a305-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="9a305-106">入力</span><span class="sxs-lookup"><span data-stu-id="9a305-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="9a305-107">述語: > [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9a305-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9a305-108">`'T`要素をフィルター処理するために使用されるブール値からブール型への関数。</span><span class="sxs-lookup"><span data-stu-id="9a305-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="9a305-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="9a305-109">array : 'T[]</span></span>

<span data-ttu-id="9a305-110">上の要素の配列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="9a305-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="9a305-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="9a305-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="9a305-112">が true であるインデックスの配列。 `predicate`</span><span class="sxs-lookup"><span data-stu-id="9a305-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9a305-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="9a305-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9a305-114">&</span><span class="sxs-lookup"><span data-stu-id="9a305-114">'T</span></span>

<span data-ttu-id="9a305-115">要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="9a305-115">The type of `array` elements.</span></span>