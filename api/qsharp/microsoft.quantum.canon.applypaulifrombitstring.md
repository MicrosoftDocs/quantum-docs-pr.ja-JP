---
uid: Microsoft.Quantum.Canon.ApplyPauliFromBitString
title: ApplyPauliFromBitString 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauliFromBitString
qsharp.summary: Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.
ms.openlocfilehash: 09754accb92c1339b781003e5722e3c8f5884e6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717810"
---
# <a name="applypaulifrombitstring-operation"></a><span data-ttu-id="12ce1-102">ApplyPauliFromBitString 操作</span><span class="sxs-lookup"><span data-stu-id="12ce1-102">ApplyPauliFromBitString operation</span></span>

<span data-ttu-id="12ce1-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="12ce1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="12ce1-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="12ce1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="12ce1-105">ブール値配列の対応するビットが指定された入力と一致する場合、配列内の各 qubit に対して P# li 演算子を適用します。</span><span class="sxs-lookup"><span data-stu-id="12ce1-105">Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.</span></span>

```qsharp
operation ApplyPauliFromBitString (pauli : Pauli, bitApply : Bool, bits : Bool[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="12ce1-106">入力</span><span class="sxs-lookup"><span data-stu-id="12ce1-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="12ce1-107">p# li: [p#](xref:microsoft.quantum.lang-ref.pauli) li</span><span class="sxs-lookup"><span data-stu-id="12ce1-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="12ce1-108">Where に適用する p# li 演算子 `qubits[idx]``bitsApply == bits[idx]`</span><span class="sxs-lookup"><span data-stu-id="12ce1-108">Pauli operator to apply to `qubits[idx]` where `bitsApply == bits[idx]`</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="12ce1-109">bitApply: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="12ce1-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="12ce1-110">bit がこの値の場合は P# li を適用します</span><span class="sxs-lookup"><span data-stu-id="12ce1-110">apply Pauli if bit is this value</span></span>


### <a name="bits--bool"></a><span data-ttu-id="12ce1-111">bits: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="12ce1-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="12ce1-112">の対応する qubit を指定するブールレジスタ `qubits`</span><span class="sxs-lookup"><span data-stu-id="12ce1-112">Boolean register specifying which corresponding qubit in `qubits` should be operated on</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="12ce1-113">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="12ce1-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="12ce1-114">指定された P# li 演算子を選択的に適用するクォンタムレジスタ</span><span class="sxs-lookup"><span data-stu-id="12ce1-114">Quantum register on which to selectively apply the specified Pauli operator</span></span>



## <a name="output--unit"></a><span data-ttu-id="12ce1-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="12ce1-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="12ce1-116">解説</span><span class="sxs-lookup"><span data-stu-id="12ce1-116">Remarks</span></span>

<span data-ttu-id="12ce1-117">ブール型の配列とクォンタムレジスタは同じ長さである必要があります。</span><span class="sxs-lookup"><span data-stu-id="12ce1-117">The Boolean array and the quantum register must be of equal length.</span></span>