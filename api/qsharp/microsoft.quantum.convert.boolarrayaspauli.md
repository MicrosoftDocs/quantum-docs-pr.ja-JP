---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: ブール関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: c5ef71322dae248fc2c6b1db3adf891de7d72488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713601"
---
# <a name="boolarrayaspauli-function"></a><span data-ttu-id="02adb-102">ブール関数</span><span class="sxs-lookup"><span data-stu-id="02adb-102">BoolArrayAsPauli function</span></span>

<span data-ttu-id="02adb-103">名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="02adb-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="02adb-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="02adb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="02adb-105">ビット文字列を指定した場合は、single qubit の演算子の配列として表されるマルチ qubit の P# li 演算子を返します。</span><span class="sxs-lookup"><span data-stu-id="02adb-105">Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="02adb-106">入力</span><span class="sxs-lookup"><span data-stu-id="02adb-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="02adb-107">p# li: [p#](xref:microsoft.quantum.lang-ref.pauli) li</span><span class="sxs-lookup"><span data-stu-id="02adb-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="02adb-108">Qubits where に適用する p# li 演算子 `bitsApply == bits[idx]` 。</span><span class="sxs-lookup"><span data-stu-id="02adb-108">Pauli operator to apply to qubits where `bitsApply == bits[idx]`.</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="02adb-109">bitApply: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="02adb-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="02adb-110">bit がこの値の場合は、P# li を適用します。</span><span class="sxs-lookup"><span data-stu-id="02adb-110">apply Pauli if bit is this value.</span></span>


### <a name="bits--bool"></a><span data-ttu-id="02adb-111">bits: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="02adb-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="02adb-112">ブール型の配列。</span><span class="sxs-lookup"><span data-stu-id="02adb-112">Boolean array.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="02adb-113">出力: [P# li](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="02adb-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="02adb-114">解説</span><span class="sxs-lookup"><span data-stu-id="02adb-114">Remarks</span></span>

<span data-ttu-id="02adb-115">ブール型の配列とクォンタムレジスタは同じ長さである必要があります。</span><span class="sxs-lookup"><span data-stu-id="02adb-115">The Boolean array and the quantum register must be of equal length.</span></span>