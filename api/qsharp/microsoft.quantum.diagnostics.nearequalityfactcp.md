---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactCP
title: NearEqualityFactCP 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactCP
qsharp.summary: Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 1d62d25a3d04c431440cf8fc1eb585cac2c73f2e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712658"
---
# <a name="nearequalityfactcp-function"></a><span data-ttu-id="941b2-102">NearEqualityFactCP 関数</span><span class="sxs-lookup"><span data-stu-id="941b2-102">NearEqualityFactCP function</span></span>

<span data-ttu-id="941b2-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="941b2-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="941b2-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="941b2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="941b2-105">古典的な複素数の値が、最小許容範囲である 1e-10 になるようにアサートします。</span><span class="sxs-lookup"><span data-stu-id="941b2-105">Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar) : Unit
```


## <a name="input"></a><span data-ttu-id="941b2-106">入力</span><span class="sxs-lookup"><span data-stu-id="941b2-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="941b2-107">実績: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="941b2-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="941b2-108">確認する数値。</span><span class="sxs-lookup"><span data-stu-id="941b2-108">The number to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="941b2-109">期待される結果: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="941b2-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="941b2-110">予期される値。</span><span class="sxs-lookup"><span data-stu-id="941b2-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="941b2-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="941b2-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
