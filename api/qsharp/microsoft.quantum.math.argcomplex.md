---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 259296f397207cde4a7d6dfe6cfb1a18e8055216
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211102"
---
# <a name="argcomplex-function"></a><span data-ttu-id="8ef35-102">ArgComplex 関数</span><span class="sxs-lookup"><span data-stu-id="8ef35-102">ArgComplex function</span></span>

<span data-ttu-id="8ef35-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="8ef35-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="8ef35-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8ef35-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8ef35-105">型の複素数のフェーズを返し `Complex` ます。</span><span class="sxs-lookup"><span data-stu-id="8ef35-105">Returns the phase of a complex number of type `Complex`.</span></span>

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="8ef35-106">入力</span><span class="sxs-lookup"><span data-stu-id="8ef35-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="8ef35-107">入力: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="8ef35-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="8ef35-108">複素数 $c = x + i y $。</span><span class="sxs-lookup"><span data-stu-id="8ef35-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="8ef35-109">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8ef35-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8ef35-110">フェーズ $ \ text{arg} [c] = \text{ArcTan} (y, x) \ in (--pi, \ pi] $。</span><span class="sxs-lookup"><span data-stu-id="8ef35-110">Phase $\text{Arg}[c] = \text{ArcTan}(y,x) \in (-\pi,\pi]$.</span></span>