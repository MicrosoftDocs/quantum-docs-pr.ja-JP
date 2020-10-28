---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 05cf8ad939691aac90625c5d056ea79aa062f553
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720278"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="de253-102">DrawRandomBool 操作</span><span class="sxs-lookup"><span data-stu-id="de253-102">DrawRandomBool operation</span></span>

<span data-ttu-id="de253-103">名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="de253-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="de253-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="de253-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="de253-105">成功の確率が指定された場合、は、指定された確率で true である単一のベルヌーイ評価を返します。</span><span class="sxs-lookup"><span data-stu-id="de253-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="de253-106">入力</span><span class="sxs-lookup"><span data-stu-id="de253-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="de253-107">successProbability: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="de253-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="de253-108">が返される確率 `true` 。</span><span class="sxs-lookup"><span data-stu-id="de253-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="de253-109">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="de253-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="de253-110">`true` 確率 `successProbability` と確率を使用 `false` `1.0 - successProbability` します。</span><span class="sxs-lookup"><span data-stu-id="de253-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>