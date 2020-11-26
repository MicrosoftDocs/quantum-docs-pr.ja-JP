---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: dbe0836af5aa19f1bdce3cfe93be6833358c22be
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192963"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="6a4c8-102">DrawRandomBool 操作</span><span class="sxs-lookup"><span data-stu-id="6a4c8-102">DrawRandomBool operation</span></span>

<span data-ttu-id="6a4c8-103">名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="6a4c8-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="6a4c8-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="6a4c8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6a4c8-105">成功の確率が指定された場合、は、指定された確率で true である単一のベルヌーイ評価を返します。</span><span class="sxs-lookup"><span data-stu-id="6a4c8-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="6a4c8-106">入力</span><span class="sxs-lookup"><span data-stu-id="6a4c8-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="6a4c8-107">successProbability: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6a4c8-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6a4c8-108">が返される確率 `true` 。</span><span class="sxs-lookup"><span data-stu-id="6a4c8-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6a4c8-109">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6a4c8-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6a4c8-110">`true` 確率 `successProbability` と確率を使用 `false` `1.0 - successProbability` します。</span><span class="sxs-lookup"><span data-stu-id="6a4c8-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>