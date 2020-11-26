---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: AllowAtMostNQubits 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: 5376b6f39d12d664342fbf71e67442c6ef8a0827
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202551"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="2fec2-102">AllowAtMostNQubits 操作</span><span class="sxs-lookup"><span data-stu-id="2fec2-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="2fec2-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2fec2-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2fec2-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2fec2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2fec2-105">この操作とその adjoint の呼び出しの間には、指定された数の追加の qubits が使用され、ステートメントを使用して割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2fec2-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="2fec2-106">入力</span><span class="sxs-lookup"><span data-stu-id="2fec2-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="2fec2-107">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2fec2-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2fec2-108">割り当てることができる qubits の最大数。</span><span class="sxs-lookup"><span data-stu-id="2fec2-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="2fec2-109">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="2fec2-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="2fec2-110">失敗したときに表示されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="2fec2-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2fec2-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2fec2-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2fec2-112">解説</span><span class="sxs-lookup"><span data-stu-id="2fec2-112">Remarks</span></span>

<span data-ttu-id="2fec2-113">この操作は、サポートされていない非 op ターゲットに置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="2fec2-113">This operation may be replaced by a no-op on targets which do not support it.</span></span>