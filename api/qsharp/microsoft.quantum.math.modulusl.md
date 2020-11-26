---
uid: Microsoft.Quantum.Math.ModulusL
title: ModulusL 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 5c9a8ceceac5d2cdac6b82f7f74a85e9443382a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194935"
---
# <a name="modulusl-function"></a><span data-ttu-id="1d922-102">ModulusL 関数</span><span class="sxs-lookup"><span data-stu-id="1d922-102">ModulusL function</span></span>

<span data-ttu-id="1d922-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="1d922-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="1d922-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1d922-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1d922-105">剰余の正規の residue を計算 `value` `modulus` します。</span><span class="sxs-lookup"><span data-stu-id="1d922-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="1d922-106">入力</span><span class="sxs-lookup"><span data-stu-id="1d922-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="1d922-107">値: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1d922-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1d922-108">Residue が計算される値</span><span class="sxs-lookup"><span data-stu-id="1d922-108">The value of which residue is computed</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="1d922-109">剰余: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1d922-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1d922-110">Residues の取得に使用する剰余。正の整数である必要があります</span><span class="sxs-lookup"><span data-stu-id="1d922-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--bigint"></a><span data-ttu-id="1d922-111">出力: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1d922-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1d922-112">0から、 `modulus - 1` `value - r` 剰余で割り切れた整数 $r $</span><span class="sxs-lookup"><span data-stu-id="1d922-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="1d922-113">解説</span><span class="sxs-lookup"><span data-stu-id="1d922-113">Remarks</span></span>

<span data-ttu-id="1d922-114">この関数は、演算子が `%` C# および Q # で動作する方法とは異なり、 `modulus - 1` 値が負の場合でも、結果は常に 0 ~ の正の整数になります。</span><span class="sxs-lookup"><span data-stu-id="1d922-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>