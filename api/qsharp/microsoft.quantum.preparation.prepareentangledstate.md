---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: この操作を実行しました
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 5f6e3ea1e7638d3bc446f21ace2968cf8284353a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210473"
---
# <a name="prepareentangledstate-operation"></a><span data-ttu-id="3e2f2-102">この操作を実行しました</span><span class="sxs-lookup"><span data-stu-id="3e2f2-102">PrepareEntangledState operation</span></span>

<span data-ttu-id="3e2f2-103">名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="3e2f2-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="3e2f2-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3e2f2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3e2f2-105">2つの qubit レジスタがペアになります。</span><span class="sxs-lookup"><span data-stu-id="3e2f2-105">Pairwise entangles two qubit registers.</span></span>

<span data-ttu-id="3e2f2-106">つまり、2つのレジスタが指定されている場合、各レジスタの {1} {2} {00} {11} qubits の各ペアの間に、$ \ket{0\cdots 0} $ 状態で各レジスタが開始されたと仮定して、下回っありの状態 $ \ frac {\ sqrt} \ left (\ket + \ket/right) $ を準備します。</span><span class="sxs-lookup"><span data-stu-id="3e2f2-106">That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.</span></span>

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3e2f2-107">入力</span><span class="sxs-lookup"><span data-stu-id="3e2f2-107">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="3e2f2-108">left: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3e2f2-108">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3e2f2-109">$ \Ket{0\cdots 0} $ 状態の qubit 配列</span><span class="sxs-lookup"><span data-stu-id="3e2f2-109">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="3e2f2-110">right: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3e2f2-110">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3e2f2-111">$ \Ket{0\cdots 0} $ 状態の qubit 配列</span><span class="sxs-lookup"><span data-stu-id="3e2f2-111">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="3e2f2-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3e2f2-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

