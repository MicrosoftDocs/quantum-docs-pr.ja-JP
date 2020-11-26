---
uid: Microsoft.Quantum.Arithmetic.CompareGTI
title: CompareGTI 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTI
qsharp.summary: 'Wrapper for integer comparison: `result = x > y`.'
ms.openlocfilehash: b6e82eb7e9c068eff5bb320bb797a8fb0f8f921b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223478"
---
# <a name="comparegti-operation"></a><span data-ttu-id="f7da7-102">CompareGTI 操作</span><span class="sxs-lookup"><span data-stu-id="f7da7-102">CompareGTI operation</span></span>

<span data-ttu-id="f7da7-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f7da7-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f7da7-104">パッケージ: [Microsoft. Quantum. 数値](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="f7da7-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="f7da7-105">整数比較の `result = x > y` ラッパー:</span><span class="sxs-lookup"><span data-stu-id="f7da7-105">Wrapper for integer comparison: `result = x > y`.</span></span>

```qsharp
operation CompareGTI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f7da7-106">入力</span><span class="sxs-lookup"><span data-stu-id="f7da7-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="f7da7-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f7da7-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f7da7-108">最初の $n $-bit number</span><span class="sxs-lookup"><span data-stu-id="f7da7-108">First $n$-bit number</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="f7da7-109">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f7da7-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f7da7-110">2番目の $n $-bit number</span><span class="sxs-lookup"><span data-stu-id="f7da7-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="f7da7-111">結果: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f7da7-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f7da7-112">$X > y $ の場合は反転されます</span><span class="sxs-lookup"><span data-stu-id="f7da7-112">Will be flipped if $x > y$</span></span>



## <a name="output--unit"></a><span data-ttu-id="f7da7-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f7da7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

