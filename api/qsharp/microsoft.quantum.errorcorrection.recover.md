---
uid: Microsoft.Quantum.ErrorCorrection.Recover
title: 回復操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: Recover
qsharp.summary: Performs a single round of error correction by a quantum code described by a `QECC` type.
ms.openlocfilehash: 3e2ce404ae3a6b4097897b859388fea3f915232c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825525"
---
# <a name="recover-operation"></a><span data-ttu-id="3a05e-102">回復操作</span><span class="sxs-lookup"><span data-stu-id="3a05e-102">Recover operation</span></span>

<span data-ttu-id="3a05e-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="3a05e-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="3a05e-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3a05e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3a05e-105">型によって記述されたクォンタムコードによって、1回のエラー修正を実行し `QECC` ます。</span><span class="sxs-lookup"><span data-stu-id="3a05e-105">Performs a single round of error correction by a quantum code described by a `QECC` type.</span></span>

```qsharp
operation Recover (code : Microsoft.Quantum.ErrorCorrection.QECC, fn : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a><span data-ttu-id="3a05e-106">入力</span><span class="sxs-lookup"><span data-stu-id="3a05e-106">Input</span></span>

### <a name="code--qecc"></a><span data-ttu-id="3a05e-107">コード: [Qecc](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="3a05e-107">code : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="3a05e-108">クォンタムエラー-型としてパッケージ化されたコードを修正するには、 `QECC` クォンタムデータのエンコードとデコード、およびエラー syndromes の測定方法を記述します。</span><span class="sxs-lookup"><span data-stu-id="3a05e-108">A quantum error-correcting code packaged as a `QECC` type describes the encoding and decoding of quantum data, and how error syndromes are to be measured.</span></span>


### <a name="fn--recoveryfn"></a><span data-ttu-id="3a05e-109">fn: [Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="3a05e-109">fn : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="3a05e-110">`RecoveryFn` `Pauli[]` 検出されたエラーを修正する操作に各エラーより隣人をマップする。</span><span class="sxs-lookup"><span data-stu-id="3a05e-110">A `RecoveryFn` that maps each error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="3a05e-111">logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="3a05e-111">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="3a05e-112">安定板のコードが定義されている qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="3a05e-112">An array of qubits where the stabilizer code is defined.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3a05e-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3a05e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="3a05e-114">参照</span><span class="sxs-lookup"><span data-stu-id="3a05e-114">See Also</span></span>

- [<span data-ttu-id="3a05e-115">Microsoft... ErrorCorrection. QECC</span><span class="sxs-lookup"><span data-stu-id="3a05e-115">Microsoft.Quantum.ErrorCorrection.QECC</span></span>](xref:Microsoft.Quantum.ErrorCorrection.QECC)
- [<span data-ttu-id="3a05e-116">Microsoft... ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="3a05e-116">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [<span data-ttu-id="3a05e-117">Microsoft... ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="3a05e-117">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)