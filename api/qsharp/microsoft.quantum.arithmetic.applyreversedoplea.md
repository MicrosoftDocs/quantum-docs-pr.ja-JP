---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA
title: ApplyReversedOpLEA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLEA
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: d5bc1b38500c449b58f8dafd640627b8e933e902
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202738"
---
# <a name="applyreversedoplea-operation"></a><span data-ttu-id="adfb6-102">ApplyReversedOpLEA 操作</span><span class="sxs-lookup"><span data-stu-id="adfb6-102">ApplyReversedOpLEA operation</span></span>

<span data-ttu-id="adfb6-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="adfb6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="adfb6-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="adfb6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="adfb6-105">ビッグエンディアン形式を使用して符号なし整数をエンコーディングするレジスタに、リトルエンディアン入力を受け取る操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="adfb6-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="adfb6-106">入力</span><span class="sxs-lookup"><span data-stu-id="adfb6-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj"></a><span data-ttu-id="adfb6-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="adfb6-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="adfb6-108">リトルエンディアンレジスタに対して動作する操作。</span><span class="sxs-lookup"><span data-stu-id="adfb6-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="adfb6-109">register: [Bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="adfb6-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="adfb6-110">変換されるビッグエンディアンレジスタ。</span><span class="sxs-lookup"><span data-stu-id="adfb6-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="adfb6-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="adfb6-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="adfb6-112">参照</span><span class="sxs-lookup"><span data-stu-id="adfb6-112">See Also</span></span>

- [<span data-ttu-id="adfb6-113">ApplyReversedOpLE です。</span><span class="sxs-lookup"><span data-stu-id="adfb6-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="adfb6-114">ApplyReversedOpLEC です。</span><span class="sxs-lookup"><span data-stu-id="adfb6-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="adfb6-115">ApplyReversedOpLECA です。</span><span class="sxs-lookup"><span data-stu-id="adfb6-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)