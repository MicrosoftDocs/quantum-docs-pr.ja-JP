---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: ApplyMultiplyControlledLowDepthAnd 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 0ad4b6eabcbbb63751489dd92a13a6673c1ae6b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841671"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a><span data-ttu-id="95734-102">ApplyMultiplyControlledLowDepthAnd 操作</span><span class="sxs-lookup"><span data-stu-id="95734-102">ApplyMultiplyControlledLowDepthAnd operation</span></span>

<span data-ttu-id="95734-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="95734-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="95734-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="95734-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="95734-105">ターゲット qubit が初期化されていることを前提として、複数の制御を行う Toffoli ゲートを実装します。</span><span class="sxs-lookup"><span data-stu-id="95734-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="95734-106">Adjoint 操作では、ターゲットの qubit が0にリセットされることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="95734-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>  <span data-ttu-id="95734-107">Rz の深さは1である必要がありますが、ヘルパーの qubits の数は qubits の数で指数で表示されます。</span><span class="sxs-lookup"><span data-stu-id="95734-107">Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.</span></span>

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="95734-108">入力</span><span class="sxs-lookup"><span data-stu-id="95734-108">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="95734-109">コントロール: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="95734-109">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="95734-110">制御 qubits</span><span class="sxs-lookup"><span data-stu-id="95734-110">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="95734-111">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="95734-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="95734-112">ターゲット qubit</span><span class="sxs-lookup"><span data-stu-id="95734-112">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="95734-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="95734-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

