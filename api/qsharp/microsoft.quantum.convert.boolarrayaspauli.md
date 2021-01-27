---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: ブール関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: c11ca05ad8a939d704547c65a8e8a6537d0df4b7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834248"
---
# <a name="boolarrayaspauli-function"></a><span data-ttu-id="4f15c-102">ブール関数</span><span class="sxs-lookup"><span data-stu-id="4f15c-102">BoolArrayAsPauli function</span></span>

<span data-ttu-id="4f15c-103">名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="4f15c-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="4f15c-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4f15c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4f15c-105">ビット文字列を指定した場合は、single qubit の演算子の配列として表されるマルチ qubit の P# li 演算子を返します。</span><span class="sxs-lookup"><span data-stu-id="4f15c-105">Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="4f15c-106">入力</span><span class="sxs-lookup"><span data-stu-id="4f15c-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="4f15c-107">p# li: [p#](xref:microsoft.quantum.lang-ref.pauli) li</span><span class="sxs-lookup"><span data-stu-id="4f15c-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="4f15c-108">Qubits where に適用する p# li 演算子 `bitsApply == bits[idx]` 。</span><span class="sxs-lookup"><span data-stu-id="4f15c-108">Pauli operator to apply to qubits where `bitsApply == bits[idx]`.</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="4f15c-109">bitApply: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4f15c-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4f15c-110">bit がこの値の場合は、P# li を適用します。</span><span class="sxs-lookup"><span data-stu-id="4f15c-110">apply Pauli if bit is this value.</span></span>


### <a name="bits--bool"></a><span data-ttu-id="4f15c-111">bits: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="4f15c-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="4f15c-112">ブール型の配列。</span><span class="sxs-lookup"><span data-stu-id="4f15c-112">Boolean array.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="4f15c-113">出力: [P# li](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="4f15c-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="4f15c-114">解説</span><span class="sxs-lookup"><span data-stu-id="4f15c-114">Remarks</span></span>

<span data-ttu-id="4f15c-115">ブール型の配列とクォンタムレジスタは同じ長さである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f15c-115">The Boolean array and the quantum register must be of equal length.</span></span>