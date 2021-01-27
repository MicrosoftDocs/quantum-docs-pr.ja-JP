---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 64db55e831078a7130a3ced6a30bfbd2299c392d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848520"
---
# <a name="indexof-function"></a><span data-ttu-id="72cb8-102">IndexOf 関数</span><span class="sxs-lookup"><span data-stu-id="72cb8-102">IndexOf function</span></span>

<span data-ttu-id="72cb8-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="72cb8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="72cb8-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="72cb8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="72cb8-105">指定された述語を満たす配列内の最初の要素の最初のインデックスを返します。</span><span class="sxs-lookup"><span data-stu-id="72cb8-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="72cb8-106">そのような要素が存在しない場合は、-1 を返します。</span><span class="sxs-lookup"><span data-stu-id="72cb8-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="72cb8-107">入力</span><span class="sxs-lookup"><span data-stu-id="72cb8-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="72cb8-108">述語: > [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="72cb8-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="72cb8-109">配列の要素に対して動作する述語関数。</span><span class="sxs-lookup"><span data-stu-id="72cb8-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="72cb8-110">arr: ' t []</span><span class="sxs-lookup"><span data-stu-id="72cb8-110">arr : 'T[]</span></span>

<span data-ttu-id="72cb8-111">指定された述語を使用して検索される配列。</span><span class="sxs-lookup"><span data-stu-id="72cb8-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="72cb8-112">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="72cb8-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="72cb8-113">`idx`が true であるような最小のインデックス `predicate(arr[idx])` 。そのような要素が存在しない場合は-1。</span><span class="sxs-lookup"><span data-stu-id="72cb8-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="72cb8-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="72cb8-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="72cb8-115">&</span><span class="sxs-lookup"><span data-stu-id="72cb8-115">'T</span></span>



## <a name="example"></a><span data-ttu-id="72cb8-116">例</span><span class="sxs-lookup"><span data-stu-id="72cb8-116">Example</span></span>

<span data-ttu-id="72cb8-117">は、 `IsEven : Int -> Bool` 入力が偶数の場合にのみを返す関数であるとし `true` ます。</span><span class="sxs-lookup"><span data-stu-id="72cb8-117">Suppose that `IsEven : Int -> Bool` is a function that returns `true` if and only if its input is even.</span></span> <span data-ttu-id="72cb8-118">次に、これをと共に使用して、 `IndexOf` 配列内の最初の偶数の要素を検索できます。</span><span class="sxs-lookup"><span data-stu-id="72cb8-118">Then, this can be used with `IndexOf` to find the first even element in an array:</span></span>

```qsharp
let items = [1, 3, 17, 2, 21];
let idx = IndexOf(IsEven, items); // returns 3
```