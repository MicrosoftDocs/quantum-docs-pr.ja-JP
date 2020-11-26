---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: ブール関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: 8e7088ec3918165d7b2afb1056a8319c6fb17796
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214281"
---
# <a name="boolarrayaspauli-function"></a><span data-ttu-id="445e6-102">ブール関数</span><span class="sxs-lookup"><span data-stu-id="445e6-102">BoolArrayAsPauli function</span></span>

<span data-ttu-id="445e6-103">名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="445e6-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="445e6-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="445e6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="445e6-105">ビット文字列を指定した場合は、single qubit の演算子の配列として表されるマルチ qubit の P# li 演算子を返します。</span><span class="sxs-lookup"><span data-stu-id="445e6-105">Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="445e6-106">入力</span><span class="sxs-lookup"><span data-stu-id="445e6-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="445e6-107">p# li: [p#](xref:microsoft.quantum.lang-ref.pauli) li</span><span class="sxs-lookup"><span data-stu-id="445e6-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="445e6-108">Qubits where に適用する p# li 演算子 `bitsApply == bits[idx]` 。</span><span class="sxs-lookup"><span data-stu-id="445e6-108">Pauli operator to apply to qubits where `bitsApply == bits[idx]`.</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="445e6-109">bitApply: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="445e6-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="445e6-110">bit がこの値の場合は、P# li を適用します。</span><span class="sxs-lookup"><span data-stu-id="445e6-110">apply Pauli if bit is this value.</span></span>


### <a name="bits--bool"></a><span data-ttu-id="445e6-111">bits: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="445e6-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="445e6-112">ブール型の配列。</span><span class="sxs-lookup"><span data-stu-id="445e6-112">Boolean array.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="445e6-113">出力: [P# li](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="445e6-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="445e6-114">解説</span><span class="sxs-lookup"><span data-stu-id="445e6-114">Remarks</span></span>

<span data-ttu-id="445e6-115">ブール型の配列とクォンタムレジスタは同じ長さである必要があります。</span><span class="sxs-lookup"><span data-stu-id="445e6-115">The Boolean array and the quantum register must be of equal length.</span></span>