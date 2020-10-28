---
uid: Microsoft.Quantum.Canon.LogicalANDMeasAndFix
title: LogicalANDMeasAndFix 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: LogicalANDMeasAndFix
qsharp.summary: Computes the logical AND of multiple qubits.
ms.openlocfilehash: 86e4b9a8c6ed5f4f56db0ceefc8051d34e911c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715925"
---
# <a name="logicalandmeasandfix-operation"></a><span data-ttu-id="480db-102">LogicalANDMeasAndFix 操作</span><span class="sxs-lookup"><span data-stu-id="480db-102">LogicalANDMeasAndFix operation</span></span>

<span data-ttu-id="480db-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="480db-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="480db-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="480db-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="480db-105">複数の qubits の論理 AND を計算します。</span><span class="sxs-lookup"><span data-stu-id="480db-105">Computes the logical AND of multiple qubits.</span></span>

```qsharp
operation LogicalANDMeasAndFix (ctrlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="480db-106">入力</span><span class="sxs-lookup"><span data-stu-id="480db-106">Input</span></span>

### <a name="ctrlregister--qubit"></a><span data-ttu-id="480db-107">ctrlRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="480db-107">ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="480db-108">複数の入力およびゲートへの qubits 入力。</span><span class="sxs-lookup"><span data-stu-id="480db-108">Qubits input to the multiple-input AND gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="480db-109">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="480db-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="480db-110">およびの出力が書き込まれる qubit。</span><span class="sxs-lookup"><span data-stu-id="480db-110">Qubit on which output of AND is written to.</span></span> <span data-ttu-id="480db-111">これは、常に $ \ket $ 状態で開始することを前提としてい {0} ます。</span><span class="sxs-lookup"><span data-stu-id="480db-111">This is assumed to always start in the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="480db-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="480db-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="480db-113">解説</span><span class="sxs-lookup"><span data-stu-id="480db-113">Remarks</span></span>

<span data-ttu-id="480db-114">`ctrlRegister`が完全に $2 $ qubits である場合、これは操作と同じですが、フェーズ `CCNOT` $e ^ {i \ pi/2} $ on $ \ket {001} $ および $-e ^ {i \ pi/2} $ on $ \ket {101} $ と $ \ket $ に相当し {011} ます。</span><span class="sxs-lookup"><span data-stu-id="480db-114">When `ctrlRegister` has exactly $2$ qubits, this is equivalent to the `CCNOT` operation but phase with a phase $e^{i\Pi/2}$ on $\ket{001}$ and $-e^{i\Pi/2}$ on $\ket{101}$ and $\ket{011}$.</span></span>
<span data-ttu-id="480db-115">Adjoint は、メジャーおよび修正アプローチでもあります。これは、元の操作を特殊なケース (参照を参照) でのみ逆にしたものですが、使用する T ゲートの数が減ります。</span><span class="sxs-lookup"><span data-stu-id="480db-115">The Adjoint is also measure-and-fixup approach that is the inverse of the original operation only in special cases (see references), but uses fewer T-gates.</span></span>

## <a name="references"></a><span data-ttu-id="480db-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="480db-116">References</span></span>

- [<span data-ttu-id="480db-117">*Gidney* 、1709.06648</span><span class="sxs-lookup"><span data-stu-id="480db-117"> *Craig Gidney* , 1709.06648</span></span>](https://arxiv.org/abs/1709.06648)