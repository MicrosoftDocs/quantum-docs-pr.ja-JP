---
uid: Microsoft.Quantum.Math.PowC
title: PowC 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowC
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: 57a0f4c8176a7f87835c7d096136e288c4875eea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194714"
---
# <a name="powc-function"></a><span data-ttu-id="fa14a-102">PowC 関数</span><span class="sxs-lookup"><span data-stu-id="fa14a-102">PowC function</span></span>

<span data-ttu-id="fa14a-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="fa14a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="fa14a-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fa14a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fa14a-105">指定された指数で累乗された数値を返します。</span><span class="sxs-lookup"><span data-stu-id="fa14a-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowC (a : Microsoft.Quantum.Math.Complex, power : Microsoft.Quantum.Math.Complex) : Microsoft.Quantum.Math.Complex
```


## <a name="input"></a><span data-ttu-id="fa14a-106">入力</span><span class="sxs-lookup"><span data-stu-id="fa14a-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="fa14a-107">a: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="fa14a-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="fa14a-108">発生させる $ $a 番号。</span><span class="sxs-lookup"><span data-stu-id="fa14a-108">The number $a$ that is to be raised.</span></span>


### <a name="power--complex"></a><span data-ttu-id="fa14a-109">power: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="fa14a-109">power : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="fa14a-110">$A $ が発生する必要のある power $b $。</span><span class="sxs-lookup"><span data-stu-id="fa14a-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--complex"></a><span data-ttu-id="fa14a-111">出力: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="fa14a-111">Output : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="fa14a-112">Power $a ^ b $</span><span class="sxs-lookup"><span data-stu-id="fa14a-112">The power $a^b$</span></span>