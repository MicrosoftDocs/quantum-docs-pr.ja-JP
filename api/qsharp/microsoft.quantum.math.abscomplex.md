---
uid: Microsoft.Quantum.Math.AbsComplex
title: AbsComplex 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplex
qsharp.summary: Returns the absolute value of a complex number of type `Complex`.
ms.openlocfilehash: 2bb4caa140bef36d893da834eac1c94b8dd8b0e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846069"
---
# <a name="abscomplex-function"></a><span data-ttu-id="fd8ab-102">AbsComplex 関数</span><span class="sxs-lookup"><span data-stu-id="fd8ab-102">AbsComplex function</span></span>

<span data-ttu-id="fd8ab-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="fd8ab-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="fd8ab-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fd8ab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fd8ab-105">型の複素数の絶対値を返し `Complex` ます。</span><span class="sxs-lookup"><span data-stu-id="fd8ab-105">Returns the absolute value of a complex number of type `Complex`.</span></span>

```qsharp
function AbsComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="fd8ab-106">入力</span><span class="sxs-lookup"><span data-stu-id="fd8ab-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="fd8ab-107">入力: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="fd8ab-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="fd8ab-108">複素数 $c = x + i y $。</span><span class="sxs-lookup"><span data-stu-id="fd8ab-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="fd8ab-109">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fd8ab-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fd8ab-110">絶対値 $ | c |= \ sqrt{x ^ 2 + y ^ 2} $。</span><span class="sxs-lookup"><span data-stu-id="fd8ab-110">Absolute value $|c| = \sqrt{x^2 + y^2}$.</span></span>