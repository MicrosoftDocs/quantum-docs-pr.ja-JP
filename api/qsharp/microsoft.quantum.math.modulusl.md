---
uid: Microsoft.Quantum.Math.ModulusL
title: ModulusL 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6be2edb052cf55f8e8465c76b5dcadeb61ff11ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842743"
---
# <a name="modulusl-function"></a><span data-ttu-id="9fd2d-102">ModulusL 関数</span><span class="sxs-lookup"><span data-stu-id="9fd2d-102">ModulusL function</span></span>

<span data-ttu-id="9fd2d-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="9fd2d-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="9fd2d-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9fd2d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9fd2d-105">剰余の正規の residue を計算 `value` `modulus` します。</span><span class="sxs-lookup"><span data-stu-id="9fd2d-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="9fd2d-106">入力</span><span class="sxs-lookup"><span data-stu-id="9fd2d-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="9fd2d-107">値: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9fd2d-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9fd2d-108">Residue が計算される値</span><span class="sxs-lookup"><span data-stu-id="9fd2d-108">The value of which residue is computed</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="9fd2d-109">剰余: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9fd2d-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9fd2d-110">Residues の取得に使用する剰余。正の整数である必要があります</span><span class="sxs-lookup"><span data-stu-id="9fd2d-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--bigint"></a><span data-ttu-id="9fd2d-111">出力: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9fd2d-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9fd2d-112">0から、 `modulus - 1` `value - r` 剰余で割り切れた整数 $r $</span><span class="sxs-lookup"><span data-stu-id="9fd2d-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="9fd2d-113">解説</span><span class="sxs-lookup"><span data-stu-id="9fd2d-113">Remarks</span></span>

<span data-ttu-id="9fd2d-114">この関数の動作は、 `%` C# および Q # での演算子の動作によって異なります。結果は、 `modulus - 1` 値が負の場合でも、常に 0 ~ の範囲の負でない整数になります。</span><span class="sxs-lookup"><span data-stu-id="9fd2d-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a non-negative integer between 0 and `modulus - 1`, even if value is negative.</span></span>