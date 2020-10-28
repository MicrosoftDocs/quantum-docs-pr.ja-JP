---
uid: Microsoft.Quantum.Chemistry.JordanWigner.SelectZ
title: SelectZ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: SelectZ
qsharp.summary: A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$. That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$
ms.openlocfilehash: 171bbe28ce8f10ca4b213a94b23f8c049546e3bf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713792"
---
# <a name="selectz-operation"></a><span data-ttu-id="162fb-102">SelectZ 操作</span><span class="sxs-lookup"><span data-stu-id="162fb-102">SelectZ operation</span></span>

<span data-ttu-id="162fb-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="162fb-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="162fb-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="162fb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="162fb-105">インデックス状態 $ \ket{p} $ に対して、qubits $p $ 条件付きで p Li $Z $ gate を適用する、$U のインデックス番号。</span><span class="sxs-lookup"><span data-stu-id="162fb-105">A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$.</span></span> <span data-ttu-id="162fb-106">つまり、$ $ \begin{align} U\ket {p} \ k {\ psi} = \ket{p}Z \_ p\ket {\ psi} \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="162fb-106">That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$</span></span>

```qsharp
operation SelectZ (indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="162fb-107">入力</span><span class="sxs-lookup"><span data-stu-id="162fb-107">Input</span></span>

### <a name="indexregister--littleendian"></a><span data-ttu-id="162fb-108">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="162fb-108">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="162fb-109">このレジスタの状態 $ \ket{p} $ によって、$Z $ が適用される qubit が決まります。</span><span class="sxs-lookup"><span data-stu-id="162fb-109">The state $\ket{p}$ of this register determines the qubit on which $Z$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="162fb-110">targetRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="162fb-110">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="162fb-111">Pare Li 演算子が適用される qubits の登録です。</span><span class="sxs-lookup"><span data-stu-id="162fb-111">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="162fb-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="162fb-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

