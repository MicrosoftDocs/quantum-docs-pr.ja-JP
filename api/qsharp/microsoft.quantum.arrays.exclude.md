---
uid: Microsoft.Quantum.Arrays.Exclude
title: Exclude 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 76cdee56e84951c63e80babfdca6a3de33583cab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848671"
---
# <a name="exclude-function"></a><span data-ttu-id="2dca6-102">Exclude 関数</span><span class="sxs-lookup"><span data-stu-id="2dca6-102">Exclude function</span></span>

<span data-ttu-id="2dca6-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2dca6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2dca6-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2dca6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2dca6-105">指定されたインデックスリストの要素を除く、別の配列の要素を含む配列を返します。</span><span class="sxs-lookup"><span data-stu-id="2dca6-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="2dca6-106">入力</span><span class="sxs-lookup"><span data-stu-id="2dca6-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="2dca6-107">削除: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2dca6-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2dca6-108">出力から除外する要素を示すインデックスの配列。</span><span class="sxs-lookup"><span data-stu-id="2dca6-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="2dca6-109">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="2dca6-109">array : 'T[]</span></span>

<span data-ttu-id="2dca6-110">出力配列内の値を取得する対象の配列。</span><span class="sxs-lookup"><span data-stu-id="2dca6-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="2dca6-111">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="2dca6-111">Output : 'T[]</span></span>

<span data-ttu-id="2dca6-112">インデックスが `output` `output[0]` `array` に表示されない `remove` 、2番目の要素などのの最初の要素である配列 `output[1]` 。</span><span class="sxs-lookup"><span data-stu-id="2dca6-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2dca6-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="2dca6-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2dca6-114">&</span><span class="sxs-lookup"><span data-stu-id="2dca6-114">'T</span></span>

<span data-ttu-id="2dca6-115">配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="2dca6-115">The type of the array elements.</span></span>

## <a name="example"></a><span data-ttu-id="2dca6-116">例</span><span class="sxs-lookup"><span data-stu-id="2dca6-116">Example</span></span>

```qsharp
let array = [10, 11, 12, 13, 14, 15];
// The following line returns [10, 12, 15].
let subarray = Exclude([1, 3, 4], array);
```