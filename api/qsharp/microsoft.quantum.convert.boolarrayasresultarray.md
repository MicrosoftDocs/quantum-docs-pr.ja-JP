---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: b30da07272ee1a6c19ae13afa618ba5deb7aaa2d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834184"
---
# <a name="boolarrayasresultarray-function"></a><span data-ttu-id="83af2-102">BoolArrayAsResultArray 関数</span><span class="sxs-lookup"><span data-stu-id="83af2-102">BoolArrayAsResultArray function</span></span>

<span data-ttu-id="83af2-103">名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="83af2-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="83af2-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="83af2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="83af2-105">型を `Bool[]` 型に変換 `Result[]` `true` します。ここで、はにマップされ、 `One` `false` はにマップされ `Zero` ます。</span><span class="sxs-lookup"><span data-stu-id="83af2-105">Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="83af2-106">入力</span><span class="sxs-lookup"><span data-stu-id="83af2-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="83af2-107">入力: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="83af2-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="83af2-108">`Bool[]` 変換されます。</span><span class="sxs-lookup"><span data-stu-id="83af2-108">`Bool[]` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="83af2-109">出力:__無効 <Result> な__[]</span><span class="sxs-lookup"><span data-stu-id="83af2-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="83af2-110">`Result[]` を表す `input`。</span><span class="sxs-lookup"><span data-stu-id="83af2-110">A `Result[]` representing the `input`.</span></span>