---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactCP
title: NearEqualityFactCP 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactCP
qsharp.summary: Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 477449913732950ad26adc0cdabaaaab803a20c3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853280"
---
# <a name="nearequalityfactcp-function"></a><span data-ttu-id="1a51e-102">NearEqualityFactCP 関数</span><span class="sxs-lookup"><span data-stu-id="1a51e-102">NearEqualityFactCP function</span></span>

<span data-ttu-id="1a51e-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1a51e-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1a51e-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1a51e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1a51e-105">古典的な複素数の値が、最小許容範囲である 1e-10 になるようにアサートします。</span><span class="sxs-lookup"><span data-stu-id="1a51e-105">Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar) : Unit
```


## <a name="input"></a><span data-ttu-id="1a51e-106">入力</span><span class="sxs-lookup"><span data-stu-id="1a51e-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="1a51e-107">実績: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="1a51e-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="1a51e-108">確認する数値。</span><span class="sxs-lookup"><span data-stu-id="1a51e-108">The number to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="1a51e-109">期待される結果: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="1a51e-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="1a51e-110">予期される値。</span><span class="sxs-lookup"><span data-stu-id="1a51e-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1a51e-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1a51e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

