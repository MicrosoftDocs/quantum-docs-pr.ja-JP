---
uid: Microsoft.Quantum.Canon.MultiplexOperationsBruteForceFromGenerator
title: MultiplexOperationsBruteForceFromGenerator 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsBruteForceFromGenerator
qsharp.summary: >-
  Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 2a9bb083b121745bd556aac692d5dc85ffec3791
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715822"
---
# <a name="multiplexoperationsbruteforcefromgenerator-operation"></a><span data-ttu-id="058eb-102">MultiplexOperationsBruteForceFromGenerator 操作</span><span class="sxs-lookup"><span data-stu-id="058eb-102">MultiplexOperationsBruteForceFromGenerator operation</span></span>

<span data-ttu-id="058eb-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="058eb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="058eb-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="058eb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="058eb-105">N-qubit number 状態 $ \ket{j} $ によって制御されている場合に、_j $ $V を適用する $U $ に、乗算によって制御される数値演算を適用します。</span><span class="sxs-lookup"><span data-stu-id="058eb-105">Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="058eb-106">$U = \ sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $。</span><span class="sxs-lookup"><span data-stu-id="058eb-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperationsBruteForceFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="058eb-107">入力</span><span class="sxs-lookup"><span data-stu-id="058eb-107">Input</span></span>

### <a name="unitarygenerator--intint---t--unit-adj--ctl"></a><span data-ttu-id="058eb-108">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl)</span><span class="sxs-lookup"><span data-stu-id="058eb-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>

<span data-ttu-id="058eb-109">1番目の要素 `Int` が unitaries $ の数で、2番目の要素 `(Int -> ('T => () is Adj + Ctl))` が $ [0, n-1] $ の $ $j 整数を取得して、_j $ の $V の型指定操作を出力する関数です。</span><span class="sxs-lookup"><span data-stu-id="058eb-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="058eb-110">index: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="058eb-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="058eb-111">数値の状態をリトルエンディアン形式でエンコードする $-qubit コントロールレジスタ $n ます。</span><span class="sxs-lookup"><span data-stu-id="058eb-111">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="058eb-112">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="058eb-112">target : 'T</span></span>

<span data-ttu-id="058eb-113">_J $ act に $V する汎用 qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="058eb-113">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="058eb-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="058eb-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="058eb-115">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="058eb-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="058eb-116">&</span><span class="sxs-lookup"><span data-stu-id="058eb-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="058eb-117">解説</span><span class="sxs-lookup"><span data-stu-id="058eb-117">Remarks</span></span>

<span data-ttu-id="058eb-118">`coefficients` $ 2 ^ n $ 未満の値が指定されている場合、id 要素が埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="058eb-118">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="058eb-119">このバージョンは、n の制御されたユニタリ演算子によって直接実装されます。</span><span class="sxs-lookup"><span data-stu-id="058eb-119">This version is implemented directly by looping through n-controlled unitary operators.</span></span>