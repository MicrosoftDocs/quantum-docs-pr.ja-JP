---
uid: Microsoft.Quantum.Arithmetic.MultiplySI
title: 乗数 Ysi 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplySI
qsharp.summary: Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 4e7f43f88654f10ece4f9c30c5bfde9a779b18ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222441"
---
# <a name="multiplysi-operation"></a><span data-ttu-id="c9b69-102">乗数 Ysi 操作</span><span class="sxs-lookup"><span data-stu-id="c9b69-102">MultiplySI operation</span></span>

<span data-ttu-id="c9b69-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c9b69-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c9b69-104">パッケージ: [Microsoft. Quantum. 数値](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="c9b69-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="c9b69-105">符号付き整数 `xs` を符号付き整数で乗算 `ys` し、結果をに格納し `result` ます。最初はゼロである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9b69-105">Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplySI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c9b69-106">入力</span><span class="sxs-lookup"><span data-stu-id="c9b69-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="c9b69-107">xs: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c9b69-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="c9b69-108">n ビット被乗数 (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c9b69-108">n-bit multiplicand (SignedLittleEndian)</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="c9b69-109">y: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c9b69-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="c9b69-110">n ビット乗数 (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c9b69-110">n-bit multiplier (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="c9b69-111">結果: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c9b69-111">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="c9b69-112">2n ビット結果 (SignedLittleEndian) は、初期状態では $ \ket $ である必要があり {0} ます。</span><span class="sxs-lookup"><span data-stu-id="c9b69-112">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c9b69-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c9b69-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

