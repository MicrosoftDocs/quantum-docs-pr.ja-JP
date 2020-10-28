---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromFiveQubitCode
title: DecodeFromFiveQubitCode 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromFiveQubitCode
qsharp.summary: Decodes the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 421da6296b604f30aefed58730091f64f19c3a61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712467"
---
# <a name="decodefromfivequbitcode-operation"></a><span data-ttu-id="8f795-102">DecodeFromFiveQubitCode 操作</span><span class="sxs-lookup"><span data-stu-id="8f795-102">DecodeFromFiveQubitCode operation</span></span>

<span data-ttu-id="8f795-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="8f795-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="8f795-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8f795-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8f795-105">⟦ 5, 1, 3 ⟧クォンタムコードをデコードします。</span><span class="sxs-lookup"><span data-stu-id="8f795-105">Decodes the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation DecodeFromFiveQubitCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="8f795-106">入力</span><span class="sxs-lookup"><span data-stu-id="8f795-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="8f795-107">logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="8f795-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="8f795-108">エンコードされた 5-qubits コードの論理状態を表す qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="8f795-108">An array of qubits representing the encoded 5-qubit code logical state.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="8f795-109">出力: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="8f795-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="8f795-110">2番目のパラメーターの補助 qubit と共に、最初のパラメーターのエンコードされていない状態を表す、値1の qubit 配列。</span><span class="sxs-lookup"><span data-stu-id="8f795-110">A qubit array of length 1 representing the unencoded state in the first parameter, together with auxiliary qubits in the second parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f795-111">参照</span><span class="sxs-lookup"><span data-stu-id="8f795-111">See Also</span></span>

- [<span data-ttu-id="8f795-112">Microsoft... Fivvldb Bitcodeencoder</span><span class="sxs-lookup"><span data-stu-id="8f795-112">Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoder)
- [<span data-ttu-id="8f795-113">Microsoft... ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="8f795-113">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)