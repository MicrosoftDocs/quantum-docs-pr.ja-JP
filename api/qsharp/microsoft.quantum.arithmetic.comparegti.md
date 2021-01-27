---
uid: Microsoft.Quantum.Arithmetic.CompareGTI
title: CompareGTI 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTI
qsharp.summary: 'Wrapper for integer comparison: `result = x > y`.'
ms.openlocfilehash: e9c245fb7c0cf3a6b1b98eb01cd582c325917602
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843298"
---
# <a name="comparegti-operation"></a><span data-ttu-id="772b6-102">CompareGTI 操作</span><span class="sxs-lookup"><span data-stu-id="772b6-102">CompareGTI operation</span></span>

<span data-ttu-id="772b6-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="772b6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="772b6-104">パッケージ: [Microsoft. Quantum. 数値](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="772b6-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="772b6-105">整数比較の `result = x > y` ラッパー:</span><span class="sxs-lookup"><span data-stu-id="772b6-105">Wrapper for integer comparison: `result = x > y`.</span></span>

```qsharp
operation CompareGTI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="772b6-106">入力</span><span class="sxs-lookup"><span data-stu-id="772b6-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="772b6-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="772b6-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="772b6-108">最初の $n $-bit number</span><span class="sxs-lookup"><span data-stu-id="772b6-108">First $n$-bit number</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="772b6-109">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="772b6-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="772b6-110">2番目の $n $-bit number</span><span class="sxs-lookup"><span data-stu-id="772b6-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="772b6-111">結果: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="772b6-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="772b6-112">$X > y $ の場合は反転されます</span><span class="sxs-lookup"><span data-stu-id="772b6-112">Will be flipped if $x > y$</span></span>



## <a name="output--unit"></a><span data-ttu-id="772b6-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="772b6-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

