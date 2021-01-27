---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: AllowAtMostNQubits 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: 3aa80767ac0f752e7be0efa2966c580ca3cb8f19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830910"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="99a4a-102">AllowAtMostNQubits 操作</span><span class="sxs-lookup"><span data-stu-id="99a4a-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="99a4a-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="99a4a-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="99a4a-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="99a4a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="99a4a-105">この操作とその adjoint の呼び出しの間には、指定された数の追加の qubits が使用され、ステートメントを使用して割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="99a4a-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="99a4a-106">入力</span><span class="sxs-lookup"><span data-stu-id="99a4a-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="99a4a-107">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="99a4a-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="99a4a-108">割り当てることができる qubits の最大数。</span><span class="sxs-lookup"><span data-stu-id="99a4a-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="99a4a-109">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="99a4a-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="99a4a-110">失敗したときに表示されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="99a4a-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="99a4a-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="99a4a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="99a4a-112">例</span><span class="sxs-lookup"><span data-stu-id="99a4a-112">Example</span></span>

<span data-ttu-id="99a4a-113">次のスニペットは、この診断をサポートするコンピューターで実行すると失敗します。</span><span class="sxs-lookup"><span data-stu-id="99a4a-113">The following snippet will fail when executed on machines which support this diagnostic:</span></span>

```qsharp
within {
    AllowAtMostNQubits(3, "Too many qubits allocated.");
} apply {
    // Fails since this allocates four qubits.
    using (register = Qubit[4]) {
    }
}
```

## <a name="remarks"></a><span data-ttu-id="99a4a-114">解説</span><span class="sxs-lookup"><span data-stu-id="99a4a-114">Remarks</span></span>

<span data-ttu-id="99a4a-115">この操作は、サポートされていない非 op ターゲットに置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="99a4a-115">This operation may be replaced by a no-op on targets which do not support it.</span></span>