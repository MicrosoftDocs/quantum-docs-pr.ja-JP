---
uid: Microsoft.Quantum.Arrays.Transposed
title: 転置関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 54071c461cf9f9411c332763b81e3bc448fb6c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718814"
---
# <a name="transposed-function"></a><span data-ttu-id="2888e-102">転置関数</span><span class="sxs-lookup"><span data-stu-id="2888e-102">Transposed function</span></span>

<span data-ttu-id="2888e-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2888e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2888e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2888e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2888e-105">配列の配列として表される行列の転置を返します。</span><span class="sxs-lookup"><span data-stu-id="2888e-105">Returns the transpose of a matrix represented as an array of arrays.</span></span>

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="2888e-106">説明</span><span class="sxs-lookup"><span data-stu-id="2888e-106">Description</span></span>

<span data-ttu-id="2888e-107">$R $ rows と $c $ columns を含む $r/倍 c $ マトリックスとして入力します。</span><span class="sxs-lookup"><span data-stu-id="2888e-107">Input as an $r \times c$ matrix with $r$ rows and $c$ columns.</span></span>  <span data-ttu-id="2888e-108">マトリックスは行ベースであり、つまり、 `matrix[i][j]` 行 $i $ および column $j $ の要素にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2888e-108">The matrix is row-based, i.e., `matrix[i][j]` accesses the element at row $i$ and column $j$.</span></span>

<span data-ttu-id="2888e-109">この関数は、入力行列の転置である $c/倍 r $ matrix を返します。</span><span class="sxs-lookup"><span data-stu-id="2888e-109">This function returns the $c \times r$ matrix that is the transpose of the input matrix.</span></span>

## <a name="input"></a><span data-ttu-id="2888e-110">入力</span><span class="sxs-lookup"><span data-stu-id="2888e-110">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="2888e-111">マトリックス: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="2888e-111">matrix : 'T[][]</span></span>

<span data-ttu-id="2888e-112">行ベースの $r/倍 c $ マトリックス</span><span class="sxs-lookup"><span data-stu-id="2888e-112">Row-based $r \times c$ matrix</span></span>



## <a name="output--t"></a><span data-ttu-id="2888e-113">出力: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="2888e-113">Output : 'T[][]</span></span>

<span data-ttu-id="2888e-114">転置 $c/x r $ matrix</span><span class="sxs-lookup"><span data-stu-id="2888e-114">Transposed $c \times r$ matrix</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2888e-115">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="2888e-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2888e-116">&</span><span class="sxs-lookup"><span data-stu-id="2888e-116">'T</span></span>

<span data-ttu-id="2888e-117">の各要素の型 `matrix` 。</span><span class="sxs-lookup"><span data-stu-id="2888e-117">The type of each element of `matrix`.</span></span>