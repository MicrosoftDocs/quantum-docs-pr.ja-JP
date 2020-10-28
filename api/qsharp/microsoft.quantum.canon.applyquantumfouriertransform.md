---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransform
title: ApplyQuantumFourierTransform 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransform
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: fa8d135c0665f0a576229797d208b321ba0329a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717796"
---
# <a name="applyquantumfouriertransform-operation"></a><span data-ttu-id="92d3f-102">ApplyQuantumFourierTransform 操作</span><span class="sxs-lookup"><span data-stu-id="92d3f-102">ApplyQuantumFourierTransform operation</span></span>

<span data-ttu-id="92d3f-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="92d3f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="92d3f-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="92d3f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="92d3f-105">リトルエンディアン表現内の整数を含むクォンタムレジスタに対して、Quantum フーリエ変換を実行します。</span><span class="sxs-lookup"><span data-stu-id="92d3f-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransform (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="92d3f-106">入力</span><span class="sxs-lookup"><span data-stu-id="92d3f-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="92d3f-107">qs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="92d3f-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="92d3f-108">クォンタムのフーリエ変換が適用されるクォンタムレジスタ</span><span class="sxs-lookup"><span data-stu-id="92d3f-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="92d3f-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="92d3f-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="92d3f-110">解説</span><span class="sxs-lookup"><span data-stu-id="92d3f-110">Remarks</span></span>

<span data-ttu-id="92d3f-111">入力と出力は、リトルエンディアンエンコーディングであると見なされます。</span><span class="sxs-lookup"><span data-stu-id="92d3f-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="92d3f-112">参照</span><span class="sxs-lookup"><span data-stu-id="92d3f-112">See Also</span></span>

- [<span data-ttu-id="92d3f-113">Microsoft. ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="92d3f-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)