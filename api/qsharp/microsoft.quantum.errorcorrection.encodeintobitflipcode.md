---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: EncodeIntoBitFlipCode 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: 694d3f7a412b64b0ad533b4478a9274384d05c61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712406"
---
# <a name="encodeintobitflipcode-operation"></a><span data-ttu-id="3e7cc-102">EncodeIntoBitFlipCode 操作</span><span class="sxs-lookup"><span data-stu-id="3e7cc-102">EncodeIntoBitFlipCode operation</span></span>

<span data-ttu-id="3e7cc-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="3e7cc-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="3e7cc-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3e7cc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3e7cc-105">[3, 1, 3]/⟦ 3, 1, 1 ⟧ビットフリップコードにエンコードされます。</span><span class="sxs-lookup"><span data-stu-id="3e7cc-105">Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation EncodeIntoBitFlipCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="3e7cc-106">入力</span><span class="sxs-lookup"><span data-stu-id="3e7cc-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="3e7cc-107">physRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3e7cc-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3e7cc-108">保護されるデータを表す物理 qubits のレジスタ。</span><span class="sxs-lookup"><span data-stu-id="3e7cc-108">A register of physical qubits representing the data to be protected.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="3e7cc-109">auxQubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3e7cc-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3e7cc-110">{00}保護されるデータのエンコードに使用される、$ \ket $ 状態の最初の補助 qubits のレジスタ。</span><span class="sxs-lookup"><span data-stu-id="3e7cc-110">A register of auxiliary qubits initially in the $\ket{00}$ state to be used in encoding the data to be protected.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="3e7cc-111">出力: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="3e7cc-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="3e7cc-112">エンコーディングで使用される物理および補助 qubits。論理レジスタとして表されます。</span><span class="sxs-lookup"><span data-stu-id="3e7cc-112">The physical and auxiliary qubits used in encoding, represented as a logical register.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e7cc-113">参照</span><span class="sxs-lookup"><span data-stu-id="3e7cc-113">See Also</span></span>

- [<span data-ttu-id="3e7cc-114">Microsoft... ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="3e7cc-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)