---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: ユーザー定義型の制御
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 1e664b470caeba656ea4a73f70bbc0ef5fe76f7e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196567"
---
# <a name="controlledrotation-user-defined-type"></a><span data-ttu-id="fd262-102">ユーザー定義型の制御</span><span class="sxs-lookup"><span data-stu-id="fd262-102">ControlledRotation user defined type</span></span>

<span data-ttu-id="fd262-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="fd262-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="fd262-104">パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="fd262-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="fd262-105">ターゲットと制御のインデックス、回転軸、およびモデルパラメーターベクターへのインデックスに関して、制御されたローテーションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fd262-105">Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.</span></span>

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a><span data-ttu-id="fd262-106">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="fd262-106">Named Items</span></span>

### <a name="targetindex--int"></a><span data-ttu-id="fd262-107">TargetIndex: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fd262-107">TargetIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fd262-108">この制御された回転のターゲット qubit のインデックス。</span><span class="sxs-lookup"><span data-stu-id="fd262-108">Index of the target qubit for this controlled rotation.</span></span>
### <a name="controlindices--int"></a><span data-ttu-id="fd262-109">ControlIndices: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="fd262-109">ControlIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="fd262-110">この回転のためのコントロール qubit インデックスの配列。</span><span class="sxs-lookup"><span data-stu-id="fd262-110">An array of the control qubit indices for this rotation.</span></span>
### <a name="axis--pauli"></a><span data-ttu-id="fd262-111">Axis: [P# li](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="fd262-111">Axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="fd262-112">この回転の軸。</span><span class="sxs-lookup"><span data-stu-id="fd262-112">The axis for this rotation.</span></span>
### <a name="parameterindex--int"></a><span data-ttu-id="fd262-113">ParameterIndex: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fd262-113">ParameterIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fd262-114">この回転の角度を説明するモデルパラメーターベクターのインデックス。</span><span class="sxs-lookup"><span data-stu-id="fd262-114">An index into a model parameter vector describing the angle for this rotation.</span></span>

## <a name="remarks"></a><span data-ttu-id="fd262-115">解説</span><span class="sxs-lookup"><span data-stu-id="fd262-115">Remarks</span></span>

<span data-ttu-id="fd262-116">制御されないローテーションは `ControlIndices` 、インデックスの空の配列にを設定することによって表すことができ `new Int[0]` ます。</span><span class="sxs-lookup"><span data-stu-id="fd262-116">An uncontrolled rotation can be represented by setting `ControlIndices` to an empty array of indexes, `new Int[0]`.</span></span>