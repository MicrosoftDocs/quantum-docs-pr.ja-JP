---
uid: Microsoft.Quantum.Convert.ResultAsBool
title: ResultAsBool 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultAsBool
qsharp.summary: Converts a `Result` type to a `Bool` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: a170acf635e4e2b2150ffc208fabc9782ff837b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224175"
---
# <a name="resultasbool-function"></a><span data-ttu-id="4dd1b-102">ResultAsBool 関数</span><span class="sxs-lookup"><span data-stu-id="4dd1b-102">ResultAsBool function</span></span>

<span data-ttu-id="4dd1b-103">名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="4dd1b-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="4dd1b-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4dd1b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4dd1b-105">型を `Result` 型に変換 `Bool` `One` します。ここで、はにマップされ、 `true` `Zero` はにマップされ `false` ます。</span><span class="sxs-lookup"><span data-stu-id="4dd1b-105">Converts a `Result` type to a `Bool` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.</span></span>

```qsharp
function ResultAsBool (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="4dd1b-106">入力</span><span class="sxs-lookup"><span data-stu-id="4dd1b-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="4dd1b-107">入力:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="4dd1b-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="4dd1b-108">`Result` 変換されます。</span><span class="sxs-lookup"><span data-stu-id="4dd1b-108">`Result` to be converted.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4dd1b-109">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4dd1b-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4dd1b-110">`Bool` を表す `input`。</span><span class="sxs-lookup"><span data-stu-id="4dd1b-110">A `Bool` representing the `input`.</span></span>