---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: MeasureIdentity 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 71a103fddb3a27703318975bea94bc7a22a9ce81
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714968"
---
# <a name="measureidentity-operation"></a><span data-ttu-id="c4ae1-102">MeasureIdentity 操作</span><span class="sxs-lookup"><span data-stu-id="c4ae1-102">MeasureIdentity operation</span></span>

<span data-ttu-id="c4ae1-103">名前空間: [Microsoft. 量子. 特性](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="c4ae1-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="c4ae1-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c4ae1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c4ae1-105">Qubits のレジスタで id 演算子を測定します。</span><span class="sxs-lookup"><span data-stu-id="c4ae1-105">Measures the identity operator on a register of qubits.</span></span>

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="c4ae1-106">入力</span><span class="sxs-lookup"><span data-stu-id="c4ae1-106">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="c4ae1-107">register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c4ae1-107">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c4ae1-108">測定するレジスタ。</span><span class="sxs-lookup"><span data-stu-id="c4ae1-108">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="c4ae1-109">出力: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="c4ae1-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="c4ae1-110">結果の値 `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="c4ae1-110">The result value `Zero`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c4ae1-111">解説</span><span class="sxs-lookup"><span data-stu-id="c4ae1-111">Remarks</span></span>

<span data-ttu-id="c4ae1-112">$/を完了した $ は eigenvalue $1 $ のみを持ち、負の eigenvalue を持たないため、この操作は常にを返し `Zero` ます。これは eigenvalue $ + 1 = (-1) ^ 0 $ に相当します。の状態を折りたたむことはできません `register` 。</span><span class="sxs-lookup"><span data-stu-id="c4ae1-112">Since $\boldone$ has only the eigenvalue $1$, and does not have a negative eigenvalue, this operation always returns `Zero`, corresponding to the eigenvalue $+1 = (-1)^0$, and does not cause a collapse of the state of `register`.</span></span>

<span data-ttu-id="c4ae1-113">実際には、この操作は役に立ちませんが、プロセス tomography のコンテキストでは、クォンタムプロセスのトレース保持に関する情報を提供するので役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c4ae1-113">On its own, this operation is not useful, but is helpful in the context of process tomography, as it provides information about the trace preservation of a quantum process.</span></span>
<span data-ttu-id="c4ae1-114">特に、損失の多い測定値を持つターゲットコンピューターでは、この操作を実際の測定値 $/bold で置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4ae1-114">In particular, a target machine with lossy measurement should replace this operation by an actual measurement of $\boldone$.</span></span>