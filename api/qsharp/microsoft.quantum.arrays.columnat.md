---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: カラム Nat 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: ad09ada1a2253a54e70dddd6dba8aa243d2cd5a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719455"
---
# <a name="columnat-function"></a><span data-ttu-id="0412a-102">カラム Nat 関数</span><span class="sxs-lookup"><span data-stu-id="0412a-102">ColumnAt function</span></span>

<span data-ttu-id="0412a-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0412a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0412a-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0412a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0412a-105">マトリックスから列を抽出します。</span><span class="sxs-lookup"><span data-stu-id="0412a-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="0412a-106">説明</span><span class="sxs-lookup"><span data-stu-id="0412a-106">Description</span></span>

<span data-ttu-id="0412a-107">この関数は、行方向の順序で行列内の列を抽出します。</span><span class="sxs-lookup"><span data-stu-id="0412a-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="0412a-108">行 corrsponds を最初のインデックスの要素アクセスに抽出すると、それ以上の処理は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="0412a-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="0412a-109">入力</span><span class="sxs-lookup"><span data-stu-id="0412a-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="0412a-110">列: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0412a-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0412a-111">マトリックスの列</span><span class="sxs-lookup"><span data-stu-id="0412a-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="0412a-112">マトリックス: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="0412a-112">matrix : 'T[][]</span></span>

<span data-ttu-id="0412a-113">2次元行列 (行方向)</span><span class="sxs-lookup"><span data-stu-id="0412a-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="0412a-114">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="0412a-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0412a-115">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="0412a-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0412a-116">&</span><span class="sxs-lookup"><span data-stu-id="0412a-116">'T</span></span>

<span data-ttu-id="0412a-117">の各要素の型 `matrix` 。</span><span class="sxs-lookup"><span data-stu-id="0412a-117">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0412a-118">参照</span><span class="sxs-lookup"><span data-stu-id="0412a-118">See Also</span></span>

- [<span data-ttu-id="0412a-119">Microsoft... 配列. 転置</span><span class="sxs-lookup"><span data-stu-id="0412a-119">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="0412a-120">Microsoft.................</span><span class="sxs-lookup"><span data-stu-id="0412a-120">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)