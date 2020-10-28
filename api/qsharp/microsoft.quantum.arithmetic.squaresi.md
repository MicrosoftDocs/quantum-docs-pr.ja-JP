---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: SquareSI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: c8c4e3cca001aa6d7ce1b9df106ce77f74524301
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719534"
---
# <a name="squaresi-operation"></a><span data-ttu-id="53d5f-102">SquareSI 操作</span><span class="sxs-lookup"><span data-stu-id="53d5f-102">SquareSI operation</span></span>

<span data-ttu-id="53d5f-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="53d5f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="53d5f-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="53d5f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="53d5f-105">2乗符号付き整数 `xs` 。結果をに格納します `result` 。最初はゼロである必要があります。</span><span class="sxs-lookup"><span data-stu-id="53d5f-105">Square signed integer `xs` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="53d5f-106">入力</span><span class="sxs-lookup"><span data-stu-id="53d5f-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="53d5f-107">xs: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="53d5f-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="53d5f-108">n ビット整数から二乗 (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="53d5f-108">n-bit integer to square (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="53d5f-109">結果: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="53d5f-109">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="53d5f-110">2n ビット結果 (SignedLittleEndian) は、初期状態では $ \ket $ である必要があり {0} ます。</span><span class="sxs-lookup"><span data-stu-id="53d5f-110">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="53d5f-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="53d5f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="53d5f-112">解説</span><span class="sxs-lookup"><span data-stu-id="53d5f-112">Remarks</span></span>

<span data-ttu-id="53d5f-113">実装は、整数の平方根に依存します。</span><span class="sxs-lookup"><span data-stu-id="53d5f-113">The implementation relies on IntegerSquare.</span></span>