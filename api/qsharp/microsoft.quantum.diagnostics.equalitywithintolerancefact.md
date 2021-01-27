---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceFact 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: ab7e43d951bf741926b15f27f94d176e88609d4a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828750"
---
# <a name="equalitywithintolerancefact-function"></a><span data-ttu-id="6845f-102">EqualityWithinToleranceFact 関数</span><span class="sxs-lookup"><span data-stu-id="6845f-102">EqualityWithinToleranceFact function</span></span>

<span data-ttu-id="6845f-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="6845f-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="6845f-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6845f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6845f-105">古典的な浮動小数点値が、指定された絶対許容範囲に最大の予測値を持つことを示す要求を表します。</span><span class="sxs-lookup"><span data-stu-id="6845f-105">Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.</span></span>

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="6845f-106">入力</span><span class="sxs-lookup"><span data-stu-id="6845f-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="6845f-107">実際: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6845f-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6845f-108">確認する数値。</span><span class="sxs-lookup"><span data-stu-id="6845f-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="6845f-109">が必要です。 [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6845f-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6845f-110">予期される値。</span><span class="sxs-lookup"><span data-stu-id="6845f-110">The expected value.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="6845f-111">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6845f-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6845f-112">実際と予想される差に対する絶対許容値。</span><span class="sxs-lookup"><span data-stu-id="6845f-112">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6845f-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6845f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

