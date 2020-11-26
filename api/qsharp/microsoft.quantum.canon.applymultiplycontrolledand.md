---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: Apply乗数 Ycontrol/operation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: 17a757278500833bc5a5d0635af020cfe1fd569f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218395"
---
# <a name="applymultiplycontrolledand-operation"></a><span data-ttu-id="aa261-102">Apply乗数 Ycontrol/operation</span><span class="sxs-lookup"><span data-stu-id="aa261-102">ApplyMultiplyControlledAnd operation</span></span>

<span data-ttu-id="aa261-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="aa261-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="aa261-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aa261-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aa261-105">ターゲット qubit が初期化されていることを前提として、複数の制御を行う Toffoli ゲートを実装します。</span><span class="sxs-lookup"><span data-stu-id="aa261-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="aa261-106">Adjoint 操作では、ターゲットの qubit が0にリセットされることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="aa261-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="aa261-107">入力</span><span class="sxs-lookup"><span data-stu-id="aa261-107">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="aa261-108">コントロール: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="aa261-108">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="aa261-109">制御 qubits</span><span class="sxs-lookup"><span data-stu-id="aa261-109">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="aa261-110">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="aa261-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="aa261-111">ターゲット qubit</span><span class="sxs-lookup"><span data-stu-id="aa261-111">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="aa261-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa261-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

