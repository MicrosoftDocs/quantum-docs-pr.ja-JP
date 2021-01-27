---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterTTKAdder
title: ApplyOuterTTKAdder 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterTTKAdder
qsharp.summary: Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.
ms.openlocfilehash: afcc3085965907b7478b513028e25d1813cf7b76
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843699"
---
# <a name="applyouterttkadder-operation"></a><span data-ttu-id="3ea73-102">ApplyOuterTTKAdder 操作</span><span class="sxs-lookup"><span data-stu-id="3ea73-102">ApplyOuterTTKAdder operation</span></span>

<span data-ttu-id="3ea73-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3ea73-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3ea73-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3ea73-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3ea73-105">RippleCarryAdderTTK の外部操作を実装して、完全なを作成するための内部操作を共役します。</span><span class="sxs-lookup"><span data-stu-id="3ea73-105">Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.</span></span>

```qsharp
operation ApplyOuterTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3ea73-106">入力</span><span class="sxs-lookup"><span data-stu-id="3ea73-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="3ea73-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3ea73-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3ea73-108">LittleEndian qubit レジスタは、最初の整数 summand 入力を RippleCarryAdderTTK にエンコードします。</span><span class="sxs-lookup"><span data-stu-id="3ea73-108">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="3ea73-109">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3ea73-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3ea73-110">LittleEndian qubit レジスタは、2番目の整数 summand 入力を RippleCarryAdderTTK にエンコードします。</span><span class="sxs-lookup"><span data-stu-id="3ea73-110">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3ea73-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3ea73-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="3ea73-112">References</span><span class="sxs-lookup"><span data-stu-id="3ea73-112">References</span></span>

- <span data-ttu-id="3ea73-113">Yasuhiro Takahashi、Seiichiro Tani、Noboru Kunihiro: "クォンタムの追加回路と無制限のファンアウト"、クォンタムの情報と計算、Vol. 10、2010。</span><span class="sxs-lookup"><span data-stu-id="3ea73-113">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530