---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: Applycontrol/Bitstring 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 7a054511bacff574e6f7e889ace048c78886cf91
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718358"
---
# <a name="applycontrolledonbitstring-operation"></a><span data-ttu-id="2d621-102">Applycontrol/Bitstring 操作</span><span class="sxs-lookup"><span data-stu-id="2d621-102">ApplyControlledOnBitString operation</span></span>

<span data-ttu-id="2d621-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2d621-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2d621-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2d621-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2d621-105">ターゲットレジスタに対して、指定されたビットマスクによって指定された状態で制御される、一連の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="2d621-105">Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.</span></span>

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="2d621-106">入力</span><span class="sxs-lookup"><span data-stu-id="2d621-106">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="2d621-107">bits: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="2d621-107">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="2d621-108">指定されたユニタリ操作を制御するビット文字列。</span><span class="sxs-lookup"><span data-stu-id="2d621-108">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="2d621-109">oracle: t => [ユニット](xref:microsoft.quantum.lang-ref.unit) の調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="2d621-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="2d621-110">ターゲットレジスタに適用されるユニタリ操作。</span><span class="sxs-lookup"><span data-stu-id="2d621-110">The unitary operation to be applied on the target register.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="2d621-111">controlRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2d621-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2d621-112">のアプリケーションを制御するクォンタムレジスタ `oracle` 。</span><span class="sxs-lookup"><span data-stu-id="2d621-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="2d621-113">targetRegister: ' t '</span><span class="sxs-lookup"><span data-stu-id="2d621-113">targetRegister : 'T</span></span>

<span data-ttu-id="2d621-114">入力としてに渡されるターゲットレジスタ `oracle` 。</span><span class="sxs-lookup"><span data-stu-id="2d621-114">The target register to be passed to `oracle` as an input.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2d621-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2d621-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2d621-116">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="2d621-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2d621-117">&</span><span class="sxs-lookup"><span data-stu-id="2d621-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="2d621-118">解説</span><span class="sxs-lookup"><span data-stu-id="2d621-118">Remarks</span></span>

<span data-ttu-id="2d621-119">によって指定されたパターンは `bits` よりも短い場合があります `controlRegister` 。この場合、追加の制御 qubits は無視されます (つまり、$ \ket $ と $ \ket $ で制御されません {0} {1} )。</span><span class="sxs-lookup"><span data-stu-id="2d621-119">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="2d621-120">`bits`がより長い場合は `controlRegister` 、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="2d621-120">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="2d621-121">たとえば、は、 `bits = [0,1,0,0,1]` `oracle` `controlRegister` が $ \ket {0} \ket {1} \ket {0} \ket \ket $ という状態である場合にのみ適用され {0} {1} ます。</span><span class="sxs-lookup"><span data-stu-id="2d621-121">For example, `bits = [0,1,0,0,1]` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{0}\ket{1}\ket{0}\ket{0}\ket{1}$.</span></span>