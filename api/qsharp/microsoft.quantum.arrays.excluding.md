---
uid: Microsoft.Quantum.Arrays.Excluding
title: 除外 (関数を)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Excluding
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: c117431e3d98bba4ed3d29cb0b171247bf77be0b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848650"
---
# <a name="excluding-function"></a><span data-ttu-id="42a70-102">除外 (関数を)</span><span class="sxs-lookup"><span data-stu-id="42a70-102">Excluding function</span></span>

<span data-ttu-id="42a70-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="42a70-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="42a70-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="42a70-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="42a70-105">指定されたインデックスリストの要素を除く、別の配列の要素を含む配列を返します。</span><span class="sxs-lookup"><span data-stu-id="42a70-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Excluding<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="42a70-106">入力</span><span class="sxs-lookup"><span data-stu-id="42a70-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="42a70-107">削除: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="42a70-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="42a70-108">出力から除外する要素を示すインデックスの配列。</span><span class="sxs-lookup"><span data-stu-id="42a70-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="42a70-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="42a70-109">array : 'T[]</span></span>

<span data-ttu-id="42a70-110">出力配列内の値を取得する対象の配列。</span><span class="sxs-lookup"><span data-stu-id="42a70-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="42a70-111">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="42a70-111">Output : 'T[]</span></span>

<span data-ttu-id="42a70-112">インデックスが `output` `output[0]` `array` に表示されない `remove` 、2番目の要素などのの最初の要素である配列 `output[1]` 。</span><span class="sxs-lookup"><span data-stu-id="42a70-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="42a70-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="42a70-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="42a70-114">&</span><span class="sxs-lookup"><span data-stu-id="42a70-114">'T</span></span>

<span data-ttu-id="42a70-115">配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="42a70-115">The type of the array elements.</span></span>

## <a name="example"></a><span data-ttu-id="42a70-116">例</span><span class="sxs-lookup"><span data-stu-id="42a70-116">Example</span></span>

```qsharp
let array = [10, 11, 12, 13, 14, 15];
// The following line returns [10, 12, 15].
let subarray = Excluding([1, 3, 4], array);
```