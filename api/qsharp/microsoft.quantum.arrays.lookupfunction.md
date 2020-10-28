---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: c929054b96ee499db896cacf0e3ae4da6f6c4b98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719071"
---
# <a name="lookupfunction-function"></a><span data-ttu-id="afca3-102">LookupFunction 関数</span><span class="sxs-lookup"><span data-stu-id="afca3-102">LookupFunction function</span></span>

<span data-ttu-id="afca3-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="afca3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="afca3-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="afca3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="afca3-105">配列が指定されている場合、その配列の要素を返す関数を返します。</span><span class="sxs-lookup"><span data-stu-id="afca3-105">Given an array, returns a function which returns elements of that array.</span></span>

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a><span data-ttu-id="afca3-106">入力</span><span class="sxs-lookup"><span data-stu-id="afca3-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="afca3-107">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="afca3-107">array : 'T[]</span></span>

<span data-ttu-id="afca3-108">参照関数として表現される配列。</span><span class="sxs-lookup"><span data-stu-id="afca3-108">The array to be represented as a lookup function.</span></span>



## <a name="output--int---t"></a><span data-ttu-id="afca3-109">出力: [Int](xref:microsoft.quantum.lang-ref.int) -> t</span><span class="sxs-lookup"><span data-stu-id="afca3-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="afca3-110">`f`そのような関数 `f(idx) == f[idx]` 。</span><span class="sxs-lookup"><span data-stu-id="afca3-110">A function `f` such that `f(idx) == f[idx]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="afca3-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="afca3-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="afca3-112">&</span><span class="sxs-lookup"><span data-stu-id="afca3-112">'T</span></span>

<span data-ttu-id="afca3-113">参照関数として表される配列の要素の型。</span><span class="sxs-lookup"><span data-stu-id="afca3-113">The type of the elements of the array being represented as a lookup function.</span></span>

## <a name="remarks"></a><span data-ttu-id="afca3-114">解説</span><span class="sxs-lookup"><span data-stu-id="afca3-114">Remarks</span></span>

<span data-ttu-id="afca3-115">この関数は、 `Int -> 'T` 引数として関数を受け取る関数や操作と相互運用する場合に主に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="afca3-115">This function is mainly useful for interoperating with functions and operations that take `Int -> 'T` functions as their arguments.</span></span> <span data-ttu-id="afca3-116">これは、たとえば、ジェネレーター表現ライブラリ内で、配列全体をメモリに記録する必要がないようにするために関数が使用される場合などに共通します。</span><span class="sxs-lookup"><span data-stu-id="afca3-116">This is common, for instance, in the generator representation library, where functions are used to avoid the need to record an entire array in memory.</span></span>