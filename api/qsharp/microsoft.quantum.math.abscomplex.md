---
uid: Microsoft.Quantum.Math.AbsComplex
title: AbsComplex 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplex
qsharp.summary: Returns the absolute value of a complex number of type `Complex`.
ms.openlocfilehash: d47e04616d4bcf49273bec31fc22990a8244962b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723890"
---
# <a name="abscomplex-function"></a><span data-ttu-id="c6e87-102">AbsComplex 関数</span><span class="sxs-lookup"><span data-stu-id="c6e87-102">AbsComplex function</span></span>

<span data-ttu-id="c6e87-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="c6e87-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="c6e87-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c6e87-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c6e87-105">型の複素数の絶対値を返し `Complex` ます。</span><span class="sxs-lookup"><span data-stu-id="c6e87-105">Returns the absolute value of a complex number of type `Complex`.</span></span>

```qsharp
function AbsComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="c6e87-106">入力</span><span class="sxs-lookup"><span data-stu-id="c6e87-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="c6e87-107">入力: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="c6e87-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="c6e87-108">複素数 $c = x + i y $。</span><span class="sxs-lookup"><span data-stu-id="c6e87-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="c6e87-109">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c6e87-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c6e87-110">絶対値 $ | c |= \ sqrt{x ^ 2 + y ^ 2} $。</span><span class="sxs-lookup"><span data-stu-id="c6e87-110">Absolute value $|c| = \sqrt{x^2 + y^2}$.</span></span>