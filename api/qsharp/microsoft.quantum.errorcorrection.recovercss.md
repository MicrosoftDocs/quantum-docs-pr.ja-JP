---
uid: Microsoft.Quantum.ErrorCorrection.RecoverCSS
title: 回復した Css 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: RecoverCSS
qsharp.summary: Performs a single round of error correction by a quantum code described by a `CSS` type.
ms.openlocfilehash: 48d3cd3d5f6aea265fac2f50b913ab855a31accf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712201"
---
# <a name="recovercss-operation"></a><span data-ttu-id="c795d-102">回復した Css 操作</span><span class="sxs-lookup"><span data-stu-id="c795d-102">RecoverCSS operation</span></span>

<span data-ttu-id="c795d-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="c795d-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="c795d-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c795d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c795d-105">型によって記述されたクォンタムコードによって、1回のエラー修正を実行し `CSS` ます。</span><span class="sxs-lookup"><span data-stu-id="c795d-105">Performs a single round of error correction by a quantum code described by a `CSS` type.</span></span>

```qsharp
operation RecoverCSS (code : Microsoft.Quantum.ErrorCorrection.CSS, fnX : Microsoft.Quantum.ErrorCorrection.RecoveryFn, fnZ : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a><span data-ttu-id="c795d-106">入力</span><span class="sxs-lookup"><span data-stu-id="c795d-106">Input</span></span>

### <a name="code--css"></a><span data-ttu-id="c795d-107">コード: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="c795d-107">code : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="c795d-108">クォンタム CSS エラー-型としてパッケージ化されたコードを修正すると、 `CSS` クォンタムデータのエンコードとデコード、およびエラー syndromes の測定方法が記述されます。</span><span class="sxs-lookup"><span data-stu-id="c795d-108">A quantum CSS error-correcting code packaged as a `CSS` type describes the encoding and decoding of quantum data, and how error syndromes are to be measured.</span></span>


### <a name="fnx--recoveryfn"></a><span data-ttu-id="c795d-109">fnX: [Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="c795d-109">fnX : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="c795d-110">`RecoveryFn`各 $X $ error より隣人を、 `Pauli[]` 検出されたエラーを修正する操作にマップする。</span><span class="sxs-lookup"><span data-stu-id="c795d-110">A `RecoveryFn` that maps each $X$ error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="fnz--recoveryfn"></a><span data-ttu-id="c795d-111">fnZ: [Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="c795d-111">fnZ : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="c795d-112">`RecoveryFn`各 $Z $ error より隣人を、 `Pauli[]` 検出されたエラーを修正する操作にマップする。</span><span class="sxs-lookup"><span data-stu-id="c795d-112">A `RecoveryFn` that maps each $Z$ error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="c795d-113">logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="c795d-113">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="c795d-114">安定板のコードが定義されている qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="c795d-114">An array of qubits where the stabilizer code is defined.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c795d-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c795d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="c795d-116">参照</span><span class="sxs-lookup"><span data-stu-id="c795d-116">See Also</span></span>

- [<span data-ttu-id="c795d-117">Microsoft... ErrorCorrection .CSS</span><span class="sxs-lookup"><span data-stu-id="c795d-117">Microsoft.Quantum.ErrorCorrection.CSS</span></span>](xref:Microsoft.Quantum.ErrorCorrection.CSS)
- [<span data-ttu-id="c795d-118">Microsoft... ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="c795d-118">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [<span data-ttu-id="c795d-119">Microsoft... ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="c795d-119">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)