---
uid: Microsoft.Quantum.Intrinsic.T
title: T 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: 352ef2c1b15a46dea85c420fc6f1cfab0382e73a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198403"
---
# <a name="t-operation"></a><span data-ttu-id="2dfda-102">T 操作</span><span class="sxs-lookup"><span data-stu-id="2dfda-102">T operation</span></span>

<span data-ttu-id="2dfda-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="2dfda-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="2dfda-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="2dfda-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2dfda-105">T ゲートを1つの qubit に適用します。</span><span class="sxs-lookup"><span data-stu-id="2dfda-105">Applies the T gate to a single qubit.</span></span>

```qsharp
operation T (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="2dfda-106">説明</span><span class="sxs-lookup"><span data-stu-id="2dfda-106">Description</span></span>

<span data-ttu-id="2dfda-107">この操作は、ユニタリ行列 \begin{align} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ 0 & e ^ {i \ pi/4} \end{bmatrix}. でシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="2dfda-107">This operation can be simulated by the unitary matrix \begin{align} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & e^{i \pi / 4} \end{bmatrix}.</span></span>
<span data-ttu-id="2dfda-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="2dfda-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="2dfda-109">入力</span><span class="sxs-lookup"><span data-stu-id="2dfda-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="2dfda-110">qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2dfda-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2dfda-111">ゲートを適用する qubit。</span><span class="sxs-lookup"><span data-stu-id="2dfda-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2dfda-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2dfda-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

