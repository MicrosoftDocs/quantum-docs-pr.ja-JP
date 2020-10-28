---
uid: Microsoft.Quantum.Canon.AndLadder
title: AndLadder 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: 05a0e8110539742501883fea75ac368d9946164d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718483"
---
# <a name="andladder-operation"></a><span data-ttu-id="ce02c-102">AndLadder 操作</span><span class="sxs-lookup"><span data-stu-id="ce02c-102">AndLadder operation</span></span>

<span data-ttu-id="ce02c-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ce02c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ce02c-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ce02c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ce02c-105">ターゲット qubits のレジスタで、制御された "AND はしご" を実行します。</span><span class="sxs-lookup"><span data-stu-id="ce02c-105">Performs a controlled "AND ladder" on a register of target qubits.</span></span>

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="description"></a><span data-ttu-id="ce02c-106">説明</span><span class="sxs-lookup"><span data-stu-id="ce02c-106">Description</span></span>

<span data-ttu-id="ce02c-107">この操作は、次の計算基準のマッピングによって記述された変換を適用します $ $ \begin{align} \ket{x \_ 1, \ ドット, x \_ n} \ket{y \_ 1, \ ドット, y \_ {n-1}} \ map\ket{\ket{x \_ 1, \ ドット, x \_ n} y \_ 1 \ oplus (x \_ 1 \ 陸 x \_ 2), \ ドット, y \_ {n-1} \ oplus (x \_ 1 \ \ket{x x \_ \_ {n-1}}, \end{align} $ $ where $ \_ 1, \ \ ($ 1, \) ドット, x \_ n} $ は、の計算ベースの状態を示し `controls` \_ ます。 $ \ket{y 1、\ ドット、y \_ {n-1}} $ は、の計算ベースの状態を表し `targets` ます。</span><span class="sxs-lookup"><span data-stu-id="ce02c-107">This operation applies a transformation described by the following mapping of the computational basis, $$ \begin{align} \ket{x\_1, \dots, x\_n} \ket{y\_1, \dots, y\_{n - 1}} \mapsto \ket{x\_1, \dots, x\_n} \ket{ y\_1 \oplus (x\_1 \land x\_2), \dots, y\_{n - 1} \oplus (x\_1 \land x\_2 \land \cdots \land x\_{n - 1} }, \end{align} $$ where $\ket{x\_1, \dots, x\_n}$ refers to the computational basis states of `controls`, and where $\ket{y\_1, \dots, y\_{n - 1}}$ refers to the computational basis states of `targets`.</span></span>

## <a name="input"></a><span data-ttu-id="ce02c-108">入力</span><span class="sxs-lookup"><span data-stu-id="ce02c-108">Input</span></span>

### <a name="ccnot--ccnotop"></a><span data-ttu-id="ce02c-109">ccnot: [Ccnotop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="ce02c-109">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="ce02c-110">構築に使用する CCNOT ゲート。</span><span class="sxs-lookup"><span data-stu-id="ce02c-110">The CCNOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="ce02c-111">コントロール: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ce02c-111">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ce02c-112">およびはしごのコントロールとして使用される qubits のレジスタ。</span><span class="sxs-lookup"><span data-stu-id="ce02c-112">A register of qubits to be used as controls for the and ladder.</span></span>
<span data-ttu-id="ce02c-113">この操作では、計算ベースの状態が `controls` 不変になります。</span><span class="sxs-lookup"><span data-stu-id="ce02c-113">This operation leaves computational basis states of `controls` invariant.</span></span>
<span data-ttu-id="ce02c-114">の長さは2以上でなければなりません。また、の長さは `controls` 1 以上にする必要があり `targets` ます。</span><span class="sxs-lookup"><span data-stu-id="ce02c-114">The length of `controls` must be at least 2, and must be equal to one plus the length of `targets`.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="ce02c-115">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ce02c-115">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ce02c-116">の長さは `targets` 1 以上、の長さから1を引いた値にする必要があり `controls` ます。</span><span class="sxs-lookup"><span data-stu-id="ce02c-116">The length of `targets` must be at least 1 and equal to the length of `controls` minus one.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ce02c-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ce02c-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ce02c-118">解説</span><span class="sxs-lookup"><span data-stu-id="ce02c-118">Remarks</span></span>

- <span data-ttu-id="ce02c-119">およびの一部として使用され <xref:microsoft.quantum.canon.applymulticontrolledc> <xref:microsoft.quantum.canon.applymulticontrolledca> ます。</span><span class="sxs-lookup"><span data-stu-id="ce02c-119">Used as a part of <xref:microsoft.quantum.canon.applymulticontrolledc> and <xref:microsoft.quantum.canon.applymulticontrolledca>.</span></span>
- <span data-ttu-id="ce02c-120">説明とサーキットの図については、図4.10 のセクション4.3 を参照してください & 語。</span><span class="sxs-lookup"><span data-stu-id="ce02c-120">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang.</span></span>

## <a name="references"></a><span data-ttu-id="ce02c-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="ce02c-121">References</span></span>

- [<span data-ttu-id="ce02c-122">*Michael、Isaac、語* 、量子計算、およびクォンタム情報</span><span class="sxs-lookup"><span data-stu-id="ce02c-122"> *Michael A. Nielsen , Isaac L. Chuang* , Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)