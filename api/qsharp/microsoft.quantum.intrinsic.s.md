---
uid: Microsoft.Quantum.Intrinsic.S
title: S 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: S
qsharp.summary: Applies the S gate to a single qubit.
ms.openlocfilehash: be9078dfdcc4eecf317b0542b1c42a8d60466a5f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817533"
---
# <a name="s-operation"></a><span data-ttu-id="b47e3-102">S 操作</span><span class="sxs-lookup"><span data-stu-id="b47e3-102">S operation</span></span>

<span data-ttu-id="b47e3-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="b47e3-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="b47e3-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="b47e3-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b47e3-105">S ゲートを1つの qubit に適用します。</span><span class="sxs-lookup"><span data-stu-id="b47e3-105">Applies the S gate to a single qubit.</span></span>

```qsharp
operation S (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="b47e3-106">説明</span><span class="sxs-lookup"><span data-stu-id="b47e3-106">Description</span></span>

<span data-ttu-id="b47e3-107">この操作は、ユニタリ matrix \begin{align} S \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ 0 & i \end{bmatrix}. によってシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="b47e3-107">This operation can be simulated by the unitary matrix \begin{align} S \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="b47e3-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="b47e3-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="b47e3-109">入力</span><span class="sxs-lookup"><span data-stu-id="b47e3-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="b47e3-110">qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b47e3-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b47e3-111">ゲートを適用する qubit。</span><span class="sxs-lookup"><span data-stu-id="b47e3-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b47e3-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b47e3-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

