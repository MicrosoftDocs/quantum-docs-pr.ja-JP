---
uid: Microsoft.Quantum.Canon.QFT
title: QFT 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: 30f475c3850c248b5af58db1e4aac3638c4c0471
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852289"
---
# <a name="qft-operation"></a><span data-ttu-id="0a1ba-102">QFT 操作</span><span class="sxs-lookup"><span data-stu-id="0a1ba-102">QFT operation</span></span>

<span data-ttu-id="0a1ba-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0a1ba-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0a1ba-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0a1ba-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0a1ba-105">ビッグエンディアン表現に整数を含むクォンタムレジスタに対して、Quantum フーリエ変換を実行します。</span><span class="sxs-lookup"><span data-stu-id="0a1ba-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0a1ba-106">入力</span><span class="sxs-lookup"><span data-stu-id="0a1ba-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="0a1ba-107">qs: [Bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="0a1ba-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="0a1ba-108">クォンタムのフーリエ変換が適用されるクォンタムレジスタ</span><span class="sxs-lookup"><span data-stu-id="0a1ba-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="0a1ba-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0a1ba-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0a1ba-110">解説</span><span class="sxs-lookup"><span data-stu-id="0a1ba-110">Remarks</span></span>

<span data-ttu-id="0a1ba-111">入力と出力はビッグエンディアンエンコーディングであると見なされます。</span><span class="sxs-lookup"><span data-stu-id="0a1ba-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a1ba-112">参照</span><span class="sxs-lookup"><span data-stu-id="0a1ba-112">See Also</span></span>

- [<span data-ttu-id="0a1ba-113">Microsoft. ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="0a1ba-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)