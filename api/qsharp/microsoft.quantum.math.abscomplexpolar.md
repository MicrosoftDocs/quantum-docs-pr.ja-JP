---
uid: Microsoft.Quantum.Math.AbsComplexPolar
title: AbsComplexPolar 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplexPolar
qsharp.summary: Returns the absolute value of a complex number of type `ComplexPolar`.
ms.openlocfilehash: c2b60cbdf69723dfc1470535dbc5beb060e68b86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856414"
---
# <a name="abscomplexpolar-function"></a><span data-ttu-id="bd52c-102">AbsComplexPolar 関数</span><span class="sxs-lookup"><span data-stu-id="bd52c-102">AbsComplexPolar function</span></span>

<span data-ttu-id="bd52c-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="bd52c-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="bd52c-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bd52c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bd52c-105">型の複素数の絶対値を返し `ComplexPolar` ます。</span><span class="sxs-lookup"><span data-stu-id="bd52c-105">Returns the absolute value of a complex number of type `ComplexPolar`.</span></span>

```qsharp
function AbsComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a><span data-ttu-id="bd52c-106">入力</span><span class="sxs-lookup"><span data-stu-id="bd52c-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="bd52c-107">入力: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="bd52c-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="bd52c-108">複素数 $c = r e ^ {i t} $。</span><span class="sxs-lookup"><span data-stu-id="bd52c-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--double"></a><span data-ttu-id="bd52c-109">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bd52c-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bd52c-110">絶対値 $ | c |= r $。</span><span class="sxs-lookup"><span data-stu-id="bd52c-110">Absolute value $|c| = r$.</span></span>