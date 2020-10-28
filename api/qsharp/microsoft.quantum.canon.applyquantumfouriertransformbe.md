---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: ApplyQuantumFourierTransformBE 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: d15310298dc138bdffb612895bbf20ca1371db6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717787"
---
# <a name="applyquantumfouriertransformbe-operation"></a><span data-ttu-id="d7606-102">ApplyQuantumFourierTransformBE 操作</span><span class="sxs-lookup"><span data-stu-id="d7606-102">ApplyQuantumFourierTransformBE operation</span></span>

<span data-ttu-id="d7606-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d7606-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d7606-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d7606-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d7606-105">ビッグエンディアン表現に整数を含むクォンタムレジスタに対して、Quantum フーリエ変換を実行します。</span><span class="sxs-lookup"><span data-stu-id="d7606-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="d7606-106">入力</span><span class="sxs-lookup"><span data-stu-id="d7606-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="d7606-107">qs: [Bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="d7606-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="d7606-108">クォンタムのフーリエ変換が適用されるクォンタムレジスタ</span><span class="sxs-lookup"><span data-stu-id="d7606-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="d7606-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d7606-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d7606-110">解説</span><span class="sxs-lookup"><span data-stu-id="d7606-110">Remarks</span></span>

<span data-ttu-id="d7606-111">入力と出力はビッグエンディアンエンコーディングであると見なされます。</span><span class="sxs-lookup"><span data-stu-id="d7606-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7606-112">参照</span><span class="sxs-lookup"><span data-stu-id="d7606-112">See Also</span></span>

- [<span data-ttu-id="d7606-113">Microsoft. ApproximateQFT</span><span class="sxs-lookup"><span data-stu-id="d7606-113">Microsoft.Quantum.Canon.ApproximateQFT</span></span>](xref:Microsoft.Quantum.Canon.ApproximateQFT)
- [<span data-ttu-id="d7606-114">Microsoft. QFTLE</span><span class="sxs-lookup"><span data-stu-id="d7606-114">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)