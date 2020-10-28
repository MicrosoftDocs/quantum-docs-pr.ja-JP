---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: Control/Bitstring 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: ca5a6e116eff187060f7a160e42836b170f0362d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716443"
---
# <a name="controlledonbitstring-function"></a><span data-ttu-id="318a8-102">Control/Bitstring 関数</span><span class="sxs-lookup"><span data-stu-id="318a8-102">ControlledOnBitString function</span></span>

<span data-ttu-id="318a8-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="318a8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="318a8-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="318a8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="318a8-105">制御レジスタの状態が指定したビットマスクに対応する場合に、ターゲットレジスタに oracle を適用する、ユニタリ操作を返します。</span><span class="sxs-lookup"><span data-stu-id="318a8-105">Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.</span></span>

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="318a8-106">説明</span><span class="sxs-lookup"><span data-stu-id="318a8-106">Description</span></span>

<span data-ttu-id="318a8-107">この関数の出力は、\begin{align} U \ket{b_0 b_1/cドット b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \ cドット b_ {n-1}} という $U の、単位の変換で表すことができる演算です。 \ otimes \begin{cases} V \ket{\psi} & \t extrm{if} (b_0 b_1 \ cドット b_ {n-1}) = \texttt{bits} \\ \\ \ket{\psi} & \textrm{otherwise} \end{cases}, \end{align} ここで $V $ は、操作のアクションを表すミリ秒変換です `oracle` 。</span><span class="sxs-lookup"><span data-stu-id="318a8-107">The output of this function is an operation that can be represented by a unitary transformation $U$ such that \begin{align} U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes \begin{cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\ \ket{\psi} & \textrm{otherwise} \end{cases}, \end{align} where $V$ is a unitary transformation that represents the action of the `oracle` operation.</span></span>

## <a name="input"></a><span data-ttu-id="318a8-108">入力</span><span class="sxs-lookup"><span data-stu-id="318a8-108">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="318a8-109">bits: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="318a8-109">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="318a8-110">指定されたユニタリ操作を制御するビット文字列。</span><span class="sxs-lookup"><span data-stu-id="318a8-110">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="318a8-111">oracle: t => [ユニット](xref:microsoft.quantum.lang-ref.unit) の調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="318a8-111">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="318a8-112">ターゲットレジスタに適用されるユニタリ操作。</span><span class="sxs-lookup"><span data-stu-id="318a8-112">The unitary operation to be applied on the target register.</span></span>



## <a name="output--qubitt--unit-adj--ctl"></a><span data-ttu-id="318a8-113">出力: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[], ' t) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="318a8-113">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="318a8-114">`oracle`コントロールのレジスタの状態がビットマスクに対応している場合に、ターゲットのレジスタに適用されるユニタリ操作 `bits` 。</span><span class="sxs-lookup"><span data-stu-id="318a8-114">A unitary operation that applies `oracle` on the target register if the control register state corresponds to the bit mask `bits`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="318a8-115">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="318a8-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="318a8-116">&</span><span class="sxs-lookup"><span data-stu-id="318a8-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="318a8-117">解説</span><span class="sxs-lookup"><span data-stu-id="318a8-117">Remarks</span></span>

<span data-ttu-id="318a8-118">によって指定されたパターンは `bits` よりも短い場合があります `controlRegister` 。この場合、追加の制御 qubits は無視されます (つまり、$ \ket $ と $ \ket $ で制御されません {0} {1} )。</span><span class="sxs-lookup"><span data-stu-id="318a8-118">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="318a8-119">`bits`がより長い場合は `controlRegister` 、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="318a8-119">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="318a8-120">ブール型の配列と1つの値を指定する `bits` と、 `oracle` この関数の出力は、次の手順を実行する操作になります。</span><span class="sxs-lookup"><span data-stu-id="318a8-120">Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function is an operation that performs the following steps:</span></span>

* <span data-ttu-id="318a8-121">`X`の要素に対応する制御レジスタの各 qubit に操作を適用 `false` し `bits` ます。</span><span class="sxs-lookup"><span data-stu-id="318a8-121">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits`;</span></span>
* <span data-ttu-id="318a8-122">`Controlled oracle`コントロールとターゲットレジスタに適用します。</span><span class="sxs-lookup"><span data-stu-id="318a8-122">apply `Controlled oracle` to the control and target registers;</span></span>
* <span data-ttu-id="318a8-123">コントロールレジスタを `X` `false` `bits` 元の状態に戻すために、の要素に対応する各 qubit に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="318a8-123">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits` again to return the control register to the original state.</span></span>

<span data-ttu-id="318a8-124">ファンクタの出力 `Controlled` は、 `ControlledOnBitString` `bits` がと等しい特殊なケースです `[true, ..., true]` 。</span><span class="sxs-lookup"><span data-stu-id="318a8-124">The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.</span></span>