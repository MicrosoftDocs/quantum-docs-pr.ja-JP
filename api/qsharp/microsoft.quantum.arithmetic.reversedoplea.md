---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEA
title: ReversedOpLEA 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: eabeb8e068ef32cf6717efd6e818271a667b39b2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719642"
---
# <a name="reversedoplea-function"></a><span data-ttu-id="aaad8-102">ReversedOpLEA 関数</span><span class="sxs-lookup"><span data-stu-id="aaad8-102">ReversedOpLEA function</span></span>

<span data-ttu-id="aaad8-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="aaad8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="aaad8-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aaad8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aaad8-105">リトルエンディアン入力を受け取る操作が指定された場合、は、ビッグエンディアン入力を受け取る新しい操作を返します。</span><span class="sxs-lookup"><span data-stu-id="aaad8-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="aaad8-106">入力</span><span class="sxs-lookup"><span data-stu-id="aaad8-106">Input</span></span>

### <a name="op--littleendian--unit-adj"></a><span data-ttu-id="aaad8-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="aaad8-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="aaad8-108">入力を元に戻す操作。</span><span class="sxs-lookup"><span data-stu-id="aaad8-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit-adj"></a><span data-ttu-id="aaad8-109">出力: [bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [ユニット](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="aaad8-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="aaad8-110">ビッグエンディアンレジスタとしての入力を受け入れる新しい操作。</span><span class="sxs-lookup"><span data-stu-id="aaad8-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="aaad8-111">参照</span><span class="sxs-lookup"><span data-stu-id="aaad8-111">See Also</span></span>

- [<span data-ttu-id="aaad8-112">ApplyReversedOpLEA です。</span><span class="sxs-lookup"><span data-stu-id="aaad8-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="aaad8-113">ReversedOpLE です。</span><span class="sxs-lookup"><span data-stu-id="aaad8-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="aaad8-114">ReversedOpLEC です。</span><span class="sxs-lookup"><span data-stu-id="aaad8-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="aaad8-115">ReversedOpLECA です。</span><span class="sxs-lookup"><span data-stu-id="aaad8-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)