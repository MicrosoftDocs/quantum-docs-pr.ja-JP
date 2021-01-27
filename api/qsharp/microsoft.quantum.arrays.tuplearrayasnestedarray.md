---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: TupleArrayAsNestedArray 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: 51a35555080d1d2475fc1aa9e48e84c7c6f92c51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845389"
---
# <a name="tuplearrayasnestedarray-function"></a><span data-ttu-id="47c2e-102">TupleArrayAsNestedArray 関数</span><span class="sxs-lookup"><span data-stu-id="47c2e-102">TupleArrayAsNestedArray function</span></span>

<span data-ttu-id="47c2e-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="47c2e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="47c2e-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="47c2e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="47c2e-105">2つのタプルのリストを入れ子になった配列に変換します。</span><span class="sxs-lookup"><span data-stu-id="47c2e-105">Turns a list of 2-tuples into a nested array.</span></span>

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="47c2e-106">入力</span><span class="sxs-lookup"><span data-stu-id="47c2e-106">Input</span></span>

### <a name="tuplelist--tt"></a><span data-ttu-id="47c2e-107">tupleList: (t, t) []</span><span class="sxs-lookup"><span data-stu-id="47c2e-107">tupleList : ('T,'T)[]</span></span>

<span data-ttu-id="47c2e-108">入れ子になった配列に変換される2組のリスト。</span><span class="sxs-lookup"><span data-stu-id="47c2e-108">List of 2-tuples to be turned into a nested array.</span></span>



## <a name="output--t"></a><span data-ttu-id="47c2e-109">出力: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="47c2e-109">Output : 'T[][]</span></span>

<span data-ttu-id="47c2e-110">TupleList に一致する長さの入れ子になった配列。</span><span class="sxs-lookup"><span data-stu-id="47c2e-110">A nested array with length matching the tupleList.</span></span>

## <a name="example"></a><span data-ttu-id="47c2e-111">例</span><span class="sxs-lookup"><span data-stu-id="47c2e-111">Example</span></span>

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a><span data-ttu-id="47c2e-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="47c2e-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="47c2e-113">&</span><span class="sxs-lookup"><span data-stu-id="47c2e-113">'T</span></span>

