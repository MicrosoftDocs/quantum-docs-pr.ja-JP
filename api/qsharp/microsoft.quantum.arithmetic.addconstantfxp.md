---
uid: Microsoft.Quantum.Arithmetic.AddConstantFxP
title: AddConstantFxP 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddConstantFxP
qsharp.summary: Adds a classical constant to a quantum fixed-point number.
ms.openlocfilehash: f6cbdb9ecf316c882dc712749d2d4203136e0070
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191093"
---
# <a name="addconstantfxp-operation"></a><span data-ttu-id="62e0a-102">AddConstantFxP 操作</span><span class="sxs-lookup"><span data-stu-id="62e0a-102">AddConstantFxP operation</span></span>

<span data-ttu-id="62e0a-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="62e0a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="62e0a-104">パッケージ: [Microsoft. Quantum. 数値](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="62e0a-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="62e0a-105">クォンタム固定小数点数に古典定数を追加します。</span><span class="sxs-lookup"><span data-stu-id="62e0a-105">Adds a classical constant to a quantum fixed-point number.</span></span>

```qsharp
operation AddConstantFxP (constant : Double, fp : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="62e0a-106">入力</span><span class="sxs-lookup"><span data-stu-id="62e0a-106">Input</span></span>

### <a name="constant--double"></a><span data-ttu-id="62e0a-107">定数: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="62e0a-107">constant : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="62e0a-108">クォンタム固定小数点数に追加する定数。</span><span class="sxs-lookup"><span data-stu-id="62e0a-108">Constant to add to the quantum fixed-point number.</span></span>


### <a name="fp--fixedpoint"></a><span data-ttu-id="62e0a-109">fp: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="62e0a-109">fp : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="62e0a-110">定数が加算される固定小数点数。</span><span class="sxs-lookup"><span data-stu-id="62e0a-110">Fixed-point number to which the constant will be added.</span></span>



## <a name="output--unit"></a><span data-ttu-id="62e0a-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="62e0a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

