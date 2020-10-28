---
uid: Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator
title: MultiplexOperationsFromGenerator 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsFromGenerator
qsharp.summary: >-
  Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 2fde0bf391568f39128e6dca4b535aa6b78407c2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715799"
---
# <a name="multiplexoperationsfromgenerator-operation"></a><span data-ttu-id="42e6d-102">MultiplexOperationsFromGenerator 操作</span><span class="sxs-lookup"><span data-stu-id="42e6d-102">MultiplexOperationsFromGenerator operation</span></span>

<span data-ttu-id="42e6d-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="42e6d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="42e6d-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="42e6d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="42e6d-105">N-qubit number 状態 $ \ket{j} $ によって制御されている場合に、_j $ の $V を適用する $U $ に、乗算によって制御される数値演算を適用します。</span><span class="sxs-lookup"><span data-stu-id="42e6d-105">Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="42e6d-106">$U = \ sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $。</span><span class="sxs-lookup"><span data-stu-id="42e6d-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperationsFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="42e6d-107">入力</span><span class="sxs-lookup"><span data-stu-id="42e6d-107">Input</span></span>

### <a name="unitarygenerator--intint---t--unit-adj--ctl"></a><span data-ttu-id="42e6d-108">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl)</span><span class="sxs-lookup"><span data-stu-id="42e6d-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>

<span data-ttu-id="42e6d-109">1番目の要素 `Int` が unitaries $ の数で、2番目の要素 `(Int -> ('T => () is Adj + Ctl))` が $ [0, n-1] $ の $ $j 整数を取得して、_j $ の $V の型指定操作を出力する関数です。</span><span class="sxs-lookup"><span data-stu-id="42e6d-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="42e6d-110">index: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="42e6d-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="42e6d-111">数値の状態をリトルエンディアン形式でエンコードする $-qubit コントロールレジスタ $n ます。</span><span class="sxs-lookup"><span data-stu-id="42e6d-111">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="42e6d-112">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="42e6d-112">target : 'T</span></span>

<span data-ttu-id="42e6d-113">_J $ act に $V する汎用 qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="42e6d-113">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="42e6d-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="42e6d-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="42e6d-115">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="42e6d-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="42e6d-116">&</span><span class="sxs-lookup"><span data-stu-id="42e6d-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="42e6d-117">解説</span><span class="sxs-lookup"><span data-stu-id="42e6d-117">Remarks</span></span>

<span data-ttu-id="42e6d-118">`coefficients` $ 2 ^ n $ 未満の値が指定されている場合、id 要素が埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="42e6d-118">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="42e6d-119">この実装では、$n-$1 補助 qubits を使用します。</span><span class="sxs-lookup"><span data-stu-id="42e6d-119">This implementation uses $n-1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="42e6d-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="42e6d-120">References</span></span>

- [<span data-ttu-id="42e6d-121">*Andrew m. Childs、Dmitri Maslov、Yunseong、Neil、Ross、人民 Su* 、arxiv: 1711.10980</span><span class="sxs-lookup"><span data-stu-id="42e6d-121"> *Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su* , arXiv:1711.10980</span></span>](https://arxiv.org/abs/1711.10980)