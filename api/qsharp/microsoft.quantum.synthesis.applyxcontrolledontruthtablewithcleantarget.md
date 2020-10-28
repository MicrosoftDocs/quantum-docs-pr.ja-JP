---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget
title: ApplyXControlledOnTruthTableWithCleanTarget 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTableWithCleanTarget
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: b43a5351985339bcf7c1f2bbe03ae6dc6dfdd165
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725234"
---
# <a name="applyxcontrolledontruthtablewithcleantarget-operation"></a><span data-ttu-id="aee40-102">ApplyXControlledOnTruthTableWithCleanTarget 操作</span><span class="sxs-lookup"><span data-stu-id="aee40-102">ApplyXControlledOnTruthTableWithCleanTarget operation</span></span>

<span data-ttu-id="aee40-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="aee40-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="aee40-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aee40-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aee40-105">の @"microsoft.quantum.intrinsic.x" `target` クラシック代入に対してブール関数が true と評価された場合に、操作をに適用し `func` `controlRegister` ます。</span><span class="sxs-lookup"><span data-stu-id="aee40-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTableWithCleanTarget (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="aee40-106">説明</span><span class="sxs-lookup"><span data-stu-id="aee40-106">Description</span></span>

<span data-ttu-id="aee40-107">この操作では、の特殊なケースを実装します。この場合、 @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" ターゲットの qubit は $ \ket $ 状態であることがわかってい {0} ます。</span><span class="sxs-lookup"><span data-stu-id="aee40-107">This operation implements a special case of @"microsoft.quantum.synthesis.applyxcontrolledontruthtable", in which the target qubit is known to be in the $\ket{0}$ state.</span></span>

<span data-ttu-id="aee40-108">実装では @"microsoft.quantum.intrinsic.cnot" 、およびゲートを使用し @"microsoft.quantum.intrinsic.r1" ます。</span><span class="sxs-lookup"><span data-stu-id="aee40-108">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>  <span data-ttu-id="aee40-109">Adjoint 操作の実装は最適化されており、測定ベースの uncomputation が使用されます。</span><span class="sxs-lookup"><span data-stu-id="aee40-109">The implementation of the adjoint operation is optimized and uses measurement-based uncomputation.</span></span>

## <a name="input"></a><span data-ttu-id="aee40-110">入力</span><span class="sxs-lookup"><span data-stu-id="aee40-110">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="aee40-111">func: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="aee40-111">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="aee40-112">ブール型の真理値テーブルを大きな整数として表現</span><span class="sxs-lookup"><span data-stu-id="aee40-112">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="aee40-113">controlRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="aee40-113">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="aee40-114">制御 qubits の登録</span><span class="sxs-lookup"><span data-stu-id="aee40-114">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="aee40-115">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="aee40-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="aee40-116">ターゲット qubit ($ \ket $ 状態である必要があります {0} )</span><span class="sxs-lookup"><span data-stu-id="aee40-116">Target qubit (must be in $\ket{0}$ state)</span></span>



## <a name="output--unit"></a><span data-ttu-id="aee40-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aee40-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="aee40-118">参照</span><span class="sxs-lookup"><span data-stu-id="aee40-118">See Also</span></span>

- [<span data-ttu-id="aee40-119">ApplyXControlledOnTruthTable です。</span><span class="sxs-lookup"><span data-stu-id="aee40-119">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable)