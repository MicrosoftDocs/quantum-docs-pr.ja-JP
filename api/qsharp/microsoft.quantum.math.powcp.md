---
uid: Microsoft.Quantum.Math.PowCP
title: PowCP 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowCP
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: 13f877c94ea30eba37f50ffae65119912e996df3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711118"
---
# <a name="powcp-function"></a><span data-ttu-id="6d5f4-102">PowCP 関数</span><span class="sxs-lookup"><span data-stu-id="6d5f4-102">PowCP function</span></span>

<span data-ttu-id="6d5f4-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="6d5f4-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="6d5f4-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6d5f4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6d5f4-105">指定された指数で累乗された数値を返します。</span><span class="sxs-lookup"><span data-stu-id="6d5f4-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowCP (a : Microsoft.Quantum.Math.ComplexPolar, power : Microsoft.Quantum.Math.ComplexPolar) : Microsoft.Quantum.Math.ComplexPolar
```


## <a name="input"></a><span data-ttu-id="6d5f4-106">入力</span><span class="sxs-lookup"><span data-stu-id="6d5f4-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="6d5f4-107">a: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="6d5f4-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="6d5f4-108">発生させる $ $a 番号。</span><span class="sxs-lookup"><span data-stu-id="6d5f4-108">The number $a$ that is to be raised.</span></span>


### <a name="power--complexpolar"></a><span data-ttu-id="6d5f4-109">電力: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="6d5f4-109">power : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="6d5f4-110">$A $ が発生する必要のある power $b $。</span><span class="sxs-lookup"><span data-stu-id="6d5f4-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--complexpolar"></a><span data-ttu-id="6d5f4-111">出力: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="6d5f4-111">Output : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="6d5f4-112">Power $a ^ b $</span><span class="sxs-lookup"><span data-stu-id="6d5f4-112">The power $a^b$</span></span>