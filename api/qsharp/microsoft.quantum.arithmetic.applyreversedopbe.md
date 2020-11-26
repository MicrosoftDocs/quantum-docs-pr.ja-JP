---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBE
title: ApplyReversedOpBE 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBE
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 6db1fcb7437d97b1e56c64165d1be523ed2df07a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202857"
---
# <a name="applyreversedopbe-operation"></a><span data-ttu-id="b04c4-102">ApplyReversedOpBE 操作</span><span class="sxs-lookup"><span data-stu-id="b04c4-102">ApplyReversedOpBE operation</span></span>

<span data-ttu-id="b04c4-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b04c4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b04c4-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b04c4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b04c4-105">リトルエンディアン入力をリトルエンディアン形式で符号なし整数にエンコードする操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="b04c4-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="b04c4-106">入力</span><span class="sxs-lookup"><span data-stu-id="b04c4-106">Input</span></span>

### <a name="op--bigendian--unit"></a><span data-ttu-id="b04c4-107">op: [bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [ユニット](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b04c4-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="b04c4-108">ビッグエンディアンレジスタに対して動作する操作。</span><span class="sxs-lookup"><span data-stu-id="b04c4-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="b04c4-109">register: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b04c4-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b04c4-110">変換されるリトルエンディアンレジスタ。</span><span class="sxs-lookup"><span data-stu-id="b04c4-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b04c4-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b04c4-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="b04c4-112">参照</span><span class="sxs-lookup"><span data-stu-id="b04c4-112">See Also</span></span>

- [<span data-ttu-id="b04c4-113">ApplyReversedOpBEA です。</span><span class="sxs-lookup"><span data-stu-id="b04c4-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="b04c4-114">ApplyReversedOpBEC です。</span><span class="sxs-lookup"><span data-stu-id="b04c4-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="b04c4-115">ApplyReversedOpBECA です。</span><span class="sxs-lookup"><span data-stu-id="b04c4-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)