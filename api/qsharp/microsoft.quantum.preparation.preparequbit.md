---
uid: Microsoft.Quantum.Preparation.PrepareQubit
title: PrepareQubit 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQubit
qsharp.summary: >-
  > [!WARNING]

  > PrepareQubit has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> instead.


  Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.

  If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).

  If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.
ms.openlocfilehash: 84674d70d6a038ceaf1c637b22afa1b724d90795
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193524"
---
# <a name="preparequbit-operation"></a><span data-ttu-id="c11ab-102">PrepareQubit 操作</span><span class="sxs-lookup"><span data-stu-id="c11ab-102">PrepareQubit operation</span></span>

<span data-ttu-id="c11ab-103">名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="c11ab-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="c11ab-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c11ab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="c11ab-105">PrepareQubit は非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="c11ab-105">PrepareQubit has been deprecated.</span></span> <span data-ttu-id="c11ab-106">代わりに、<xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> を使用してください。</span><span class="sxs-lookup"><span data-stu-id="c11ab-106">Please use <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> instead.</span></span>

<span data-ttu-id="c11ab-107">`Zero`指定された Pauli 演算子の + 1 () eigenstate で qubit を準備します。</span><span class="sxs-lookup"><span data-stu-id="c11ab-107">Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator.</span></span>
<span data-ttu-id="c11ab-108">Id 演算子が指定されている場合、qubit は下回っ mixed 状態で準備されます。</span><span class="sxs-lookup"><span data-stu-id="c11ab-108">If the identity operator is given, then the qubit is prepared in the maximally mixed state.</span></span>

<span data-ttu-id="c11ab-109">Qubit が最初に $ \ket $ 状態であった場合 {0} 、この操作は、指定された p li 演算子の $ + $1 eigenstate の qubit を準備します。または、の場合は、 `PauliI` 代わりに下回っ mixed 状態 (を参照) で qubit を準備し <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ます。</span><span class="sxs-lookup"><span data-stu-id="c11ab-109">If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).</span></span>

<span data-ttu-id="c11ab-110">Qubit が $ \ket $ 以外の状態であった場合 {0} 、この操作では次のゲートが適用されます。 $H $ for `PauliX` 、$HS $ for `PauliY` 、$I $ for `PauliZ` および <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI` 。</span><span class="sxs-lookup"><span data-stu-id="c11ab-110">If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.</span></span>

```qsharp
operation PrepareQubit (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="c11ab-111">入力</span><span class="sxs-lookup"><span data-stu-id="c11ab-111">Input</span></span>

### <a name="basis--pauli"></a><span data-ttu-id="c11ab-112">基礎: [P# li](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="c11ab-112">basis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="c11ab-113">P$P Li 演算子は $ です。</span><span class="sxs-lookup"><span data-stu-id="c11ab-113">A Pauli operator $P$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="c11ab-114">qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c11ab-114">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c11ab-115">準備する qubit。</span><span class="sxs-lookup"><span data-stu-id="c11ab-115">A qubit to be prepared.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c11ab-116">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c11ab-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

