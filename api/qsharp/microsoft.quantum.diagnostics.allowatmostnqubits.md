---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: AllowAtMostNQubits 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: ddbed96df0d95cfd78730c091a6a81ee6e49c349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713055"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="b81a7-102">AllowAtMostNQubits 操作</span><span class="sxs-lookup"><span data-stu-id="b81a7-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="b81a7-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b81a7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b81a7-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b81a7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b81a7-105">この操作とその adjoint の呼び出しの間には、指定された数の追加の qubits が使用され、ステートメントを使用して割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b81a7-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="b81a7-106">入力</span><span class="sxs-lookup"><span data-stu-id="b81a7-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="b81a7-107">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b81a7-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b81a7-108">割り当てることができる qubits の最大数。</span><span class="sxs-lookup"><span data-stu-id="b81a7-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="b81a7-109">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="b81a7-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="b81a7-110">失敗したときに表示されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="b81a7-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b81a7-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b81a7-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b81a7-112">解説</span><span class="sxs-lookup"><span data-stu-id="b81a7-112">Remarks</span></span>

<span data-ttu-id="b81a7-113">この操作は、サポートされていない非 op ターゲットに置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="b81a7-113">This operation may be replaced by a no-op on targets which do not support it.</span></span>