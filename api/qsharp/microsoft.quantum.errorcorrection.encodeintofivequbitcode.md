---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: EncodeIntoFiveQubitCode 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: c9df4c5c98a78cae8b3af4597020d35469454153
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712397"
---
# <a name="encodeintofivequbitcode-operation"></a><span data-ttu-id="af0aa-102">EncodeIntoFiveQubitCode 操作</span><span class="sxs-lookup"><span data-stu-id="af0aa-102">EncodeIntoFiveQubitCode operation</span></span>

<span data-ttu-id="af0aa-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="af0aa-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="af0aa-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="af0aa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="af0aa-105">⟦ 5, 1, 3 ⟧クォンタムコードにエンコードします。</span><span class="sxs-lookup"><span data-stu-id="af0aa-105">Encodes into the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="af0aa-106">入力</span><span class="sxs-lookup"><span data-stu-id="af0aa-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="af0aa-107">physRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="af0aa-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="af0aa-108">エンコード前の状態を表す qubit。</span><span class="sxs-lookup"><span data-stu-id="af0aa-108">A qubit representing an unencoded state.</span></span> <span data-ttu-id="af0aa-109">この配列 `Qubit[]` の長さは1です。</span><span class="sxs-lookup"><span data-stu-id="af0aa-109">This array `Qubit[]` is of length 1.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="af0aa-110">auxQubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="af0aa-110">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="af0aa-111">エンコードされた状態を表すために使用される補助 qubits のレジスタ。</span><span class="sxs-lookup"><span data-stu-id="af0aa-111">A register of auxiliary qubits that will be used to represent the encoded state.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="af0aa-112">出力: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="af0aa-112">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="af0aa-113">エンコードされた `LogicalRegister` 状態を格納する型の物理 qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="af0aa-113">An array of physical qubits of type `LogicalRegister` that store the encoded state.</span></span>

## <a name="see-also"></a><span data-ttu-id="af0aa-114">参照</span><span class="sxs-lookup"><span data-stu-id="af0aa-114">See Also</span></span>

- [<span data-ttu-id="af0aa-115">Microsoft... ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="af0aa-115">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)