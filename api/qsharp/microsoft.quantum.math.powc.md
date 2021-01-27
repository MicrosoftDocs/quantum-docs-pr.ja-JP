---
uid: Microsoft.Quantum.Math.PowC
title: PowC 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowC
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: 7dbadbd4c3cc16c3fa0bcd9b5b1acbee990e24ac
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846816"
---
# <a name="powc-function"></a><span data-ttu-id="1b4e1-102">PowC 関数</span><span class="sxs-lookup"><span data-stu-id="1b4e1-102">PowC function</span></span>

<span data-ttu-id="1b4e1-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="1b4e1-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="1b4e1-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1b4e1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1b4e1-105">指定された指数で累乗された数値を返します。</span><span class="sxs-lookup"><span data-stu-id="1b4e1-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowC (a : Microsoft.Quantum.Math.Complex, power : Microsoft.Quantum.Math.Complex) : Microsoft.Quantum.Math.Complex
```


## <a name="input"></a><span data-ttu-id="1b4e1-106">入力</span><span class="sxs-lookup"><span data-stu-id="1b4e1-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="1b4e1-107">a: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="1b4e1-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="1b4e1-108">発生させる $ $a 番号。</span><span class="sxs-lookup"><span data-stu-id="1b4e1-108">The number $a$ that is to be raised.</span></span>


### <a name="power--complex"></a><span data-ttu-id="1b4e1-109">power: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="1b4e1-109">power : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="1b4e1-110">$A $ が発生する必要のある power $b $。</span><span class="sxs-lookup"><span data-stu-id="1b4e1-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--complex"></a><span data-ttu-id="1b4e1-111">出力: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="1b4e1-111">Output : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="1b4e1-112">Power $a ^ b $</span><span class="sxs-lookup"><span data-stu-id="1b4e1-112">The power $a^b$</span></span>