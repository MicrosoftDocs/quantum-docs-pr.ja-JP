---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 7ff80f13f432a18f216b2dee4bd65b1e82034fa5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719174"
---
# <a name="indexof-function"></a><span data-ttu-id="24e58-102">IndexOf 関数</span><span class="sxs-lookup"><span data-stu-id="24e58-102">IndexOf function</span></span>

<span data-ttu-id="24e58-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="24e58-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="24e58-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="24e58-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="24e58-105">指定された述語を満たす配列内の最初の要素の最初のインデックスを返します。</span><span class="sxs-lookup"><span data-stu-id="24e58-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="24e58-106">そのような要素が存在しない場合は、-1 を返します。</span><span class="sxs-lookup"><span data-stu-id="24e58-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="24e58-107">入力</span><span class="sxs-lookup"><span data-stu-id="24e58-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="24e58-108">述語: > [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="24e58-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="24e58-109">配列の要素に対して動作する述語関数。</span><span class="sxs-lookup"><span data-stu-id="24e58-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="24e58-110">arr: ' t []</span><span class="sxs-lookup"><span data-stu-id="24e58-110">arr : 'T[]</span></span>

<span data-ttu-id="24e58-111">指定された述語を使用して検索される配列。</span><span class="sxs-lookup"><span data-stu-id="24e58-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="24e58-112">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="24e58-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="24e58-113">`idx`が true であるような最小のインデックス `predicate(arr[idx])` 。そのような要素が存在しない場合は-1。</span><span class="sxs-lookup"><span data-stu-id="24e58-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="24e58-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="24e58-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="24e58-115">&</span><span class="sxs-lookup"><span data-stu-id="24e58-115">'T</span></span>

