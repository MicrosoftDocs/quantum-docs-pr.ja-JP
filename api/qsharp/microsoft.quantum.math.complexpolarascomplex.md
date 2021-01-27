---
uid: Microsoft.Quantum.Math.ComplexPolarAsComplex
title: ComplexPolarAsComplex 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolarAsComplex
qsharp.summary: Converts a complex number of type `ComplexPolar` to a complex number of type `Complex`.
ms.openlocfilehash: 6834b47705d080d4597ae1a6037462521fac45f7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853869"
---
# <a name="complexpolarascomplex-function"></a><span data-ttu-id="46acf-102">ComplexPolarAsComplex 関数</span><span class="sxs-lookup"><span data-stu-id="46acf-102">ComplexPolarAsComplex function</span></span>

<span data-ttu-id="46acf-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="46acf-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="46acf-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="46acf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="46acf-105">複素数型の複素数を `ComplexPolar` 型の複素数に変換 `Complex` します。</span><span class="sxs-lookup"><span data-stu-id="46acf-105">Converts a complex number of type `ComplexPolar` to a complex number of type `Complex`.</span></span>

```qsharp
function ComplexPolarAsComplex (input : Microsoft.Quantum.Math.ComplexPolar) : Microsoft.Quantum.Math.Complex
```


## <a name="input"></a><span data-ttu-id="46acf-106">入力</span><span class="sxs-lookup"><span data-stu-id="46acf-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="46acf-107">入力: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="46acf-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="46acf-108">複素数 $c = r e ^ {i t} $。</span><span class="sxs-lookup"><span data-stu-id="46acf-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--complex"></a><span data-ttu-id="46acf-109">出力: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="46acf-109">Output : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="46acf-110">複素数 $c = x + i y $。</span><span class="sxs-lookup"><span data-stu-id="46acf-110">Complex number $c = x + i y$.</span></span>