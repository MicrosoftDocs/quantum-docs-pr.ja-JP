---
uid: Microsoft.Quantum.Convert.ResultArrayAsBoolArray
title: Resultarrayasブール配列関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultArrayAsBoolArray
qsharp.summary: Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: 384531137474562ebc8cc24dcd1ac976dc91ad9d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832587"
---
# <a name="resultarrayasboolarray-function"></a><span data-ttu-id="94140-102">Resultarrayasブール配列関数</span><span class="sxs-lookup"><span data-stu-id="94140-102">ResultArrayAsBoolArray function</span></span>

<span data-ttu-id="94140-103">名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="94140-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="94140-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="94140-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="94140-105">型を `Result[]` 型に変換 `Bool[]` `One` します。ここで、はにマップされ、 `true` `Zero` はにマップされ `false` ます。</span><span class="sxs-lookup"><span data-stu-id="94140-105">Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.</span></span>

```qsharp
function ResultArrayAsBoolArray (input : Result[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="94140-106">入力</span><span class="sxs-lookup"><span data-stu-id="94140-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="94140-107">入力:__無効 <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="94140-107">input : __invalid<Result>__[]</span></span>

<span data-ttu-id="94140-108">`Result[]` 変換されます。</span><span class="sxs-lookup"><span data-stu-id="94140-108">`Result[]` to be converted.</span></span>



## <a name="output--bool"></a><span data-ttu-id="94140-109">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="94140-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="94140-110">`Bool[]` を表す `input`。</span><span class="sxs-lookup"><span data-stu-id="94140-110">A `Bool[]` representing the `input`.</span></span>