---
uid: Microsoft.Quantum.Math.ArgComplexPolar
title: ArgComplexPolar 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplexPolar
qsharp.summary: Returns the phase of a complex number of type `ComplexPolar`.
ms.openlocfilehash: 5809b5463e6bf8ee73d095dfe4eafedfbb5e0702
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852914"
---
# <a name="argcomplexpolar-function"></a><span data-ttu-id="2b624-102">ArgComplexPolar 関数</span><span class="sxs-lookup"><span data-stu-id="2b624-102">ArgComplexPolar function</span></span>

<span data-ttu-id="2b624-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="2b624-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="2b624-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2b624-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2b624-105">型の複素数のフェーズを返し `ComplexPolar` ます。</span><span class="sxs-lookup"><span data-stu-id="2b624-105">Returns the phase of a complex number of type `ComplexPolar`.</span></span>

```qsharp
function ArgComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a><span data-ttu-id="2b624-106">入力</span><span class="sxs-lookup"><span data-stu-id="2b624-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="2b624-107">入力: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="2b624-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="2b624-108">複素数 $c = r e ^ {i t} $。</span><span class="sxs-lookup"><span data-stu-id="2b624-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--double"></a><span data-ttu-id="2b624-109">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2b624-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2b624-110">フェーズ $ \ text{arg} [c] = t $。</span><span class="sxs-lookup"><span data-stu-id="2b624-110">Phase $\text{Arg}[c] = t$.</span></span>