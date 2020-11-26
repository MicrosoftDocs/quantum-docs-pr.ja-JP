---
uid: Microsoft.Quantum.Math.PowCAsCP
title: PowCAsCP 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowCAsCP
qsharp.summary: Internal. Since it is easiest to define the power of two complex numbers in cartesian form as returning in polar form, we define that here, then convert as needed.
ms.openlocfilehash: b24b4787743baa447ed8ab6cc61a13e4a18316e9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227507"
---
# <a name="powcascp-function"></a><span data-ttu-id="2f471-102">PowCAsCP 関数</span><span class="sxs-lookup"><span data-stu-id="2f471-102">PowCAsCP function</span></span>

<span data-ttu-id="2f471-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="2f471-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="2f471-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2f471-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2f471-105">内部。</span><span class="sxs-lookup"><span data-stu-id="2f471-105">Internal.</span></span> <span data-ttu-id="2f471-106">2つの複素数の累乗は、極座標形式で返されるデカルト形式で定義するのが最も簡単であるため、ここで定義し、必要に応じて変換します。</span><span class="sxs-lookup"><span data-stu-id="2f471-106">Since it is easiest to define the power of two complex numbers in cartesian form as returning in polar form, we define that here, then convert as needed.</span></span>

```qsharp
function PowCAsCP (base_ : Microsoft.Quantum.Math.Complex, power : Microsoft.Quantum.Math.Complex) : Microsoft.Quantum.Math.ComplexPolar
```


## <a name="input"></a><span data-ttu-id="2f471-107">入力</span><span class="sxs-lookup"><span data-stu-id="2f471-107">Input</span></span>

### <a name="base_--complex"></a><span data-ttu-id="2f471-108">base_: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="2f471-108">base_ : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>




### <a name="power--complex"></a><span data-ttu-id="2f471-109">power: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="2f471-109">power : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>





## <a name="output--complexpolar"></a><span data-ttu-id="2f471-110">出力: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="2f471-110">Output : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

