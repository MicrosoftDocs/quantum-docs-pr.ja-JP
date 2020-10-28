---
uid: Microsoft.Quantum.ErrorCorrection.Recover
title: 回復操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: Recover
qsharp.summary: Performs a single round of error correction by a quantum code described by a `QECC` type.
ms.openlocfilehash: a659399f51794a4edc1d2ff43da84e46797103fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712210"
---
# <a name="recover-operation"></a><span data-ttu-id="a9655-102">回復操作</span><span class="sxs-lookup"><span data-stu-id="a9655-102">Recover operation</span></span>

<span data-ttu-id="a9655-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="a9655-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="a9655-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a9655-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a9655-105">型によって記述されたクォンタムコードによって、1回のエラー修正を実行し `QECC` ます。</span><span class="sxs-lookup"><span data-stu-id="a9655-105">Performs a single round of error correction by a quantum code described by a `QECC` type.</span></span>

```qsharp
operation Recover (code : Microsoft.Quantum.ErrorCorrection.QECC, fn : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a><span data-ttu-id="a9655-106">入力</span><span class="sxs-lookup"><span data-stu-id="a9655-106">Input</span></span>

### <a name="code--qecc"></a><span data-ttu-id="a9655-107">コード: [Qecc](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="a9655-107">code : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="a9655-108">クォンタムエラー-型としてパッケージ化されたコードを修正するには、 `QECC` クォンタムデータのエンコードとデコード、およびエラー syndromes の測定方法を記述します。</span><span class="sxs-lookup"><span data-stu-id="a9655-108">A quantum error-correcting code packaged as a `QECC` type describes the encoding and decoding of quantum data, and how error syndromes are to be measured.</span></span>


### <a name="fn--recoveryfn"></a><span data-ttu-id="a9655-109">fn: [Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="a9655-109">fn : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="a9655-110">`RecoveryFn` `Pauli[]` 検出されたエラーを修正する操作に各エラーより隣人をマップする。</span><span class="sxs-lookup"><span data-stu-id="a9655-110">A `RecoveryFn` that maps each error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="a9655-111">logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="a9655-111">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="a9655-112">安定板のコードが定義されている qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="a9655-112">An array of qubits where the stabilizer code is defined.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a9655-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a9655-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="a9655-114">参照</span><span class="sxs-lookup"><span data-stu-id="a9655-114">See Also</span></span>

- [<span data-ttu-id="a9655-115">Microsoft... ErrorCorrection. QECC</span><span class="sxs-lookup"><span data-stu-id="a9655-115">Microsoft.Quantum.ErrorCorrection.QECC</span></span>](xref:Microsoft.Quantum.ErrorCorrection.QECC)
- [<span data-ttu-id="a9655-116">Microsoft... ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="a9655-116">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [<span data-ttu-id="a9655-117">Microsoft... ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="a9655-117">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)