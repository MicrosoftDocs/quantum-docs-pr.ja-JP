---
uid: Microsoft.Quantum.Math.ContinuedFractionConvergentL
title: ContinuedFractionConvergentL 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ContinuedFractionConvergentL
qsharp.summary: Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`
ms.openlocfilehash: a02b38fedb5b0025f04e7bba86f2f998493206b3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723825"
---
# <a name="continuedfractionconvergentl-function"></a><span data-ttu-id="3e1b2-102">ContinuedFractionConvergentL 関数</span><span class="sxs-lookup"><span data-stu-id="3e1b2-102">ContinuedFractionConvergentL function</span></span>

<span data-ttu-id="3e1b2-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="3e1b2-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="3e1b2-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3e1b2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3e1b2-105">に最も近い `fraction` 、分母が以下である継続分数の値を検索します。 `denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="3e1b2-105">Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>

```qsharp
function ContinuedFractionConvergentL (fraction : Microsoft.Quantum.Math.BigFraction, denominatorBound : BigInt) : Microsoft.Quantum.Math.BigFraction
```


## <a name="input"></a><span data-ttu-id="3e1b2-106">入力</span><span class="sxs-lookup"><span data-stu-id="3e1b2-106">Input</span></span>

### <a name="fraction--bigfraction"></a><span data-ttu-id="3e1b2-107">分数: [Bigfraction](xref:Microsoft.Quantum.Math.BigFraction)</span><span class="sxs-lookup"><span data-stu-id="3e1b2-107">fraction : [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span></span>




### <a name="denominatorbound--bigint"></a><span data-ttu-id="3e1b2-108">denominatorBound: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="3e1b2-108">denominatorBound : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigfraction"></a><span data-ttu-id="3e1b2-109">出力: [Bigfraction](xref:Microsoft.Quantum.Math.BigFraction)</span><span class="sxs-lookup"><span data-stu-id="3e1b2-109">Output : [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span></span>

<span data-ttu-id="3e1b2-110">分母が以下の場合に最も近い継続分数 `fraction``denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="3e1b2-110">Continued fraction closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>