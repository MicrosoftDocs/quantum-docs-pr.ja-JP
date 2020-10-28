---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 50a2bdb4a73ef9d67d3f5532493c142bb7f753cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713596"
---
# <a name="boolarrayasresultarray-function"></a><span data-ttu-id="f4371-102">BoolArrayAsResultArray 関数</span><span class="sxs-lookup"><span data-stu-id="f4371-102">BoolArrayAsResultArray function</span></span>

<span data-ttu-id="f4371-103">名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="f4371-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="f4371-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f4371-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f4371-105">型を `Bool[]` 型に変換 `Result[]` `true` します。ここで、はにマップされ、 `One` `false` はにマップされ `Zero` ます。</span><span class="sxs-lookup"><span data-stu-id="f4371-105">Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="f4371-106">入力</span><span class="sxs-lookup"><span data-stu-id="f4371-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="f4371-107">入力: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="f4371-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="f4371-108">`Bool[]` 変換されます。</span><span class="sxs-lookup"><span data-stu-id="f4371-108">`Bool[]` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="f4371-109">出力: __無効 <Result> な__ []</span><span class="sxs-lookup"><span data-stu-id="f4371-109">Output : __invalid<Result>__ []</span></span>

<span data-ttu-id="f4371-110">`Result[]` を表す `input`。</span><span class="sxs-lookup"><span data-stu-id="f4371-110">A `Result[]` representing the `input`.</span></span>