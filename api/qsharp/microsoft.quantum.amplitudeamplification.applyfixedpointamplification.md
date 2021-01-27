---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: ApplyFixedPointAmplification 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: fa19c3bb06ae91a2fa18acb6f853020830e749f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847226"
---
# <a name="applyfixedpointamplification-operation"></a><span data-ttu-id="a28b4-102">ApplyFixedPointAmplification 操作</span><span class="sxs-lookup"><span data-stu-id="a28b4-102">ApplyFixedPointAmplification operation</span></span>

<span data-ttu-id="a28b4-103">名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="a28b4-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="a28b4-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a28b4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a28b4-105">Fixed-Point 振幅増幅アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="a28b4-105">Fixed-Point Amplitude Amplification algorithm</span></span>

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a28b4-106">入力</span><span class="sxs-lookup"><span data-stu-id="a28b4-106">Input</span></span>

### <a name="statepreporacle--stateoracle"></a><span data-ttu-id="a28b4-107">statePrepOracle: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="a28b4-107">statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="a28b4-108">開始状態を準備する oracle のユニタリ。</span><span class="sxs-lookup"><span data-stu-id="a28b4-108">Unitary oracle that prepares the start state.</span></span>


### <a name="startqubits--qubit"></a><span data-ttu-id="a28b4-109">startQubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a28b4-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a28b4-110">Qubit レジスタ</span><span class="sxs-lookup"><span data-stu-id="a28b4-110">Qubit register</span></span>



## <a name="output--unit"></a><span data-ttu-id="a28b4-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a28b4-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a28b4-112">解説</span><span class="sxs-lookup"><span data-stu-id="a28b4-112">Remarks</span></span>

<span data-ttu-id="a28b4-113">StartQubits は、$ \ket{0 \ cドット 0} $ 状態である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a28b4-113">The startQubits must be in the $\ket{0 \cdots 0}$ state.</span></span> <span data-ttu-id="a28b4-114">この操作では、最大数のクエリに到達するか、ターゲットの状態が検出されるまで、$2 $ の累乗による多数のクエリを反復処理します。</span><span class="sxs-lookup"><span data-stu-id="a28b4-114">This operation iterates over a number of queries in powers of $2$ until either a maximal number of queries is reached, or the target state is found.</span></span>