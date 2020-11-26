---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLE
title: ApplyReversedOpLE 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLE
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: 16ce6842cdef8e519a13a45640edc3d79cdbce25
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202755"
---
# <a name="applyreversedople-operation"></a><span data-ttu-id="b388b-102">ApplyReversedOpLE 操作</span><span class="sxs-lookup"><span data-stu-id="b388b-102">ApplyReversedOpLE operation</span></span>

<span data-ttu-id="b388b-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b388b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b388b-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b388b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b388b-105">ビッグエンディアン形式を使用して符号なし整数をエンコーディングするレジスタに、リトルエンディアン入力を受け取る操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="b388b-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="b388b-106">入力</span><span class="sxs-lookup"><span data-stu-id="b388b-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="b388b-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b388b-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="b388b-108">リトルエンディアンレジスタに対して動作する操作。</span><span class="sxs-lookup"><span data-stu-id="b388b-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="b388b-109">register: [Bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="b388b-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="b388b-110">変換されるビッグエンディアンレジスタ。</span><span class="sxs-lookup"><span data-stu-id="b388b-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b388b-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b388b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="b388b-112">参照</span><span class="sxs-lookup"><span data-stu-id="b388b-112">See Also</span></span>

- [<span data-ttu-id="b388b-113">ApplyReversedOpLEA です。</span><span class="sxs-lookup"><span data-stu-id="b388b-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="b388b-114">ApplyReversedOpLEC です。</span><span class="sxs-lookup"><span data-stu-id="b388b-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="b388b-115">ApplyReversedOpLECA です。</span><span class="sxs-lookup"><span data-stu-id="b388b-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)