---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLE
title: ReversedOpLE 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLE
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 6ebc4e97cb6d515e99e85922d03ca246b56084ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719647"
---
# <a name="reversedople-function"></a><span data-ttu-id="1bad2-102">ReversedOpLE 関数</span><span class="sxs-lookup"><span data-stu-id="1bad2-102">ReversedOpLE function</span></span>

<span data-ttu-id="1bad2-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1bad2-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1bad2-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1bad2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1bad2-105">リトルエンディアン入力を受け取る操作が指定された場合、は、ビッグエンディアン入力を受け取る新しい操作を返します。</span><span class="sxs-lookup"><span data-stu-id="1bad2-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="1bad2-106">入力</span><span class="sxs-lookup"><span data-stu-id="1bad2-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="1bad2-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1bad2-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="1bad2-108">入力を元に戻す操作。</span><span class="sxs-lookup"><span data-stu-id="1bad2-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit"></a><span data-ttu-id="1bad2-109">出力: [bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [ユニット](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1bad2-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="1bad2-110">ビッグエンディアンレジスタとしての入力を受け入れる新しい操作。</span><span class="sxs-lookup"><span data-stu-id="1bad2-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="1bad2-111">参照</span><span class="sxs-lookup"><span data-stu-id="1bad2-111">See Also</span></span>

- [<span data-ttu-id="1bad2-112">ApplyReversedOpLE です。</span><span class="sxs-lookup"><span data-stu-id="1bad2-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="1bad2-113">ReversedOpLEA です。</span><span class="sxs-lookup"><span data-stu-id="1bad2-113">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="1bad2-114">ReversedOpLEC です。</span><span class="sxs-lookup"><span data-stu-id="1bad2-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="1bad2-115">ReversedOpLECA です。</span><span class="sxs-lookup"><span data-stu-id="1bad2-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)