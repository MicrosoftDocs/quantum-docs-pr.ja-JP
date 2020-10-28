---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalI
title: コンピューターの Procali 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalI
qsharp.summary: Computes the reciprocal 1/x for an unsigned integer x using integer division. The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.
ms.openlocfilehash: b99e816ed69af6e6d1758442d6f95c5ab0e5c07a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721226"
---
# <a name="computereciprocali-operation"></a><span data-ttu-id="45d17-102">コンピューターの Procali 操作</span><span class="sxs-lookup"><span data-stu-id="45d17-102">ComputeReciprocalI operation</span></span>

<span data-ttu-id="45d17-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="45d17-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="45d17-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="45d17-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="45d17-105">整数除算を使用して、符号なし整数 x の逆数 1/x を計算します。</span><span class="sxs-lookup"><span data-stu-id="45d17-105">Computes the reciprocal 1/x for an unsigned integer x using integer division.</span></span> <span data-ttu-id="45d17-106">整数として解釈される結果はになり `floor(2^(2*n-1) / x)` ます。</span><span class="sxs-lookup"><span data-stu-id="45d17-106">The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.</span></span>

```qsharp
operation ComputeReciprocalI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="45d17-107">入力</span><span class="sxs-lookup"><span data-stu-id="45d17-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="45d17-108">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="45d17-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="45d17-109">n ビット符号なし整数</span><span class="sxs-lookup"><span data-stu-id="45d17-109">n-bit unsigned integer</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="45d17-110">結果: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="45d17-110">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="45d17-111">2n ビット出力は、最初に $ \ket $ にある必要があり {0} ます。</span><span class="sxs-lookup"><span data-stu-id="45d17-111">2n-bit output, must be in $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="45d17-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="45d17-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="45d17-113">解説</span><span class="sxs-lookup"><span data-stu-id="45d17-113">Remarks</span></span>

<span data-ttu-id="45d17-114">入力 x = 0 の場合、出力はすべて1になります。</span><span class="sxs-lookup"><span data-stu-id="45d17-114">For the input x=0, the output will be all-ones.</span></span>