---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: ApplyMultiplyControlledLowDepthAnd 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 6900f9b0f014fba28ae73a70f180f3e4696900cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717950"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a><span data-ttu-id="a5c31-102">ApplyMultiplyControlledLowDepthAnd 操作</span><span class="sxs-lookup"><span data-stu-id="a5c31-102">ApplyMultiplyControlledLowDepthAnd operation</span></span>

<span data-ttu-id="a5c31-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a5c31-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a5c31-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a5c31-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a5c31-105">ターゲット qubit が初期化されていることを前提として、複数の制御を行う Toffoli ゲートを実装します。</span><span class="sxs-lookup"><span data-stu-id="a5c31-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="a5c31-106">Adjoint 操作では、ターゲットの qubit が0にリセットされることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="a5c31-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>  <span data-ttu-id="a5c31-107">Rz の深さは1である必要がありますが、ヘルパーの qubits の数は qubits の数で指数で表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5c31-107">Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.</span></span>

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="a5c31-108">入力</span><span class="sxs-lookup"><span data-stu-id="a5c31-108">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="a5c31-109">コントロール: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a5c31-109">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a5c31-110">制御 qubits</span><span class="sxs-lookup"><span data-stu-id="a5c31-110">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="a5c31-111">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a5c31-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a5c31-112">ターゲット qubit</span><span class="sxs-lookup"><span data-stu-id="a5c31-112">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="a5c31-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a5c31-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

