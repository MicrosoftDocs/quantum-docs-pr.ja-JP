---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: _prepareEntangledState 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 97a55b4bb85095c7d8e8432dfcd1c6d6f7e93cdc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223937"
---
# <a name="_prepareentangledstate-operation"></a><span data-ttu-id="453d8-102">_prepareEntangledState 操作</span><span class="sxs-lookup"><span data-stu-id="453d8-102">_prepareEntangledState operation</span></span>

<span data-ttu-id="453d8-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="453d8-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="453d8-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="453d8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="453d8-105">2つのレジスタが指定されている場合、によって、各レジスタの qubits の各ペアの間に下回っあり状態が準備されます。</span><span class="sxs-lookup"><span data-stu-id="453d8-105">Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers.</span></span>
<span data-ttu-id="453d8-106">すべての qubits は、| 0 ⟩状態で開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="453d8-106">All qubits must start in the |0⟩ state.</span></span>

<span data-ttu-id="453d8-107">結果として、各レジスタからの対応する qubits のペアは、$ \ket{\ {beta_ {00} } beta_ {00} } $ にあります。</span><span class="sxs-lookup"><span data-stu-id="453d8-107">The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.</span></span>

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="453d8-108">入力</span><span class="sxs-lookup"><span data-stu-id="453d8-108">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="453d8-109">left: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="453d8-109">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="453d8-110">$ \Ket{0\cdots 0} $ 状態の qubit 配列</span><span class="sxs-lookup"><span data-stu-id="453d8-110">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="453d8-111">right: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="453d8-111">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="453d8-112">$ \Ket{0\cdots 0} $ 状態の qubit 配列</span><span class="sxs-lookup"><span data-stu-id="453d8-112">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="453d8-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="453d8-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

