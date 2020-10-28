---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC
title: ApplyReversedOpLEC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLEC
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: ac9a6000140445a457a9abc46d5143dcb089883e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721447"
---
# <a name="applyreversedoplec-operation"></a><span data-ttu-id="a6a6c-102">ApplyReversedOpLEC 操作</span><span class="sxs-lookup"><span data-stu-id="a6a6c-102">ApplyReversedOpLEC operation</span></span>

<span data-ttu-id="a6a6c-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a6a6c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a6a6c-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a6a6c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a6a6c-105">ビッグエンディアン形式を使用して符号なし整数をエンコーディングするレジスタに、リトルエンディアン入力を受け取る操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="a6a6c-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="a6a6c-106">入力</span><span class="sxs-lookup"><span data-stu-id="a6a6c-106">Input</span></span>

### <a name="op--littleendian--unit-ctl"></a><span data-ttu-id="a6a6c-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="a6a6c-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="a6a6c-108">リトルエンディアンレジスタに対して動作する操作。</span><span class="sxs-lookup"><span data-stu-id="a6a6c-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="a6a6c-109">register: [Bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="a6a6c-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="a6a6c-110">変換されるビッグエンディアンレジスタ。</span><span class="sxs-lookup"><span data-stu-id="a6a6c-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a6a6c-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a6a6c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="a6a6c-112">参照</span><span class="sxs-lookup"><span data-stu-id="a6a6c-112">See Also</span></span>

- [<span data-ttu-id="a6a6c-113">ApplyReversedOpLE です。</span><span class="sxs-lookup"><span data-stu-id="a6a6c-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="a6a6c-114">ApplyReversedOpLEA です。</span><span class="sxs-lookup"><span data-stu-id="a6a6c-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="a6a6c-115">ApplyReversedOpLECA です。</span><span class="sxs-lookup"><span data-stu-id="a6a6c-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)