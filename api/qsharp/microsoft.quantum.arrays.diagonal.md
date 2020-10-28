---
uid: Microsoft.Quantum.Arrays.Diagonal
title: 対角線関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 180b7185c94d712fa02100cb97abfbb6c464d12a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719383"
---
# <a name="diagonal-function"></a><span data-ttu-id="ee4ca-102">対角線関数</span><span class="sxs-lookup"><span data-stu-id="ee4ca-102">Diagonal function</span></span>

<span data-ttu-id="ee4ca-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ee4ca-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ee4ca-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ee4ca-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ee4ca-105">2次元配列の対角線要素の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="ee4ca-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="ee4ca-106">説明</span><span class="sxs-lookup"><span data-stu-id="ee4ca-106">Description</span></span>

<span data-ttu-id="ee4ca-107">2次元配列が二乗図形でない場合は、行と列の数の最小値に対する対角線が返されます。</span><span class="sxs-lookup"><span data-stu-id="ee4ca-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="ee4ca-108">入力</span><span class="sxs-lookup"><span data-stu-id="ee4ca-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="ee4ca-109">マトリックス: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="ee4ca-109">matrix : 'T[][]</span></span>

<span data-ttu-id="ee4ca-110">2次元行列 (行方向)</span><span class="sxs-lookup"><span data-stu-id="ee4ca-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="ee4ca-111">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="ee4ca-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ee4ca-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="ee4ca-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ee4ca-113">&</span><span class="sxs-lookup"><span data-stu-id="ee4ca-113">'T</span></span>

<span data-ttu-id="ee4ca-114">の各要素の型 `matrix` 。</span><span class="sxs-lookup"><span data-stu-id="ee4ca-114">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee4ca-115">参照</span><span class="sxs-lookup"><span data-stu-id="ee4ca-115">See Also</span></span>

- [<span data-ttu-id="ee4ca-116">Microsoft... 配列. 転置</span><span class="sxs-lookup"><span data-stu-id="ee4ca-116">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)