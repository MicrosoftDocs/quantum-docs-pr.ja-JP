---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: Apply乗数 Ycontrol/operation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: feca28d394e4af31eb4ffe737111d00ede45e27e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717955"
---
# <a name="applymultiplycontrolledand-operation"></a><span data-ttu-id="e721c-102">Apply乗数 Ycontrol/operation</span><span class="sxs-lookup"><span data-stu-id="e721c-102">ApplyMultiplyControlledAnd operation</span></span>

<span data-ttu-id="e721c-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e721c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e721c-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e721c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e721c-105">ターゲット qubit が初期化されていることを前提として、複数の制御を行う Toffoli ゲートを実装します。</span><span class="sxs-lookup"><span data-stu-id="e721c-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="e721c-106">Adjoint 操作では、ターゲットの qubit が0にリセットされることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="e721c-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="e721c-107">入力</span><span class="sxs-lookup"><span data-stu-id="e721c-107">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="e721c-108">コントロール: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e721c-108">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e721c-109">制御 qubits</span><span class="sxs-lookup"><span data-stu-id="e721c-109">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="e721c-110">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e721c-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e721c-111">ターゲット qubit</span><span class="sxs-lookup"><span data-stu-id="e721c-111">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="e721c-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e721c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

