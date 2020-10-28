---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromBitFlipCode
title: DecodeFromBitFlipCode 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromBitFlipCode
qsharp.summary: Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: be6ad5fce9eeb3eea031ff301b78dbb3680b66f0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712481"
---
# <a name="decodefrombitflipcode-operation"></a><span data-ttu-id="c514d-102">DecodeFromBitFlipCode 操作</span><span class="sxs-lookup"><span data-stu-id="c514d-102">DecodeFromBitFlipCode operation</span></span>

<span data-ttu-id="c514d-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="c514d-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="c514d-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c514d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c514d-105">[3, 1, 3]/⟦ 3, 1, 1 ⟧ビットフリップコードからデコードします。</span><span class="sxs-lookup"><span data-stu-id="c514d-105">Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation DecodeFromBitFlipCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="c514d-106">入力</span><span class="sxs-lookup"><span data-stu-id="c514d-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="c514d-107">logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="c514d-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="c514d-108">ビットフリップコードのコードブロック。</span><span class="sxs-lookup"><span data-stu-id="c514d-108">A code block of the bit-flip code.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="c514d-109">出力: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="c514d-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="c514d-110">論理レジスタにエンコードされたデータの組と、より隣人を表すために使用される補助 qubits。</span><span class="sxs-lookup"><span data-stu-id="c514d-110">A tuple of the data encoded into the logical register, and the auxiliary qubits used to represent the syndrome.</span></span>

## <a name="see-also"></a><span data-ttu-id="c514d-111">参照</span><span class="sxs-lookup"><span data-stu-id="c514d-111">See Also</span></span>

- [<span data-ttu-id="c514d-112">Microsoft... ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="c514d-112">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="c514d-113">EncodeIntoBitFlipCode を修正します。</span><span class="sxs-lookup"><span data-stu-id="c514d-113">Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode</span></span>](xref:Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode)