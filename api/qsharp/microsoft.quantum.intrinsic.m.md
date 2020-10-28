---
uid: Microsoft.Quantum.Intrinsic.M
title: M 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: 8d4b120385bfc7086a7cb0e3f77034c760d78d92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720938"
---
# <a name="m-operation"></a><span data-ttu-id="6ec61-102">M 操作</span><span class="sxs-lookup"><span data-stu-id="6ec61-102">M operation</span></span>

<span data-ttu-id="6ec61-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="6ec61-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="6ec61-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6ec61-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6ec61-105">P$Z $ ベースで1つの qubit の測定を実行します。</span><span class="sxs-lookup"><span data-stu-id="6ec61-105">Performs a measurement of a single qubit in the Pauli $Z$ basis.</span></span>

<span data-ttu-id="6ec61-106">出力結果は、distribution \begin{align} (\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. によって得られます。</span><span class="sxs-lookup"><span data-stu-id="6ec61-106">The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span></span>
<span data-ttu-id="6ec61-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="6ec61-107">\end{align}</span></span>

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a><span data-ttu-id="6ec61-108">入力</span><span class="sxs-lookup"><span data-stu-id="6ec61-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="6ec61-109">qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6ec61-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6ec61-110">測定する qubit。</span><span class="sxs-lookup"><span data-stu-id="6ec61-110">Qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="6ec61-111">出力: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="6ec61-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="6ec61-112">`Zero` $ + $1 eigenvalue が観測されている場合は、 `One` $-$1 eigenvalue が観測されている場合はです。</span><span class="sxs-lookup"><span data-stu-id="6ec61-112">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="6ec61-113">解説</span><span class="sxs-lookup"><span data-stu-id="6ec61-113">Remarks</span></span>

<span data-ttu-id="6ec61-114">次と同じです。</span><span class="sxs-lookup"><span data-stu-id="6ec61-114">Equivalent to:</span></span>

```qsharp
Measure([PauliZ], [qubit]);
```