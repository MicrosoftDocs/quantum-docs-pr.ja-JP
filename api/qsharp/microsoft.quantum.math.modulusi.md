---
uid: Microsoft.Quantum.Math.ModulusI
title: ModulusI 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6bbb3877b93e1fc6b38f85a716ba617311c7cfba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227779"
---
# <a name="modulusi-function"></a><span data-ttu-id="1fb60-102">ModulusI 関数</span><span class="sxs-lookup"><span data-stu-id="1fb60-102">ModulusI function</span></span>

<span data-ttu-id="1fb60-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="1fb60-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="1fb60-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1fb60-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1fb60-105">剰余の正規の residue を計算 `value` `modulus` します。</span><span class="sxs-lookup"><span data-stu-id="1fb60-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="1fb60-106">入力</span><span class="sxs-lookup"><span data-stu-id="1fb60-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="1fb60-107">値: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1fb60-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1fb60-108">Residue が計算される値</span><span class="sxs-lookup"><span data-stu-id="1fb60-108">The value of which residue is computed</span></span>


### <a name="modulus--int"></a><span data-ttu-id="1fb60-109">剰余: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1fb60-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1fb60-110">Residues の取得に使用する剰余。正の整数である必要があります</span><span class="sxs-lookup"><span data-stu-id="1fb60-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--int"></a><span data-ttu-id="1fb60-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1fb60-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1fb60-112">0から、 `modulus - 1` `value - r` 剰余で割り切れた整数 $r $</span><span class="sxs-lookup"><span data-stu-id="1fb60-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="1fb60-113">解説</span><span class="sxs-lookup"><span data-stu-id="1fb60-113">Remarks</span></span>

<span data-ttu-id="1fb60-114">この関数は、演算子が `%` C# および Q # で動作する方法とは異なり、 `modulus - 1` 値が負の場合でも、結果は常に 0 ~ の正の整数になります。</span><span class="sxs-lookup"><span data-stu-id="1fb60-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>