---
uid: Microsoft.Quantum.Arrays.Diagonal
title: 対角線関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 2857046f59a958fed106af0944b75baaa3292e96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842827"
---
# <a name="diagonal-function"></a><span data-ttu-id="b51ff-102">対角線関数</span><span class="sxs-lookup"><span data-stu-id="b51ff-102">Diagonal function</span></span>

<span data-ttu-id="b51ff-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b51ff-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b51ff-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b51ff-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b51ff-105">2次元配列の対角線要素の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="b51ff-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="b51ff-106">説明</span><span class="sxs-lookup"><span data-stu-id="b51ff-106">Description</span></span>

<span data-ttu-id="b51ff-107">2次元配列が二乗図形でない場合は、行と列の数の最小値に対する対角線が返されます。</span><span class="sxs-lookup"><span data-stu-id="b51ff-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="b51ff-108">入力</span><span class="sxs-lookup"><span data-stu-id="b51ff-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="b51ff-109">マトリックス: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="b51ff-109">matrix : 'T[][]</span></span>

<span data-ttu-id="b51ff-110">2次元行列 (行方向)</span><span class="sxs-lookup"><span data-stu-id="b51ff-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="b51ff-111">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="b51ff-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b51ff-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="b51ff-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b51ff-113">&</span><span class="sxs-lookup"><span data-stu-id="b51ff-113">'T</span></span>

<span data-ttu-id="b51ff-114">の各要素の型 `matrix` 。</span><span class="sxs-lookup"><span data-stu-id="b51ff-114">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="b51ff-115">例</span><span class="sxs-lookup"><span data-stu-id="b51ff-115">Example</span></span>

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let diagonal = Diagonal(matrix);
// same as: column = [1, 5, 9]
```

## <a name="see-also"></a><span data-ttu-id="b51ff-116">参照</span><span class="sxs-lookup"><span data-stu-id="b51ff-116">See Also</span></span>

- [<span data-ttu-id="b51ff-117">Microsoft... 配列. 転置</span><span class="sxs-lookup"><span data-stu-id="b51ff-117">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)