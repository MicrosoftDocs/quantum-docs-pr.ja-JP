---
uid: Microsoft.Quantum.Convert.ResultArrayAsBoolArray
title: Resultarrayasブール配列関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultArrayAsBoolArray
qsharp.summary: Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: f3af3abd4ee58f495d4ea60ec4f21a2690abec1d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224226"
---
# <a name="resultarrayasboolarray-function"></a><span data-ttu-id="039a8-102">Resultarrayasブール配列関数</span><span class="sxs-lookup"><span data-stu-id="039a8-102">ResultArrayAsBoolArray function</span></span>

<span data-ttu-id="039a8-103">名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="039a8-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="039a8-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="039a8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="039a8-105">型を `Result[]` 型に変換 `Bool[]` `One` します。ここで、はにマップされ、 `true` `Zero` はにマップされ `false` ます。</span><span class="sxs-lookup"><span data-stu-id="039a8-105">Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.</span></span>

```qsharp
function ResultArrayAsBoolArray (input : Result[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="039a8-106">入力</span><span class="sxs-lookup"><span data-stu-id="039a8-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="039a8-107">入力:__無効 <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="039a8-107">input : __invalid<Result>__[]</span></span>

<span data-ttu-id="039a8-108">`Result[]` 変換されます。</span><span class="sxs-lookup"><span data-stu-id="039a8-108">`Result[]` to be converted.</span></span>



## <a name="output--bool"></a><span data-ttu-id="039a8-109">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="039a8-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="039a8-110">`Bool[]` を表す `input`。</span><span class="sxs-lookup"><span data-stu-id="039a8-110">A `Bool[]` representing the `input`.</span></span>