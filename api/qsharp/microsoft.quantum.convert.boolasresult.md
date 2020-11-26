---
uid: Microsoft.Quantum.Convert.BoolAsResult
title: ブール Asresult 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolAsResult
qsharp.summary: Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 0190529dd804922a69499fbf1c2c4c916c4b720a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214247"
---
# <a name="boolasresult-function"></a><span data-ttu-id="acff9-102">ブール Asresult 関数</span><span class="sxs-lookup"><span data-stu-id="acff9-102">BoolAsResult function</span></span>

<span data-ttu-id="acff9-103">名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="acff9-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="acff9-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="acff9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="acff9-105">型を `Bool` 型に変換 `Result` `true` します。ここで、はにマップされ、 `One` `false` はにマップされ `Zero` ます。</span><span class="sxs-lookup"><span data-stu-id="acff9-105">Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolAsResult (input : Bool) : Result
```


## <a name="input"></a><span data-ttu-id="acff9-106">入力</span><span class="sxs-lookup"><span data-stu-id="acff9-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="acff9-107">入力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="acff9-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="acff9-108">`Bool` 変換されます。</span><span class="sxs-lookup"><span data-stu-id="acff9-108">`Bool` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="acff9-109">出力:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="acff9-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="acff9-110">`Result` を表す `input`。</span><span class="sxs-lookup"><span data-stu-id="acff9-110">A `Result` representing the `input`.</span></span>