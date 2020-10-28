---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdder
title: ApplyInnerTTKAdder 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdder
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 23c1f6dcdf3894cf1b416efd922c9eed01ac8f85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721658"
---
# <a name="applyinnerttkadder-operation"></a><span data-ttu-id="0f240-102">ApplyInnerTTKAdder 操作</span><span class="sxs-lookup"><span data-stu-id="0f240-102">ApplyInnerTTKAdder operation</span></span>

<span data-ttu-id="0f240-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0f240-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0f240-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0f240-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0f240-105">操作 RippleCarryAdderTTK の内部加算関数を実装します。</span><span class="sxs-lookup"><span data-stu-id="0f240-105">Implements the inner addition function for the operation RippleCarryAdderTTK.</span></span> <span data-ttu-id="0f240-106">これは、完全な conjugated を構築するために外部操作と共に使用される内部操作です。</span><span class="sxs-lookup"><span data-stu-id="0f240-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="0f240-107">入力</span><span class="sxs-lookup"><span data-stu-id="0f240-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="0f240-108">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0f240-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0f240-109">LittleEndian qubit レジスタは、最初の整数 summand 入力を RippleCarryAdderTTK にエンコードします。</span><span class="sxs-lookup"><span data-stu-id="0f240-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="0f240-110">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0f240-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0f240-111">LittleEndian qubit レジスタは、2番目の整数 summand 入力を RippleCarryAdderTTK にエンコードします。</span><span class="sxs-lookup"><span data-stu-id="0f240-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="0f240-112">キャリー: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0f240-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0f240-113">キャリー qubit, は、合計の最上位ビットを xor しています。</span><span class="sxs-lookup"><span data-stu-id="0f240-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0f240-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f240-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0f240-115">解説</span><span class="sxs-lookup"><span data-stu-id="0f240-115">Remarks</span></span>

<span data-ttu-id="0f240-116">指定された制御操作は、操作の対称および相互キャンセルを利用して、すべての操作にコントロールを追加する既定の実装を改善します。</span><span class="sxs-lookup"><span data-stu-id="0f240-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="0f240-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f240-117">References</span></span>

- <span data-ttu-id="0f240-118">Yasuhiro Takahashi、Seiichiro Tani、Noboru Kunihiro: "クォンタムの追加回路と無制限のファンアウト"、クォンタムの情報と計算、Vol. 10、2010。</span><span class="sxs-lookup"><span data-stu-id="0f240-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530