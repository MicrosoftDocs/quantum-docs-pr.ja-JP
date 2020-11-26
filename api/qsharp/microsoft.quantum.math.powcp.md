---
uid: Microsoft.Quantum.Math.PowCP
title: PowCP 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowCP
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: 185d40acff6027a775130faaff64582c58384a90
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194646"
---
# <a name="powcp-function"></a><span data-ttu-id="04f27-102">PowCP 関数</span><span class="sxs-lookup"><span data-stu-id="04f27-102">PowCP function</span></span>

<span data-ttu-id="04f27-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="04f27-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="04f27-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="04f27-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="04f27-105">指定された指数で累乗された数値を返します。</span><span class="sxs-lookup"><span data-stu-id="04f27-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowCP (a : Microsoft.Quantum.Math.ComplexPolar, power : Microsoft.Quantum.Math.ComplexPolar) : Microsoft.Quantum.Math.ComplexPolar
```


## <a name="input"></a><span data-ttu-id="04f27-106">入力</span><span class="sxs-lookup"><span data-stu-id="04f27-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="04f27-107">a: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="04f27-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="04f27-108">発生させる $ $a 番号。</span><span class="sxs-lookup"><span data-stu-id="04f27-108">The number $a$ that is to be raised.</span></span>


### <a name="power--complexpolar"></a><span data-ttu-id="04f27-109">電力: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="04f27-109">power : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="04f27-110">$A $ が発生する必要のある power $b $。</span><span class="sxs-lookup"><span data-stu-id="04f27-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--complexpolar"></a><span data-ttu-id="04f27-111">出力: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="04f27-111">Output : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="04f27-112">Power $a ^ b $</span><span class="sxs-lookup"><span data-stu-id="04f27-112">The power $a^b$</span></span>