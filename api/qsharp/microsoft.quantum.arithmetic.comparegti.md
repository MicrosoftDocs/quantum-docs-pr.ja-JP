---
uid: Microsoft.Quantum.Arithmetic.CompareGTI
title: CompareGTI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTI
qsharp.summary: 'Wrapper for integer comparison: `result = x > y`.'
ms.openlocfilehash: c60c2827060f4ef223ebaf80ccdef09faaf56098
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721286"
---
# <a name="comparegti-operation"></a><span data-ttu-id="df16a-102">CompareGTI 操作</span><span class="sxs-lookup"><span data-stu-id="df16a-102">CompareGTI operation</span></span>

<span data-ttu-id="df16a-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="df16a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="df16a-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="df16a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="df16a-105">整数比較の `result = x > y` ラッパー:</span><span class="sxs-lookup"><span data-stu-id="df16a-105">Wrapper for integer comparison: `result = x > y`.</span></span>

```qsharp
operation CompareGTI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="df16a-106">入力</span><span class="sxs-lookup"><span data-stu-id="df16a-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="df16a-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="df16a-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="df16a-108">最初の $n $-bit number</span><span class="sxs-lookup"><span data-stu-id="df16a-108">First $n$-bit number</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="df16a-109">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="df16a-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="df16a-110">2番目の $n $-bit number</span><span class="sxs-lookup"><span data-stu-id="df16a-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="df16a-111">結果: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="df16a-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="df16a-112">$X > y $ の場合は反転されます</span><span class="sxs-lookup"><span data-stu-id="df16a-112">Will be flipped if $x > y$</span></span>



## <a name="output--unit"></a><span data-ttu-id="df16a-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="df16a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
