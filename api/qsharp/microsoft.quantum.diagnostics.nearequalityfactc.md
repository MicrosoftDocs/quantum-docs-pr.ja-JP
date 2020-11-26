---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactC
title: NearEqualityFactC 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactC
qsharp.summary: Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: b08d5edcc1ead2cd125864a157efac76b72ba0d9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201616"
---
# <a name="nearequalityfactc-function"></a><span data-ttu-id="a24f8-102">NearEqualityFactC 関数</span><span class="sxs-lookup"><span data-stu-id="a24f8-102">NearEqualityFactC function</span></span>

<span data-ttu-id="a24f8-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a24f8-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a24f8-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a24f8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a24f8-105">古典的な複素数の値が、最小許容範囲である 1e-10 になるようにアサートします。</span><span class="sxs-lookup"><span data-stu-id="a24f8-105">Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex) : Unit
```


## <a name="input"></a><span data-ttu-id="a24f8-106">入力</span><span class="sxs-lookup"><span data-stu-id="a24f8-106">Input</span></span>

### <a name="actual--complex"></a><span data-ttu-id="a24f8-107">実績: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="a24f8-107">actual : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="a24f8-108">確認する数値。</span><span class="sxs-lookup"><span data-stu-id="a24f8-108">The number to be checked.</span></span>


### <a name="expected--complex"></a><span data-ttu-id="a24f8-109">必要: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="a24f8-109">expected : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="a24f8-110">予期される値。</span><span class="sxs-lookup"><span data-stu-id="a24f8-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a24f8-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a24f8-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

