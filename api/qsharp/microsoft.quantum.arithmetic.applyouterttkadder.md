---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterTTKAdder
title: ApplyOuterTTKAdder 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterTTKAdder
qsharp.summary: Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.
ms.openlocfilehash: 3d6d7c3446075130e5a8ee93abbd27e617d50b3b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721562"
---
# <a name="applyouterttkadder-operation"></a><span data-ttu-id="313ac-102">ApplyOuterTTKAdder 操作</span><span class="sxs-lookup"><span data-stu-id="313ac-102">ApplyOuterTTKAdder operation</span></span>

<span data-ttu-id="313ac-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="313ac-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="313ac-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="313ac-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="313ac-105">RippleCarryAdderTTK の外部操作を実装して、完全なを作成するための内部操作を共役します。</span><span class="sxs-lookup"><span data-stu-id="313ac-105">Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.</span></span>

```qsharp
operation ApplyOuterTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="313ac-106">入力</span><span class="sxs-lookup"><span data-stu-id="313ac-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="313ac-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="313ac-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="313ac-108">LittleEndian qubit レジスタは、最初の整数 summand 入力を RippleCarryAdderTTK にエンコードします。</span><span class="sxs-lookup"><span data-stu-id="313ac-108">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="313ac-109">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="313ac-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="313ac-110">LittleEndian qubit レジスタは、2番目の整数 summand 入力を RippleCarryAdderTTK にエンコードします。</span><span class="sxs-lookup"><span data-stu-id="313ac-110">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="313ac-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="313ac-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="313ac-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="313ac-112">References</span></span>

- <span data-ttu-id="313ac-113">Yasuhiro Takahashi、Seiichiro Tani、Noboru Kunihiro: "クォンタムの追加回路と無制限のファンアウト"、クォンタムの情報と計算、Vol. 10、2010。</span><span class="sxs-lookup"><span data-stu-id="313ac-113">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530