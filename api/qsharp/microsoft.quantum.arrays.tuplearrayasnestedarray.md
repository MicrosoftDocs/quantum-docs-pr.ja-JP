---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: TupleArrayAsNestedArray 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: 917f35db949790ab3ae6e7a2184bcfcf5ed50be6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718807"
---
# <a name="tuplearrayasnestedarray-function"></a><span data-ttu-id="28b41-102">TupleArrayAsNestedArray 関数</span><span class="sxs-lookup"><span data-stu-id="28b41-102">TupleArrayAsNestedArray function</span></span>

<span data-ttu-id="28b41-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="28b41-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="28b41-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="28b41-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="28b41-105">2つのタプルのリストを入れ子になった配列に変換します。</span><span class="sxs-lookup"><span data-stu-id="28b41-105">Turns a list of 2-tuples into a nested array.</span></span>

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="28b41-106">入力</span><span class="sxs-lookup"><span data-stu-id="28b41-106">Input</span></span>

### <a name="tuplelist--tt"></a><span data-ttu-id="28b41-107">tupleList: (t, t) []</span><span class="sxs-lookup"><span data-stu-id="28b41-107">tupleList : ('T,'T)[]</span></span>

<span data-ttu-id="28b41-108">入れ子になった配列に変換される2組のリスト。</span><span class="sxs-lookup"><span data-stu-id="28b41-108">List of 2-tuples to be turned into a nested array.</span></span>



## <a name="output--t"></a><span data-ttu-id="28b41-109">出力: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="28b41-109">Output : 'T[][]</span></span>

<span data-ttu-id="28b41-110">TupleList に一致する長さの入れ子になった配列。</span><span class="sxs-lookup"><span data-stu-id="28b41-110">A nested array with length matching the tupleList.</span></span>

## <a name="example"></a><span data-ttu-id="28b41-111">例</span><span class="sxs-lookup"><span data-stu-id="28b41-111">Example</span></span>

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a><span data-ttu-id="28b41-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="28b41-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="28b41-113">&</span><span class="sxs-lookup"><span data-stu-id="28b41-113">'T</span></span>

