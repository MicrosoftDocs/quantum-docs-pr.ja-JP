---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA
title: ApplyReversedOpBEA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: f606011dd002d6eadc4f882005f4577aeb28cac0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721483"
---
# <a name="applyreversedopbea-operation"></a><span data-ttu-id="2ac4e-102">ApplyReversedOpBEA 操作</span><span class="sxs-lookup"><span data-stu-id="2ac4e-102">ApplyReversedOpBEA operation</span></span>

<span data-ttu-id="2ac4e-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2ac4e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2ac4e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2ac4e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2ac4e-105">リトルエンディアン入力をリトルエンディアン形式で符号なし整数にエンコードする操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="2ac4e-106">入力</span><span class="sxs-lookup"><span data-stu-id="2ac4e-106">Input</span></span>

### <a name="op--bigendian--unit-adj"></a><span data-ttu-id="2ac4e-107">op: [bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [ユニット](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="2ac4e-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="2ac4e-108">ビッグエンディアンレジスタに対して動作する操作。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="2ac4e-109">register: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2ac4e-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2ac4e-110">変換されるリトルエンディアンレジスタ。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2ac4e-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2ac4e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="2ac4e-112">参照</span><span class="sxs-lookup"><span data-stu-id="2ac4e-112">See Also</span></span>

- [<span data-ttu-id="2ac4e-113">ApplyReversedOpBE です。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="2ac4e-114">ApplyReversedOpBEC です。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="2ac4e-115">ApplyReversedOpBECA です。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)