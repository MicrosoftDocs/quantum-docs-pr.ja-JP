---
uid: Microsoft.Quantum.Arrays.Unzipped
title: 関数の解凍
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 37c960dc5dbdb8099fbebe1ad63cb44ce642733c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718790"
---
# <a name="unzipped-function"></a><span data-ttu-id="68d30-102">関数の解凍</span><span class="sxs-lookup"><span data-stu-id="68d30-102">Unzipped function</span></span>

<span data-ttu-id="68d30-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="68d30-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="68d30-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="68d30-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="68d30-105">2組の配列を指定すると、2つの配列の組を返します。各配列には、入力配列の組の要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="68d30-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="68d30-106">入力</span><span class="sxs-lookup"><span data-stu-id="68d30-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="68d30-107">arr: (' U '、' U) []</span><span class="sxs-lookup"><span data-stu-id="68d30-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="68d30-108">2つのタプルを含む配列</span><span class="sxs-lookup"><span data-stu-id="68d30-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="68d30-109">出力: (' t [], ' U [])</span><span class="sxs-lookup"><span data-stu-id="68d30-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="68d30-110">2つの配列 (最初の1つは入力タプルの最初の要素、2つ目は入力タプルの2番目の要素を含んでいます)。</span><span class="sxs-lookup"><span data-stu-id="68d30-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="68d30-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="68d30-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="68d30-112">&</span><span class="sxs-lookup"><span data-stu-id="68d30-112">'T</span></span>

<span data-ttu-id="68d30-113">各組の最初の要素の型</span><span class="sxs-lookup"><span data-stu-id="68d30-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="68d30-114">' U</span><span class="sxs-lookup"><span data-stu-id="68d30-114">'U</span></span>

<span data-ttu-id="68d30-115">各組の2番目の要素の型</span><span class="sxs-lookup"><span data-stu-id="68d30-115">The type of the second element in each tuple</span></span>

## <a name="see-also"></a><span data-ttu-id="68d30-116">参照</span><span class="sxs-lookup"><span data-stu-id="68d30-116">See Also</span></span>

- [<span data-ttu-id="68d30-117">Microsoft.Quantum.Arrays.Zip中</span><span class="sxs-lookup"><span data-stu-id="68d30-117">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)