---
uid: Microsoft.Quantum.Math.PowCAsCP
title: PowCAsCP 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowCAsCP
qsharp.summary: Internal. Since it is easiest to define the power of two complex numbers in cartesian form as returning in polar form, we define that here, then convert as needed.
ms.openlocfilehash: fb629f360e4b19715e406d4a4f4fae7a31e81736
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847050"
---
# <a name="powcascp-function"></a><span data-ttu-id="706d7-102">PowCAsCP 関数</span><span class="sxs-lookup"><span data-stu-id="706d7-102">PowCAsCP function</span></span>

<span data-ttu-id="706d7-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="706d7-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="706d7-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="706d7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="706d7-105">内部。</span><span class="sxs-lookup"><span data-stu-id="706d7-105">Internal.</span></span> <span data-ttu-id="706d7-106">2つの複素数の累乗は、極座標形式で返されるデカルト形式で定義するのが最も簡単であるため、ここで定義し、必要に応じて変換します。</span><span class="sxs-lookup"><span data-stu-id="706d7-106">Since it is easiest to define the power of two complex numbers in cartesian form as returning in polar form, we define that here, then convert as needed.</span></span>

```qsharp
function PowCAsCP (base_ : Microsoft.Quantum.Math.Complex, power : Microsoft.Quantum.Math.Complex) : Microsoft.Quantum.Math.ComplexPolar
```


## <a name="input"></a><span data-ttu-id="706d7-107">入力</span><span class="sxs-lookup"><span data-stu-id="706d7-107">Input</span></span>

### <a name="base_--complex"></a><span data-ttu-id="706d7-108">base_: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="706d7-108">base_ : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>




### <a name="power--complex"></a><span data-ttu-id="706d7-109">power: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="706d7-109">power : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>





## <a name="output--complexpolar"></a><span data-ttu-id="706d7-110">出力: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="706d7-110">Output : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

