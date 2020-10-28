---
uid: Microsoft.Quantum.Intrinsic.T
title: T 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: 868031386c95f65ae956b5e444c6d87d7ea0a697
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720854"
---
# <a name="t-operation"></a><span data-ttu-id="d8c5a-102">T 操作</span><span class="sxs-lookup"><span data-stu-id="d8c5a-102">T operation</span></span>

<span data-ttu-id="d8c5a-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="d8c5a-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="d8c5a-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d8c5a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d8c5a-105">T ゲートを1つの qubit に適用します。</span><span class="sxs-lookup"><span data-stu-id="d8c5a-105">Applies the T gate to a single qubit.</span></span>

```qsharp
operation T (qubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="d8c5a-106">説明</span><span class="sxs-lookup"><span data-stu-id="d8c5a-106">Description</span></span>

<span data-ttu-id="d8c5a-107">この操作は、ユニタリ行列 \begin{align} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ 0 & e ^ {i \ pi/4} \end{bmatrix}. でシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="d8c5a-107">This operation can be simulated by the unitary matrix \begin{align} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & e^{i \pi / 4} \end{bmatrix}.</span></span>
<span data-ttu-id="d8c5a-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="d8c5a-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="d8c5a-109">入力</span><span class="sxs-lookup"><span data-stu-id="d8c5a-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="d8c5a-110">qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d8c5a-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d8c5a-111">ゲートを適用する qubit。</span><span class="sxs-lookup"><span data-stu-id="d8c5a-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d8c5a-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d8c5a-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

