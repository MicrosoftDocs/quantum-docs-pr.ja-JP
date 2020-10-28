---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: Applycontrol/Int 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: c8ea76946143967de4b6ac65986a1c4407ecb633
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718351"
---
# <a name="applycontrolledonint-operation"></a><span data-ttu-id="ae4fe-102">Applycontrol/Int 操作</span><span class="sxs-lookup"><span data-stu-id="ae4fe-102">ApplyControlledOnInt operation</span></span>

<span data-ttu-id="ae4fe-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ae4fe-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ae4fe-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ae4fe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ae4fe-105">コントロールの登録状態が指定した正の整数に対応する場合は、ターゲットレジスタに対して、値の指定操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="ae4fe-105">Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="ae4fe-106">入力</span><span class="sxs-lookup"><span data-stu-id="ae4fe-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="ae4fe-107">数値の状態: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ae4fe-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ae4fe-108">操作を制御する必要がある負で `oracle` ない整数。</span><span class="sxs-lookup"><span data-stu-id="ae4fe-108">A nonnegative integer on which the operation `oracle` should be controlled.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="ae4fe-109">oracle: t => [ユニット](xref:microsoft.quantum.lang-ref.unit) の調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="ae4fe-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="ae4fe-110">制御される、ユニタリ操作。</span><span class="sxs-lookup"><span data-stu-id="ae4fe-110">A unitary operation to be controlled.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="ae4fe-111">controlRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ae4fe-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ae4fe-112">のアプリケーションを制御するクォンタムレジスタ `oracle` 。</span><span class="sxs-lookup"><span data-stu-id="ae4fe-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="ae4fe-113">targetRegister: ' t '</span><span class="sxs-lookup"><span data-stu-id="ae4fe-113">targetRegister : 'T</span></span>

<span data-ttu-id="ae4fe-114">適用するレジスタ `oracle` 。</span><span class="sxs-lookup"><span data-stu-id="ae4fe-114">A register on which to apply `oracle`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ae4fe-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ae4fe-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ae4fe-116">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="ae4fe-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ae4fe-117">&</span><span class="sxs-lookup"><span data-stu-id="ae4fe-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="ae4fe-118">解説</span><span class="sxs-lookup"><span data-stu-id="ae4fe-118">Remarks</span></span>

<span data-ttu-id="ae4fe-119">の値は、リトルエン `numberState` ディアンエンコーディングを使用して解釈されます。</span><span class="sxs-lookup"><span data-stu-id="ae4fe-119">The value of `numberState` is interpreted using a little-endian encoding.</span></span>

<span data-ttu-id="ae4fe-120">`numberState` は最大で $ 2 ^ \texttt{Length (controlRegister)}-$1 である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae4fe-120">`numberState` must be at most $2^\texttt{Length(controlRegister)} - 1$.</span></span>
<span data-ttu-id="ae4fe-121">たとえば、 `numberState = 537` `oracle` は、 `controlRegister` が $ \ket $ という状態にある場合にのみ適用されることを意味し {537} ます。</span><span class="sxs-lookup"><span data-stu-id="ae4fe-121">For example, `numberState = 537` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{537}$.</span></span>