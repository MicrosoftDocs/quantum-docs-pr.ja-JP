---
uid: Microsoft.Quantum.Canon.QFT
title: QFT 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: e5b40be6c86647205fe1c764b6b043272296a354
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715654"
---
# <a name="qft-operation"></a><span data-ttu-id="cd338-102">QFT 操作</span><span class="sxs-lookup"><span data-stu-id="cd338-102">QFT operation</span></span>

<span data-ttu-id="cd338-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cd338-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cd338-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cd338-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cd338-105">ビッグエンディアン表現に整数を含むクォンタムレジスタに対して、Quantum フーリエ変換を実行します。</span><span class="sxs-lookup"><span data-stu-id="cd338-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="cd338-106">入力</span><span class="sxs-lookup"><span data-stu-id="cd338-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="cd338-107">qs: [Bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="cd338-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="cd338-108">クォンタムのフーリエ変換が適用されるクォンタムレジスタ</span><span class="sxs-lookup"><span data-stu-id="cd338-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="cd338-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cd338-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cd338-110">解説</span><span class="sxs-lookup"><span data-stu-id="cd338-110">Remarks</span></span>

<span data-ttu-id="cd338-111">入力と出力はビッグエンディアンエンコーディングであると見なされます。</span><span class="sxs-lookup"><span data-stu-id="cd338-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd338-112">参照</span><span class="sxs-lookup"><span data-stu-id="cd338-112">See Also</span></span>

- [<span data-ttu-id="cd338-113">Microsoft. ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="cd338-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)