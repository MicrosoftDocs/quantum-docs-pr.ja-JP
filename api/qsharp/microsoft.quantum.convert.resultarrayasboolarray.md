---
uid: Microsoft.Quantum.Convert.ResultArrayAsBoolArray
title: Resultarrayasブール配列関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultArrayAsBoolArray
qsharp.summary: Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: 0356fe9c98306ee3e1857f4af311aef9b3789a7d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713358"
---
# <a name="resultarrayasboolarray-function"></a><span data-ttu-id="bb1b9-102">Resultarrayasブール配列関数</span><span class="sxs-lookup"><span data-stu-id="bb1b9-102">ResultArrayAsBoolArray function</span></span>

<span data-ttu-id="bb1b9-103">名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="bb1b9-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="bb1b9-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bb1b9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bb1b9-105">型を `Result[]` 型に変換 `Bool[]` `One` します。ここで、はにマップされ、 `true` `Zero` はにマップされ `false` ます。</span><span class="sxs-lookup"><span data-stu-id="bb1b9-105">Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.</span></span>

```qsharp
function ResultArrayAsBoolArray (input : Result[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="bb1b9-106">入力</span><span class="sxs-lookup"><span data-stu-id="bb1b9-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="bb1b9-107">入力: __無効 <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="bb1b9-107">input : __invalid<Result>__ []</span></span>

<span data-ttu-id="bb1b9-108">`Result[]` 変換されます。</span><span class="sxs-lookup"><span data-stu-id="bb1b9-108">`Result[]` to be converted.</span></span>



## <a name="output--bool"></a><span data-ttu-id="bb1b9-109">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="bb1b9-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="bb1b9-110">`Bool[]` を表す `input`。</span><span class="sxs-lookup"><span data-stu-id="bb1b9-110">A `Bool[]` representing the `input`.</span></span>