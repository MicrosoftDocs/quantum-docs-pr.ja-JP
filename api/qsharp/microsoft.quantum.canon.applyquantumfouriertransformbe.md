---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: ApplyQuantumFourierTransformBE 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: a1f4a0a5e94465fc8bf3af344e2e19ee0d1d15e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841563"
---
# <a name="applyquantumfouriertransformbe-operation"></a><span data-ttu-id="0a11b-102">ApplyQuantumFourierTransformBE 操作</span><span class="sxs-lookup"><span data-stu-id="0a11b-102">ApplyQuantumFourierTransformBE operation</span></span>

<span data-ttu-id="0a11b-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0a11b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0a11b-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0a11b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0a11b-105">ビッグエンディアン表現に整数を含むクォンタムレジスタに対して、Quantum フーリエ変換を実行します。</span><span class="sxs-lookup"><span data-stu-id="0a11b-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0a11b-106">入力</span><span class="sxs-lookup"><span data-stu-id="0a11b-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="0a11b-107">qs: [Bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="0a11b-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="0a11b-108">クォンタムのフーリエ変換が適用されるクォンタムレジスタ</span><span class="sxs-lookup"><span data-stu-id="0a11b-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="0a11b-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0a11b-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0a11b-110">解説</span><span class="sxs-lookup"><span data-stu-id="0a11b-110">Remarks</span></span>

<span data-ttu-id="0a11b-111">入力と出力はビッグエンディアンエンコーディングであると見なされます。</span><span class="sxs-lookup"><span data-stu-id="0a11b-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a11b-112">参照</span><span class="sxs-lookup"><span data-stu-id="0a11b-112">See Also</span></span>

- [<span data-ttu-id="0a11b-113">Microsoft. ApproximateQFT</span><span class="sxs-lookup"><span data-stu-id="0a11b-113">Microsoft.Quantum.Canon.ApproximateQFT</span></span>](xref:Microsoft.Quantum.Canon.ApproximateQFT)
- [<span data-ttu-id="0a11b-114">Microsoft. QFTLE</span><span class="sxs-lookup"><span data-stu-id="0a11b-114">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)