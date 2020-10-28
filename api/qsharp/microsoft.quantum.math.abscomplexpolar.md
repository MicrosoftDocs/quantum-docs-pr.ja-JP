---
uid: Microsoft.Quantum.Math.AbsComplexPolar
title: AbsComplexPolar 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplexPolar
qsharp.summary: Returns the absolute value of a complex number of type `ComplexPolar`.
ms.openlocfilehash: bc74d691e69a4f1be096582e42ec3a88ddcdd3c0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723881"
---
# <a name="abscomplexpolar-function"></a><span data-ttu-id="7356f-102">AbsComplexPolar 関数</span><span class="sxs-lookup"><span data-stu-id="7356f-102">AbsComplexPolar function</span></span>

<span data-ttu-id="7356f-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="7356f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="7356f-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7356f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7356f-105">型の複素数の絶対値を返し `ComplexPolar` ます。</span><span class="sxs-lookup"><span data-stu-id="7356f-105">Returns the absolute value of a complex number of type `ComplexPolar`.</span></span>

```qsharp
function AbsComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a><span data-ttu-id="7356f-106">入力</span><span class="sxs-lookup"><span data-stu-id="7356f-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="7356f-107">入力: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="7356f-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="7356f-108">複素数 $c = r e ^ {i t} $。</span><span class="sxs-lookup"><span data-stu-id="7356f-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--double"></a><span data-ttu-id="7356f-109">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7356f-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7356f-110">絶対値 $ | c |= r $。</span><span class="sxs-lookup"><span data-stu-id="7356f-110">Absolute value $|c| = r$.</span></span>