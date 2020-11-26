---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: Control/Bitstring 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: 9435406506fc99fe211f5dce628b21c18ee4f9fe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216661"
---
# <a name="controlledonbitstring-function"></a><span data-ttu-id="6794f-102">Control/Bitstring 関数</span><span class="sxs-lookup"><span data-stu-id="6794f-102">ControlledOnBitString function</span></span>

<span data-ttu-id="6794f-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6794f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6794f-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6794f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6794f-105">制御レジスタの状態が指定したビットマスクに対応する場合に、ターゲットレジスタに oracle を適用する、ユニタリ操作を返します。</span><span class="sxs-lookup"><span data-stu-id="6794f-105">Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.</span></span>

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="6794f-106">説明</span><span class="sxs-lookup"><span data-stu-id="6794f-106">Description</span></span>

<span data-ttu-id="6794f-107">この関数の出力は、\begin{align} U \ket{b_0 b_1/cドット b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \ cドット b_ {n-1}} という $U の、単位の変換で表すことができる演算です。 \ otimes \begin{cases} V \ket{\psi} & \t extrm{if} (b_0 b_1 \ cドット b_ {n-1}) = \texttt{bits} \\ \\ \ket{\psi} & \textrm{otherwise} \end{cases}, \end{align} ここで $V $ は、操作のアクションを表すミリ秒変換です `oracle` 。</span><span class="sxs-lookup"><span data-stu-id="6794f-107">The output of this function is an operation that can be represented by a unitary transformation $U$ such that \begin{align} U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes \begin{cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\ \ket{\psi} & \textrm{otherwise} \end{cases}, \end{align} where $V$ is a unitary transformation that represents the action of the `oracle` operation.</span></span>

## <a name="input"></a><span data-ttu-id="6794f-108">入力</span><span class="sxs-lookup"><span data-stu-id="6794f-108">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="6794f-109">bits: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="6794f-109">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="6794f-110">指定されたユニタリ操作を制御するビット文字列。</span><span class="sxs-lookup"><span data-stu-id="6794f-110">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="6794f-111">oracle: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="6794f-111">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="6794f-112">ターゲットレジスタに適用されるユニタリ操作。</span><span class="sxs-lookup"><span data-stu-id="6794f-112">The unitary operation to be applied on the target register.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="6794f-113">出力: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[], ' t) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="6794f-113">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="6794f-114">`oracle`コントロールのレジスタの状態がビットマスクに対応している場合に、ターゲットのレジスタに適用されるユニタリ操作 `bits` 。</span><span class="sxs-lookup"><span data-stu-id="6794f-114">A unitary operation that applies `oracle` on the target register if the control register state corresponds to the bit mask `bits`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6794f-115">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="6794f-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6794f-116">&</span><span class="sxs-lookup"><span data-stu-id="6794f-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="6794f-117">解説</span><span class="sxs-lookup"><span data-stu-id="6794f-117">Remarks</span></span>

<span data-ttu-id="6794f-118">によって指定されたパターンは `bits` よりも短い場合があります `controlRegister` 。この場合、追加の制御 qubits は無視されます (つまり、$ \ket $ と $ \ket $ で制御されません {0} {1} )。</span><span class="sxs-lookup"><span data-stu-id="6794f-118">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="6794f-119">`bits`がより長い場合は `controlRegister` 、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="6794f-119">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="6794f-120">ブール型の配列と1つの値を指定する `bits` と、 `oracle` この関数の出力は、次の手順を実行する操作になります。</span><span class="sxs-lookup"><span data-stu-id="6794f-120">Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function is an operation that performs the following steps:</span></span>

* <span data-ttu-id="6794f-121">`X`の要素に対応する制御レジスタの各 qubit に操作を適用 `false` し `bits` ます。</span><span class="sxs-lookup"><span data-stu-id="6794f-121">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits`;</span></span>
* <span data-ttu-id="6794f-122">`Controlled oracle`コントロールとターゲットレジスタに適用します。</span><span class="sxs-lookup"><span data-stu-id="6794f-122">apply `Controlled oracle` to the control and target registers;</span></span>
* <span data-ttu-id="6794f-123">コントロールレジスタを `X` `false` `bits` 元の状態に戻すために、の要素に対応する各 qubit に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="6794f-123">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits` again to return the control register to the original state.</span></span>

<span data-ttu-id="6794f-124">ファンクタの出力 `Controlled` は、 `ControlledOnBitString` `bits` がと等しい特殊なケースです `[true, ..., true]` 。</span><span class="sxs-lookup"><span data-stu-id="6794f-124">The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.</span></span>