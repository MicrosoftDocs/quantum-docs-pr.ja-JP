---
uid: Microsoft.Quantum.Math.ContinuedFractionConvergentL
title: ContinuedFractionConvergentL 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ContinuedFractionConvergentL
qsharp.summary: Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`
ms.openlocfilehash: c10fcbbe63d3d4c7d6c56196768c1062be1ca350
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210932"
---
# <a name="continuedfractionconvergentl-function"></a><span data-ttu-id="0ef0f-102">ContinuedFractionConvergentL 関数</span><span class="sxs-lookup"><span data-stu-id="0ef0f-102">ContinuedFractionConvergentL function</span></span>

<span data-ttu-id="0ef0f-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="0ef0f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="0ef0f-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0ef0f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0ef0f-105">に最も近い `fraction` 、分母が以下である継続分数の値を検索します。 `denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="0ef0f-105">Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>

```qsharp
function ContinuedFractionConvergentL (fraction : Microsoft.Quantum.Math.BigFraction, denominatorBound : BigInt) : Microsoft.Quantum.Math.BigFraction
```


## <a name="input"></a><span data-ttu-id="0ef0f-106">入力</span><span class="sxs-lookup"><span data-stu-id="0ef0f-106">Input</span></span>

### <a name="fraction--bigfraction"></a><span data-ttu-id="0ef0f-107">分数: [Bigfraction](xref:Microsoft.Quantum.Math.BigFraction)</span><span class="sxs-lookup"><span data-stu-id="0ef0f-107">fraction : [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span></span>




### <a name="denominatorbound--bigint"></a><span data-ttu-id="0ef0f-108">denominatorBound: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="0ef0f-108">denominatorBound : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigfraction"></a><span data-ttu-id="0ef0f-109">出力: [Bigfraction](xref:Microsoft.Quantum.Math.BigFraction)</span><span class="sxs-lookup"><span data-stu-id="0ef0f-109">Output : [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span></span>

<span data-ttu-id="0ef0f-110">分母が以下の場合に最も近い継続分数 `fraction``denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="0ef0f-110">Continued fraction closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>