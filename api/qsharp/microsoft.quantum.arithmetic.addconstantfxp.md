---
uid: Microsoft.Quantum.Arithmetic.AddConstantFxP
title: AddConstantFxP 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddConstantFxP
qsharp.summary: Adds a classical constant to a quantum fixed-point number.
ms.openlocfilehash: fd985d1112298c3d2bbb0db2ff0d934098566e93
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843881"
---
# <a name="addconstantfxp-operation"></a><span data-ttu-id="b7d3b-102">AddConstantFxP 操作</span><span class="sxs-lookup"><span data-stu-id="b7d3b-102">AddConstantFxP operation</span></span>

<span data-ttu-id="b7d3b-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b7d3b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b7d3b-104">パッケージ: [Microsoft. Quantum. 数値](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="b7d3b-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="b7d3b-105">クォンタム固定小数点数に古典定数を追加します。</span><span class="sxs-lookup"><span data-stu-id="b7d3b-105">Adds a classical constant to a quantum fixed-point number.</span></span>

```qsharp
operation AddConstantFxP (constant : Double, fp : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b7d3b-106">入力</span><span class="sxs-lookup"><span data-stu-id="b7d3b-106">Input</span></span>

### <a name="constant--double"></a><span data-ttu-id="b7d3b-107">定数: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b7d3b-107">constant : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b7d3b-108">クォンタム固定小数点数に追加する定数。</span><span class="sxs-lookup"><span data-stu-id="b7d3b-108">Constant to add to the quantum fixed-point number.</span></span>


### <a name="fp--fixedpoint"></a><span data-ttu-id="b7d3b-109">fp: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="b7d3b-109">fp : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="b7d3b-110">定数が加算される固定小数点数。</span><span class="sxs-lookup"><span data-stu-id="b7d3b-110">Fixed-point number to which the constant will be added.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b7d3b-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b7d3b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

