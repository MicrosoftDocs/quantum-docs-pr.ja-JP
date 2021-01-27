---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA
title: ApplyReversedOpBEA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 1759764947cdbd84a1db945296d441a13f13767e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843597"
---
# <a name="applyreversedopbea-operation"></a><span data-ttu-id="793a5-102">ApplyReversedOpBEA 操作</span><span class="sxs-lookup"><span data-stu-id="793a5-102">ApplyReversedOpBEA operation</span></span>

<span data-ttu-id="793a5-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="793a5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="793a5-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="793a5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="793a5-105">リトルエンディアン入力をリトルエンディアン形式で符号なし整数にエンコードする操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="793a5-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="793a5-106">入力</span><span class="sxs-lookup"><span data-stu-id="793a5-106">Input</span></span>

### <a name="op--bigendian--unit--is-adj"></a><span data-ttu-id="793a5-107">op: [bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [ユニット](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="793a5-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="793a5-108">ビッグエンディアンレジスタに対して動作する操作。</span><span class="sxs-lookup"><span data-stu-id="793a5-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="793a5-109">register: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="793a5-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="793a5-110">変換されるリトルエンディアンレジスタ。</span><span class="sxs-lookup"><span data-stu-id="793a5-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="793a5-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="793a5-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="793a5-112">参照</span><span class="sxs-lookup"><span data-stu-id="793a5-112">See Also</span></span>

- [<span data-ttu-id="793a5-113">ApplyReversedOpBE です。</span><span class="sxs-lookup"><span data-stu-id="793a5-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="793a5-114">ApplyReversedOpBEC です。</span><span class="sxs-lookup"><span data-stu-id="793a5-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="793a5-115">ApplyReversedOpBECA です。</span><span class="sxs-lookup"><span data-stu-id="793a5-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)