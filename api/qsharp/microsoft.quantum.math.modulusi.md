---
uid: Microsoft.Quantum.Math.ModulusI
title: ModulusI 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 3f698a00b2c8d94b7cb3cca4f1721c659918f4a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723092"
---
# <a name="modulusi-function"></a><span data-ttu-id="e21cb-102">ModulusI 関数</span><span class="sxs-lookup"><span data-stu-id="e21cb-102">ModulusI function</span></span>

<span data-ttu-id="e21cb-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e21cb-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e21cb-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e21cb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e21cb-105">剰余の正規の residue を計算 `value` `modulus` します。</span><span class="sxs-lookup"><span data-stu-id="e21cb-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="e21cb-106">入力</span><span class="sxs-lookup"><span data-stu-id="e21cb-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="e21cb-107">値: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e21cb-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e21cb-108">Residue が計算される値</span><span class="sxs-lookup"><span data-stu-id="e21cb-108">The value of which residue is computed</span></span>


### <a name="modulus--int"></a><span data-ttu-id="e21cb-109">剰余: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e21cb-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e21cb-110">Residues の取得に使用する剰余。正の整数である必要があります</span><span class="sxs-lookup"><span data-stu-id="e21cb-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--int"></a><span data-ttu-id="e21cb-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e21cb-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e21cb-112">0から、 `modulus - 1` `value - r` 剰余で割り切れた整数 $r $</span><span class="sxs-lookup"><span data-stu-id="e21cb-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="e21cb-113">解説</span><span class="sxs-lookup"><span data-stu-id="e21cb-113">Remarks</span></span>

<span data-ttu-id="e21cb-114">この関数は、演算子が `%` C# および Q # で動作する方法とは異なり、 `modulus - 1` 値が負の場合でも、結果は常に 0 ~ の正の整数になります。</span><span class="sxs-lookup"><span data-stu-id="e21cb-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>