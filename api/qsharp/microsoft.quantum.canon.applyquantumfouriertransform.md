---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransform
title: ApplyQuantumFourierTransform 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransform
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: d99000c21c79d2ca97b1fe92ad331c7ba8599700
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844758"
---
# <a name="applyquantumfouriertransform-operation"></a><span data-ttu-id="54eab-102">ApplyQuantumFourierTransform 操作</span><span class="sxs-lookup"><span data-stu-id="54eab-102">ApplyQuantumFourierTransform operation</span></span>

<span data-ttu-id="54eab-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="54eab-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="54eab-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="54eab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="54eab-105">リトルエンディアン表現内の整数を含むクォンタムレジスタに対して、Quantum フーリエ変換を実行します。</span><span class="sxs-lookup"><span data-stu-id="54eab-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransform (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="54eab-106">入力</span><span class="sxs-lookup"><span data-stu-id="54eab-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="54eab-107">qs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="54eab-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="54eab-108">クォンタムのフーリエ変換が適用されるクォンタムレジスタ</span><span class="sxs-lookup"><span data-stu-id="54eab-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="54eab-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="54eab-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="54eab-110">解説</span><span class="sxs-lookup"><span data-stu-id="54eab-110">Remarks</span></span>

<span data-ttu-id="54eab-111">入力と出力は、リトルエンディアンエンコーディングであると見なされます。</span><span class="sxs-lookup"><span data-stu-id="54eab-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="54eab-112">参照</span><span class="sxs-lookup"><span data-stu-id="54eab-112">See Also</span></span>

- [<span data-ttu-id="54eab-113">Microsoft. ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="54eab-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)