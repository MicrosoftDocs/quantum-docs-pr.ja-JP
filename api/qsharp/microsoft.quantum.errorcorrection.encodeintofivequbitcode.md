---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: EncodeIntoFiveQubitCode 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 1bccf46453ad34199dcebc5bcff693359fe2254c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826315"
---
# <a name="encodeintofivequbitcode-operation"></a><span data-ttu-id="8ec92-102">EncodeIntoFiveQubitCode 操作</span><span class="sxs-lookup"><span data-stu-id="8ec92-102">EncodeIntoFiveQubitCode operation</span></span>

<span data-ttu-id="8ec92-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="8ec92-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="8ec92-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8ec92-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8ec92-105">⟦ 5, 1, 3 ⟧クォンタムコードにエンコードします。</span><span class="sxs-lookup"><span data-stu-id="8ec92-105">Encodes into the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="8ec92-106">入力</span><span class="sxs-lookup"><span data-stu-id="8ec92-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="8ec92-107">physRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8ec92-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8ec92-108">エンコード前の状態を表す qubit。</span><span class="sxs-lookup"><span data-stu-id="8ec92-108">A qubit representing an unencoded state.</span></span> <span data-ttu-id="8ec92-109">この配列 `Qubit[]` の長さは1です。</span><span class="sxs-lookup"><span data-stu-id="8ec92-109">This array `Qubit[]` is of length 1.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="8ec92-110">auxQubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8ec92-110">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8ec92-111">エンコードされた状態を表すために使用される補助 qubits のレジスタ。</span><span class="sxs-lookup"><span data-stu-id="8ec92-111">A register of auxiliary qubits that will be used to represent the encoded state.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="8ec92-112">出力: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="8ec92-112">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="8ec92-113">エンコードされた `LogicalRegister` 状態を格納する型の物理 qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="8ec92-113">An array of physical qubits of type `LogicalRegister` that store the encoded state.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ec92-114">参照</span><span class="sxs-lookup"><span data-stu-id="8ec92-114">See Also</span></span>

- [<span data-ttu-id="8ec92-115">Microsoft... ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="8ec92-115">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)