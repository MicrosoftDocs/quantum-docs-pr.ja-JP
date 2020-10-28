---
uid: Microsoft.Quantum.Convert.BoolAsResult
title: ブール Asresult 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolAsResult
qsharp.summary: Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: eea6c062afdbb3172e63261e52a82e2576c14011
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713587"
---
# <a name="boolasresult-function"></a><span data-ttu-id="03613-102">ブール Asresult 関数</span><span class="sxs-lookup"><span data-stu-id="03613-102">BoolAsResult function</span></span>

<span data-ttu-id="03613-103">名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="03613-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="03613-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="03613-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="03613-105">型を `Bool` 型に変換 `Result` `true` します。ここで、はにマップされ、 `One` `false` はにマップされ `Zero` ます。</span><span class="sxs-lookup"><span data-stu-id="03613-105">Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolAsResult (input : Bool) : Result
```


## <a name="input"></a><span data-ttu-id="03613-106">入力</span><span class="sxs-lookup"><span data-stu-id="03613-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="03613-107">入力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="03613-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="03613-108">`Bool` 変換されます。</span><span class="sxs-lookup"><span data-stu-id="03613-108">`Bool` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="03613-109">出力: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="03613-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="03613-110">`Result` を表す `input`。</span><span class="sxs-lookup"><span data-stu-id="03613-110">A `Result` representing the `input`.</span></span>