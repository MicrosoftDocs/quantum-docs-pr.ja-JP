---
uid: Microsoft.Quantum.Arrays.Unzipped
title: 関数の解凍
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 7eea7982721dc596b8660be5f3634df71b1ddf95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845382"
---
# <a name="unzipped-function"></a><span data-ttu-id="bbc95-102">関数の解凍</span><span class="sxs-lookup"><span data-stu-id="bbc95-102">Unzipped function</span></span>

<span data-ttu-id="bbc95-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bbc95-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bbc95-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bbc95-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bbc95-105">2組の配列を指定すると、2つの配列の組を返します。各配列には、入力配列の組の要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bbc95-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="bbc95-106">入力</span><span class="sxs-lookup"><span data-stu-id="bbc95-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="bbc95-107">arr: (' U '、' U) []</span><span class="sxs-lookup"><span data-stu-id="bbc95-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="bbc95-108">2つのタプルを含む配列</span><span class="sxs-lookup"><span data-stu-id="bbc95-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="bbc95-109">出力: (' t [], ' U [])</span><span class="sxs-lookup"><span data-stu-id="bbc95-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="bbc95-110">2つの配列 (最初の1つは入力タプルの最初の要素、2つ目は入力タプルの2番目の要素を含んでいます)。</span><span class="sxs-lookup"><span data-stu-id="bbc95-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bbc95-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="bbc95-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bbc95-112">&</span><span class="sxs-lookup"><span data-stu-id="bbc95-112">'T</span></span>

<span data-ttu-id="bbc95-113">各組の最初の要素の型</span><span class="sxs-lookup"><span data-stu-id="bbc95-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="bbc95-114">' U</span><span class="sxs-lookup"><span data-stu-id="bbc95-114">'U</span></span>

<span data-ttu-id="bbc95-115">各組の2番目の要素の型</span><span class="sxs-lookup"><span data-stu-id="bbc95-115">The type of the second element in each tuple</span></span>

## <a name="example"></a><span data-ttu-id="bbc95-116">例</span><span class="sxs-lookup"><span data-stu-id="bbc95-116">Example</span></span>

```qsharp
// split is same as ([6, 5, 5, 3, 2, 1], [true, false, false, false, true, false])
let split = Unzipped([(6, true), (5, false), (5, false), (3, false), (2, true), (1, false)]);
```

## <a name="see-also"></a><span data-ttu-id="bbc95-117">参照</span><span class="sxs-lookup"><span data-stu-id="bbc95-117">See Also</span></span>

- [<span data-ttu-id="bbc95-118">Microsoft.Quantum.Arrays.Zip中</span><span class="sxs-lookup"><span data-stu-id="bbc95-118">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)