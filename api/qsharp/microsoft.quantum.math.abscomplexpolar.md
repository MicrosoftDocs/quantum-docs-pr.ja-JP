---
uid: Microsoft.Quantum.Math.AbsComplexPolar
title: AbsComplexPolar 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplexPolar
qsharp.summary: Returns the absolute value of a complex number of type `ComplexPolar`.
ms.openlocfilehash: 01845556cbabde768f9c7c47c733453048df9416
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195989"
---
# <a name="abscomplexpolar-function"></a><span data-ttu-id="c012a-102">AbsComplexPolar 関数</span><span class="sxs-lookup"><span data-stu-id="c012a-102">AbsComplexPolar function</span></span>

<span data-ttu-id="c012a-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="c012a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="c012a-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c012a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c012a-105">型の複素数の絶対値を返し `ComplexPolar` ます。</span><span class="sxs-lookup"><span data-stu-id="c012a-105">Returns the absolute value of a complex number of type `ComplexPolar`.</span></span>

```qsharp
function AbsComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a><span data-ttu-id="c012a-106">入力</span><span class="sxs-lookup"><span data-stu-id="c012a-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="c012a-107">入力: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="c012a-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="c012a-108">複素数 $c = r e ^ {i t} $。</span><span class="sxs-lookup"><span data-stu-id="c012a-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--double"></a><span data-ttu-id="c012a-109">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c012a-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c012a-110">絶対値 $ | c |= r $。</span><span class="sxs-lookup"><span data-stu-id="c012a-110">Absolute value $|c| = r$.</span></span>