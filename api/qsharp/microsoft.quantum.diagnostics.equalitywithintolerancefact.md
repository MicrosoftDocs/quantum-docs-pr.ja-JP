---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceFact 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: de15a32d5b38c5ab8c681d2c052669a48cf676cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712747"
---
# <a name="equalitywithintolerancefact-function"></a><span data-ttu-id="5fd20-102">EqualityWithinToleranceFact 関数</span><span class="sxs-lookup"><span data-stu-id="5fd20-102">EqualityWithinToleranceFact function</span></span>

<span data-ttu-id="5fd20-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="5fd20-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="5fd20-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5fd20-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5fd20-105">古典的な浮動小数点値が、指定された絶対許容範囲に最大の予測値を持つことを示す要求を表します。</span><span class="sxs-lookup"><span data-stu-id="5fd20-105">Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.</span></span>

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="5fd20-106">入力</span><span class="sxs-lookup"><span data-stu-id="5fd20-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="5fd20-107">実際: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5fd20-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5fd20-108">確認する数値。</span><span class="sxs-lookup"><span data-stu-id="5fd20-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="5fd20-109">が必要です。 [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5fd20-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5fd20-110">予期される値。</span><span class="sxs-lookup"><span data-stu-id="5fd20-110">The expected value.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="5fd20-111">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5fd20-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5fd20-112">実際と予想される差に対する絶対許容値。</span><span class="sxs-lookup"><span data-stu-id="5fd20-112">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5fd20-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5fd20-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

