---
uid: Microsoft.Quantum.Preparation.PreparePauliEigenstate
title: PreparePauliEigenstate 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PreparePauliEigenstate
qsharp.summary: Prepares a qubit in the positive eigenstate of a given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.
ms.openlocfilehash: b24852bb3a455a9fe04b3535156d0c3dfb1a7d12
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193694"
---
# <a name="preparepaulieigenstate-operation"></a><span data-ttu-id="cbb92-102">PreparePauliEigenstate 操作</span><span class="sxs-lookup"><span data-stu-id="cbb92-102">PreparePauliEigenstate operation</span></span>

<span data-ttu-id="cbb92-103">名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="cbb92-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="cbb92-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cbb92-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cbb92-105">指定された Pauli 演算子の正の eigenstate で qubit を準備します。</span><span class="sxs-lookup"><span data-stu-id="cbb92-105">Prepares a qubit in the positive eigenstate of a given Pauli operator.</span></span>
<span data-ttu-id="cbb92-106">Id 演算子が指定されている場合、qubit は下回っ mixed 状態で準備されます。</span><span class="sxs-lookup"><span data-stu-id="cbb92-106">If the identity operator is given, then the qubit is prepared in the maximally mixed state.</span></span>

```qsharp
operation PreparePauliEigenstate (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="cbb92-107">説明</span><span class="sxs-lookup"><span data-stu-id="cbb92-107">Description</span></span>

<span data-ttu-id="cbb92-108">Qubit が最初に $ \ket $ 状態であった場合 {0} 、この操作は、指定された p li 演算子の $ + $1 eigenstate の qubit を準備します。または、の場合は、 `PauliI` 代わりに下回っ mixed 状態 (を参照) で qubit を準備し <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ます。</span><span class="sxs-lookup"><span data-stu-id="cbb92-108">If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).</span></span>

<span data-ttu-id="cbb92-109">Qubit が $ \ket $ 以外の状態であった場合 {0} 、この操作では次のゲートが適用されます。 $H $ for `PauliX` 、$HS $ for `PauliY` 、$I $ for `PauliZ` および <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI` 。</span><span class="sxs-lookup"><span data-stu-id="cbb92-109">If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.</span></span>

## <a name="input"></a><span data-ttu-id="cbb92-110">入力</span><span class="sxs-lookup"><span data-stu-id="cbb92-110">Input</span></span>

### <a name="basis--pauli"></a><span data-ttu-id="cbb92-111">基礎: [P# li](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="cbb92-111">basis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="cbb92-112">P$P Li 演算子は $ です。</span><span class="sxs-lookup"><span data-stu-id="cbb92-112">A Pauli operator $P$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="cbb92-113">qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cbb92-113">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cbb92-114">準備する qubit。</span><span class="sxs-lookup"><span data-stu-id="cbb92-114">A qubit to be prepared.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cbb92-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cbb92-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

