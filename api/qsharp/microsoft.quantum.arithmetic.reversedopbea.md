---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEA
title: ReversedOpBEA 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: b2418911e71c0b98e1a78247b2ae066887d89cd8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719695"
---
# <a name="reversedopbea-function"></a><span data-ttu-id="8d2f3-102">ReversedOpBEA 関数</span><span class="sxs-lookup"><span data-stu-id="8d2f3-102">ReversedOpBEA function</span></span>

<span data-ttu-id="8d2f3-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8d2f3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8d2f3-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8d2f3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8d2f3-105">ビッグエンディアン入力を受け取る操作が指定された場合、は、リトルエンディアン入力を受け取る新しい操作を返します。</span><span class="sxs-lookup"><span data-stu-id="8d2f3-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="8d2f3-106">入力</span><span class="sxs-lookup"><span data-stu-id="8d2f3-106">Input</span></span>

### <a name="op--bigendian--unit-adj"></a><span data-ttu-id="8d2f3-107">op: [bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [ユニット](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="8d2f3-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="8d2f3-108">入力を元に戻す操作。</span><span class="sxs-lookup"><span data-stu-id="8d2f3-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit-adj"></a><span data-ttu-id="8d2f3-109">出力: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="8d2f3-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="8d2f3-110">入力をリトルエンディアンレジスタとして受け入れる新しい操作。</span><span class="sxs-lookup"><span data-stu-id="8d2f3-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="8d2f3-111">参照</span><span class="sxs-lookup"><span data-stu-id="8d2f3-111">See Also</span></span>

- [<span data-ttu-id="8d2f3-112">ApplyReversedOpBEA です。</span><span class="sxs-lookup"><span data-stu-id="8d2f3-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="8d2f3-113">ReversedOpBE です。</span><span class="sxs-lookup"><span data-stu-id="8d2f3-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="8d2f3-114">ReversedOpBEC です。</span><span class="sxs-lookup"><span data-stu-id="8d2f3-114">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [<span data-ttu-id="8d2f3-115">ReversedOpBECA です。</span><span class="sxs-lookup"><span data-stu-id="8d2f3-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)