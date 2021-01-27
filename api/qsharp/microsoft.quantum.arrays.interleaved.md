---
uid: Microsoft.Quantum.Arrays.Interleaved
title: インターリーブ関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 3605c0d0bc43cdb1097d025861c3ec2424763c86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848106"
---
# <a name="interleaved-function"></a><span data-ttu-id="46389-102">インターリーブ関数</span><span class="sxs-lookup"><span data-stu-id="46389-102">Interleaved function</span></span>

<span data-ttu-id="46389-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="46389-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="46389-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="46389-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="46389-105">(ほぼ) 同じサイズの2つの配列を相互に保持します。</span><span class="sxs-lookup"><span data-stu-id="46389-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="46389-106">説明</span><span class="sxs-lookup"><span data-stu-id="46389-106">Description</span></span>

<span data-ttu-id="46389-107">この関数は、2つの配列のインターリーブを返します。最初の配列の最初の要素、2番目の配列の最初の要素、およびなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="46389-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="46389-108">最初の配列は、2番目の配列と同じ長さであるか、または1つ以上の要素を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="46389-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="46389-109">入力</span><span class="sxs-lookup"><span data-stu-id="46389-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="46389-110">最初: ' t []</span><span class="sxs-lookup"><span data-stu-id="46389-110">first : 'T[]</span></span>

<span data-ttu-id="46389-111">インターリーブされる最初の配列。</span><span class="sxs-lookup"><span data-stu-id="46389-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="46389-112">2番目: ' t []</span><span class="sxs-lookup"><span data-stu-id="46389-112">second : 'T[]</span></span>

<span data-ttu-id="46389-113">インターリーブする2番目の配列。</span><span class="sxs-lookup"><span data-stu-id="46389-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="46389-114">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="46389-114">Output : 'T[]</span></span>

<span data-ttu-id="46389-115">インターリーブ配列</span><span class="sxs-lookup"><span data-stu-id="46389-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="46389-116">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="46389-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="46389-117">&</span><span class="sxs-lookup"><span data-stu-id="46389-117">'T</span></span>

<span data-ttu-id="46389-118">およびの各要素の型 `first` `second` 。</span><span class="sxs-lookup"><span data-stu-id="46389-118">The type of each element of `first` and `second`.</span></span>

## <a name="example"></a><span data-ttu-id="46389-119">例</span><span class="sxs-lookup"><span data-stu-id="46389-119">Example</span></span>

```qsharp
// same as int1 = [1, -1, 2, -2, 3, -3]
let int1 = Interleaved([1, 2, 3], [-1, -2, -3])

// same as int2 = [false, true, false, true, false]
let int2 = Interleaved(ConstantArray(3, false), ConstantArray(2, true));
```