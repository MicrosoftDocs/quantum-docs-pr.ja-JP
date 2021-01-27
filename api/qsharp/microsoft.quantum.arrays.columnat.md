---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: カラム Nat 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 32dc814de9b04563c2798a768f121723a1a8252c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846254"
---
# <a name="columnat-function"></a><span data-ttu-id="a35f0-102">カラム Nat 関数</span><span class="sxs-lookup"><span data-stu-id="a35f0-102">ColumnAt function</span></span>

<span data-ttu-id="a35f0-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a35f0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a35f0-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a35f0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a35f0-105">マトリックスから列を抽出します。</span><span class="sxs-lookup"><span data-stu-id="a35f0-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="a35f0-106">説明</span><span class="sxs-lookup"><span data-stu-id="a35f0-106">Description</span></span>

<span data-ttu-id="a35f0-107">この関数は、行方向の順序で行列内の列を抽出します。</span><span class="sxs-lookup"><span data-stu-id="a35f0-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="a35f0-108">行 corrsponds を最初のインデックスの要素アクセスに抽出すると、それ以上の処理は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a35f0-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="a35f0-109">入力</span><span class="sxs-lookup"><span data-stu-id="a35f0-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="a35f0-110">列: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a35f0-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a35f0-111">マトリックスの列</span><span class="sxs-lookup"><span data-stu-id="a35f0-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="a35f0-112">マトリックス: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="a35f0-112">matrix : 'T[][]</span></span>

<span data-ttu-id="a35f0-113">2次元行列 (行方向)</span><span class="sxs-lookup"><span data-stu-id="a35f0-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="a35f0-114">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="a35f0-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a35f0-115">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="a35f0-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a35f0-116">&</span><span class="sxs-lookup"><span data-stu-id="a35f0-116">'T</span></span>

<span data-ttu-id="a35f0-117">の各要素の型 `matrix` 。</span><span class="sxs-lookup"><span data-stu-id="a35f0-117">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="a35f0-118">例</span><span class="sxs-lookup"><span data-stu-id="a35f0-118">Example</span></span>

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let column = ColumnAt(0, matrix);
// same as: column = [1, 4, 7]
```

## <a name="see-also"></a><span data-ttu-id="a35f0-119">参照</span><span class="sxs-lookup"><span data-stu-id="a35f0-119">See Also</span></span>

- [<span data-ttu-id="a35f0-120">Microsoft... 配列. 転置</span><span class="sxs-lookup"><span data-stu-id="a35f0-120">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="a35f0-121">Microsoft.................</span><span class="sxs-lookup"><span data-stu-id="a35f0-121">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)