---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: CompareGTSI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: 735ae21168d8efb3e626a8f1ea36e97f5cdf8760
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721279"
---
# <a name="comparegtsi-operation"></a><span data-ttu-id="8c980-102">CompareGTSI 操作</span><span class="sxs-lookup"><span data-stu-id="8c980-102">CompareGTSI operation</span></span>

<span data-ttu-id="8c980-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8c980-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8c980-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8c980-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8c980-105">符号付き整数比較のラッパー: `result = xs > ys` 。</span><span class="sxs-lookup"><span data-stu-id="8c980-105">Wrapper for signed integer comparison: `result = xs > ys`.</span></span>

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="8c980-106">入力</span><span class="sxs-lookup"><span data-stu-id="8c980-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="8c980-107">xs: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8c980-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="8c980-108">最初の $n $-bit number</span><span class="sxs-lookup"><span data-stu-id="8c980-108">First $n$-bit number</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="8c980-109">y: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8c980-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="8c980-110">2番目の $n $-bit number</span><span class="sxs-lookup"><span data-stu-id="8c980-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="8c980-111">結果: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8c980-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8c980-112">$Xs > y $ の場合は、反転されます</span><span class="sxs-lookup"><span data-stu-id="8c980-112">Will be flipped if $xs > ys$</span></span>



## <a name="output--unit"></a><span data-ttu-id="8c980-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8c980-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

