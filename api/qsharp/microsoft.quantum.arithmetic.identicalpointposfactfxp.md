---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: IdenticalPointPosFactFxP 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 0b285ce980ca1abbc3eb20838389a6f49835e742
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721118"
---
# <a name="identicalpointposfactfxp-function"></a><span data-ttu-id="5de9e-102">IdenticalPointPosFactFxP 関数</span><span class="sxs-lookup"><span data-stu-id="5de9e-102">IdenticalPointPosFactFxP function</span></span>

<span data-ttu-id="5de9e-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5de9e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5de9e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5de9e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5de9e-105">指定された配列内のすべての固定小数点数が、最下位ビットからカウントされるときに同一のポイント位置を持つことをアサートします。</span><span class="sxs-lookup"><span data-stu-id="5de9e-105">Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit.</span></span> <span data-ttu-id="5de9e-106">つまり、ビット数からポイント位置を引いた値は、配列内のすべての固定小数点数に対して定数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5de9e-106">I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.</span></span>

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="5de9e-107">入力</span><span class="sxs-lookup"><span data-stu-id="5de9e-107">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="5de9e-108">fixedPoints: [Fixedpoints](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="5de9e-108">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="5de9e-109">互換性をチェックするクォンタム固定小数点数の配列 (アサーションを使用)。</span><span class="sxs-lookup"><span data-stu-id="5de9e-109">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="5de9e-110">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5de9e-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

