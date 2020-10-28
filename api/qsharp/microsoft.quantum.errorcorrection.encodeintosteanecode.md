---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoSteaneCode
title: EncodeIntoSteaneCode 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoSteaneCode
qsharp.summary: An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 39b8ab549413d9d5281f6b84a6e970c45242fca8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712392"
---
# <a name="encodeintosteanecode-operation"></a><span data-ttu-id="7f834-102">EncodeIntoSteaneCode 操作</span><span class="sxs-lookup"><span data-stu-id="7f834-102">EncodeIntoSteaneCode operation</span></span>

<span data-ttu-id="7f834-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="7f834-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="7f834-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7f834-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7f834-105">エンコードされていないクォンタムレジスタを⟦7、1、3⟧ Steane 量子コードでエンコードされたクォンタムレジスタにマップするエンコーディング操作。</span><span class="sxs-lookup"><span data-stu-id="7f834-105">An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
operation EncodeIntoSteaneCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="7f834-106">入力</span><span class="sxs-lookup"><span data-stu-id="7f834-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="7f834-107">physRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7f834-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7f834-108">エンコードされていないクォンタム状態を保持する qubit レジスタ</span><span class="sxs-lookup"><span data-stu-id="7f834-108">A qubit register which holds the an unencoded quantum state</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="7f834-109">auxQubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7f834-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7f834-110">最初は0で、エンコーディング操作を実行できるようにクォンタムシステムに追加される qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="7f834-110">A qubit register which is initially zero and which gets added to the quantum system so that an encoding operation can be performed</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="7f834-111">出力: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="7f834-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="7f834-112">Steane encoder が適用された後の状態を保持するクォンタムレジスタ</span><span class="sxs-lookup"><span data-stu-id="7f834-112">A quantum register holding the state after the Steane encoder has been applied</span></span>

## <a name="see-also"></a><span data-ttu-id="7f834-113">参照</span><span class="sxs-lookup"><span data-stu-id="7f834-113">See Also</span></span>

- [<span data-ttu-id="7f834-114">Microsoft... ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="7f834-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="7f834-115">SteaneCodeDecoder を修正します。</span><span class="sxs-lookup"><span data-stu-id="7f834-115">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)