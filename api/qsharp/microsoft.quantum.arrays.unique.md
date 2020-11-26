---
uid: Microsoft.Quantum.Arrays.Unique
title: Unique 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: 7964d5d41eb68cb05f9414164d69496c1f76eb08
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220010"
---
# <a name="unique-function"></a><span data-ttu-id="bedce-102">Unique 関数</span><span class="sxs-lookup"><span data-stu-id="bedce-102">Unique function</span></span>

<span data-ttu-id="bedce-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bedce-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bedce-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bedce-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bedce-105">隣接する要素が等しくない新しい配列を返します。</span><span class="sxs-lookup"><span data-stu-id="bedce-105">Returns a new array that has no equal adjacent elements.</span></span>

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="bedce-106">説明</span><span class="sxs-lookup"><span data-stu-id="bedce-106">Description</span></span>

<span data-ttu-id="bedce-107">要素の配列と関数が等しいかどうかをテストするために、この関数は要素の相対順序を保持する新しい配列を返しますが、等しいすべての隣接する要素は、1つの要素だけにフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="bedce-107">Given some array of elements and a function to test equality, this function returns a new array in which the relative order of elements is kept, but all adjacent elements which are equal are filtered to just a single element.</span></span>

## <a name="input"></a><span data-ttu-id="bedce-108">入力</span><span class="sxs-lookup"><span data-stu-id="bedce-108">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="bedce-109">equal: (t, t)-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bedce-109">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bedce-110">`a` `b` がである場合にと等しいと見なされる2つの要素を比較する関数 `equal(a, b)` `true` 。</span><span class="sxs-lookup"><span data-stu-id="bedce-110">A function that compares two elements such that `a` is considered to be equal to `b` if `equal(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="bedce-111">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="bedce-111">array : 'T[]</span></span>

<span data-ttu-id="bedce-112">一意の要素をフィルター処理する対象の配列。</span><span class="sxs-lookup"><span data-stu-id="bedce-112">The array to be filtered for unique elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="bedce-113">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="bedce-113">Output : 'T[]</span></span>

<span data-ttu-id="bedce-114">隣接する要素が等しくない配列。</span><span class="sxs-lookup"><span data-stu-id="bedce-114">Array with no equal adjacent elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bedce-115">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="bedce-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bedce-116">&</span><span class="sxs-lookup"><span data-stu-id="bedce-116">'T</span></span>

<span data-ttu-id="bedce-117">の各要素の型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="bedce-117">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="bedce-118">解説</span><span class="sxs-lookup"><span data-stu-id="bedce-118">Remarks</span></span>

<span data-ttu-id="bedce-119">等しいが、互いに隣接していない複数の要素がある場合は、出力配列に複数の要素が出現します。</span><span class="sxs-lookup"><span data-stu-id="bedce-119">If there are multiple elements that are equal but not next to each other, there will be multiple occurrences in the output array.</span></span>  <span data-ttu-id="bedce-120">この関数をと共に使用して `Sorted` 、一意の要素全体を含む配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="bedce-120">Use this function together with `Sorted` to get an array with overall unique elements.</span></span>