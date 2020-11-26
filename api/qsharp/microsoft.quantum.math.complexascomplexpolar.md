---
uid: Microsoft.Quantum.Math.ComplexAsComplexPolar
title: ComplexAsComplexPolar 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexAsComplexPolar
qsharp.summary: Converts a complex number of type `Complex` to a complex number of type `ComplexPolar`.
ms.openlocfilehash: 5155583291e69a78df66f3b77d758fc1708d9146
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195632"
---
# <a name="complexascomplexpolar-function"></a><span data-ttu-id="22154-102">ComplexAsComplexPolar 関数</span><span class="sxs-lookup"><span data-stu-id="22154-102">ComplexAsComplexPolar function</span></span>

<span data-ttu-id="22154-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="22154-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="22154-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="22154-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="22154-105">複素数型の複素数を `Complex` 型の複素数に変換 `ComplexPolar` します。</span><span class="sxs-lookup"><span data-stu-id="22154-105">Converts a complex number of type `Complex` to a complex number of type `ComplexPolar`.</span></span>

```qsharp
function ComplexAsComplexPolar (input : Microsoft.Quantum.Math.Complex) : Microsoft.Quantum.Math.ComplexPolar
```


## <a name="input"></a><span data-ttu-id="22154-106">入力</span><span class="sxs-lookup"><span data-stu-id="22154-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="22154-107">入力: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="22154-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="22154-108">複素数 $c = x + i y $。</span><span class="sxs-lookup"><span data-stu-id="22154-108">Complex number $c = x + i y$.</span></span>



## <a name="output--complexpolar"></a><span data-ttu-id="22154-109">出力: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="22154-109">Output : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="22154-110">複素数 $c = r e ^ {i t} $。</span><span class="sxs-lookup"><span data-stu-id="22154-110">Complex number $c = r e^{i t}$.</span></span>