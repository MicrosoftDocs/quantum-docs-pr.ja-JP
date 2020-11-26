---
uid: Microsoft.Quantum.Canon.MultiplexOperations
title: MultiplexOperations 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperations
qsharp.summary: >-
  Applies an array of operations controlled by an array of number states.

  That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: ad66b39fcfacbe5231ec3b9ba96989d6d5d449c1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206104"
---
# <a name="multiplexoperations-operation"></a><span data-ttu-id="b4b67-102">MultiplexOperations 操作</span><span class="sxs-lookup"><span data-stu-id="b4b67-102">MultiplexOperations operation</span></span>

<span data-ttu-id="b4b67-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b4b67-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b4b67-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b4b67-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b4b67-105">数値の状態の配列によって制御される操作の配列を適用します。</span><span class="sxs-lookup"><span data-stu-id="b4b67-105">Applies an array of operations controlled by an array of number states.</span></span>

<span data-ttu-id="b4b67-106">つまり、$n $-qubit 数値の状態 $ \ket{j} $ によって制御されている場合は、_j $ の $V によって $ に適用される、多重制御された $U $ に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b4b67-106">That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="b4b67-107">$U = \ sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $。</span><span class="sxs-lookup"><span data-stu-id="b4b67-107">$U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperations<'T> (unitaries : ('T => Unit is Adj + Ctl)[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b4b67-108">入力</span><span class="sxs-lookup"><span data-stu-id="b4b67-108">Input</span></span>

### <a name="unitaries--t--unit--is-adj--ctl"></a><span data-ttu-id="b4b67-109">unitaries: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl []</span><span class="sxs-lookup"><span data-stu-id="b4b67-109">unitaries : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="b4b67-110">最大 $ 2 ^ n $ のユニタリ操作の配列。</span><span class="sxs-lookup"><span data-stu-id="b4b67-110">Array of up to $2^n$ unitary operations.</span></span> <span data-ttu-id="b4b67-111">$J $ th 操作は、リトルエンディアン形式でエンコードされた数値の状態 $ \ket{j} $ によってインデックスが付けられます。</span><span class="sxs-lookup"><span data-stu-id="b4b67-111">The $j$th operation is indexed by the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="b4b67-112">index: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b4b67-112">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b4b67-113">数値の状態をリトルエンディアン形式でエンコードする $-qubit コントロールレジスタ $n ます。</span><span class="sxs-lookup"><span data-stu-id="b4b67-113">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="b4b67-114">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="b4b67-114">target : 'T</span></span>

<span data-ttu-id="b4b67-115">_J $ act に $V する汎用 qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="b4b67-115">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b4b67-116">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b4b67-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b4b67-117">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="b4b67-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b4b67-118">&</span><span class="sxs-lookup"><span data-stu-id="b4b67-118">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="b4b67-119">解説</span><span class="sxs-lookup"><span data-stu-id="b4b67-119">Remarks</span></span>

<span data-ttu-id="b4b67-120">`coefficients` $ 2 ^ n $ 未満の値が指定されている場合、id 要素が埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="b4b67-120">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="b4b67-121">この実装では、$n-$1 補助 qubits を使用します。</span><span class="sxs-lookup"><span data-stu-id="b4b67-121">This implementation uses $n - 1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="b4b67-122">リファレンス</span><span class="sxs-lookup"><span data-stu-id="b4b67-122">References</span></span>

- <span data-ttu-id="b4b67-123">クォンタムの速度を Childs、Dmitri Maslov、Yunseong、Neil、Ross、人民 Su を使用して最初のクォンタムシミュレーションに向けて https://arxiv.org/abs/1711.10980</span><span class="sxs-lookup"><span data-stu-id="b4b67-123">Toward the first quantum simulation with quantum speedup Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su https://arxiv.org/abs/1711.10980</span></span>