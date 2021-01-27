---
uid: Microsoft.Quantum.Intrinsic.T
title: T 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: bee252d9905aed26f6bf663f895e464e38073f44
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817508"
---
# <a name="t-operation"></a><span data-ttu-id="8bb94-102">T 操作</span><span class="sxs-lookup"><span data-stu-id="8bb94-102">T operation</span></span>

<span data-ttu-id="8bb94-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="8bb94-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="8bb94-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="8bb94-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="8bb94-105">T ゲートを1つの qubit に適用します。</span><span class="sxs-lookup"><span data-stu-id="8bb94-105">Applies the T gate to a single qubit.</span></span>

```qsharp
operation T (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="8bb94-106">説明</span><span class="sxs-lookup"><span data-stu-id="8bb94-106">Description</span></span>

<span data-ttu-id="8bb94-107">この操作は、ユニタリ行列 \begin{align} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ 0 & e ^ {i \ pi/4} \end{bmatrix}. でシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="8bb94-107">This operation can be simulated by the unitary matrix \begin{align} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & e^{i \pi / 4} \end{bmatrix}.</span></span>
<span data-ttu-id="8bb94-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="8bb94-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="8bb94-109">入力</span><span class="sxs-lookup"><span data-stu-id="8bb94-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="8bb94-110">qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8bb94-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8bb94-111">ゲートを適用する qubit。</span><span class="sxs-lookup"><span data-stu-id="8bb94-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8bb94-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8bb94-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

