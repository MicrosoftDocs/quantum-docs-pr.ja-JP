---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: Applycontrol/Int 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 499a25104742b2d03886065baad4d535ea92e83b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845101"
---
# <a name="applycontrolledonint-operation"></a><span data-ttu-id="3703f-102">Applycontrol/Int 操作</span><span class="sxs-lookup"><span data-stu-id="3703f-102">ApplyControlledOnInt operation</span></span>

<span data-ttu-id="3703f-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3703f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3703f-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3703f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3703f-105">コントロールの登録状態が指定した正の整数に対応する場合は、ターゲットレジスタに対して、値の指定操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="3703f-105">Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3703f-106">入力</span><span class="sxs-lookup"><span data-stu-id="3703f-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="3703f-107">数値の状態: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3703f-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3703f-108">操作を制御する必要がある負で `oracle` ない整数。</span><span class="sxs-lookup"><span data-stu-id="3703f-108">A nonnegative integer on which the operation `oracle` should be controlled.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="3703f-109">oracle: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="3703f-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="3703f-110">制御される、ユニタリ操作。</span><span class="sxs-lookup"><span data-stu-id="3703f-110">A unitary operation to be controlled.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="3703f-111">controlRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3703f-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3703f-112">のアプリケーションを制御するクォンタムレジスタ `oracle` 。</span><span class="sxs-lookup"><span data-stu-id="3703f-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="3703f-113">targetRegister: ' t '</span><span class="sxs-lookup"><span data-stu-id="3703f-113">targetRegister : 'T</span></span>

<span data-ttu-id="3703f-114">適用するレジスタ `oracle` 。</span><span class="sxs-lookup"><span data-stu-id="3703f-114">A register on which to apply `oracle`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3703f-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3703f-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3703f-116">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="3703f-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3703f-117">&</span><span class="sxs-lookup"><span data-stu-id="3703f-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="3703f-118">解説</span><span class="sxs-lookup"><span data-stu-id="3703f-118">Remarks</span></span>

<span data-ttu-id="3703f-119">の値は、リトルエン `numberState` ディアンエンコーディングを使用して解釈されます。</span><span class="sxs-lookup"><span data-stu-id="3703f-119">The value of `numberState` is interpreted using a little-endian encoding.</span></span>

<span data-ttu-id="3703f-120">`numberState` は最大で $ 2 ^ \texttt{Length (controlRegister)}-$1 である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3703f-120">`numberState` must be at most $2^\texttt{Length(controlRegister)} - 1$.</span></span>
<span data-ttu-id="3703f-121">たとえば、 `numberState = 537` `oracle` は、 `controlRegister` が $ \ket $ という状態にある場合にのみ適用されることを意味し {537} ます。</span><span class="sxs-lookup"><span data-stu-id="3703f-121">For example, `numberState = 537` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{537}$.</span></span>