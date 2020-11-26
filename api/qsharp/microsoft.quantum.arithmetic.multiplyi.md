---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: 乗算 Yi 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 96922f0147788b37cc9bace5154288a722d4ba95
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222509"
---
# <a name="multiplyi-operation"></a><span data-ttu-id="8884a-102">乗算 Yi 操作</span><span class="sxs-lookup"><span data-stu-id="8884a-102">MultiplyI operation</span></span>

<span data-ttu-id="8884a-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8884a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8884a-104">パッケージ: [Microsoft. Quantum. 数値](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="8884a-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="8884a-105">整数 `xs` を整数で乗算 `ys` し、結果をに格納し `result` ます。最初はゼロである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8884a-105">Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8884a-106">入力</span><span class="sxs-lookup"><span data-stu-id="8884a-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="8884a-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8884a-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8884a-108">$n $-bit 被乗数 (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8884a-108">$n$-bit multiplicand (LittleEndian)</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="8884a-109">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8884a-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8884a-110">$n $-bit 乗数 (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8884a-110">$n$-bit multiplier (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="8884a-111">結果: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8884a-111">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8884a-112">$ 2n $ ビット結果 (LittleEndian) は、初期状態で $ \ket $ である必要があり {0} ます。</span><span class="sxs-lookup"><span data-stu-id="8884a-112">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8884a-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8884a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8884a-114">解説</span><span class="sxs-lookup"><span data-stu-id="8884a-114">Remarks</span></span>

<span data-ttu-id="8884a-115">標準のシフトアンド追加アプローチを使用して乗算を実装します。</span><span class="sxs-lookup"><span data-stu-id="8884a-115">Uses a standard shift-and-add approach to implement the multiplication.</span></span>
<span data-ttu-id="8884a-116">制御されたバージョンを改善するには、コントロール qubit の ancilla qubit に $x _i $ をコピーし、ancilla qubit に対する加算を制御します。</span><span class="sxs-lookup"><span data-stu-id="8884a-116">The controlled version was improved by copying out $x_i$ to an ancilla qubit conditioned on the control qubits, and then controlling the addition on the ancilla qubit.</span></span>