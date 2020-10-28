---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBE
title: ReversedOpBE 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBE
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 170f63e60e6c26dbdd33af02c6a3387a1b3dbc44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719702"
---
# <a name="reversedopbe-function"></a><span data-ttu-id="e5a1e-102">ReversedOpBE 関数</span><span class="sxs-lookup"><span data-stu-id="e5a1e-102">ReversedOpBE function</span></span>

<span data-ttu-id="e5a1e-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e5a1e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e5a1e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e5a1e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e5a1e-105">ビッグエンディアン入力を受け取る操作が指定された場合、は、リトルエンディアン入力を受け取る新しい操作を返します。</span><span class="sxs-lookup"><span data-stu-id="e5a1e-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="e5a1e-106">入力</span><span class="sxs-lookup"><span data-stu-id="e5a1e-106">Input</span></span>

### <a name="op--bigendian--unit"></a><span data-ttu-id="e5a1e-107">op: [bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [ユニット](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e5a1e-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e5a1e-108">入力を元に戻す操作。</span><span class="sxs-lookup"><span data-stu-id="e5a1e-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit"></a><span data-ttu-id="e5a1e-109">出力: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e5a1e-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e5a1e-110">入力をリトルエンディアンレジスタとして受け入れる新しい操作。</span><span class="sxs-lookup"><span data-stu-id="e5a1e-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5a1e-111">参照</span><span class="sxs-lookup"><span data-stu-id="e5a1e-111">See Also</span></span>

- [<span data-ttu-id="e5a1e-112">ApplyReversedOpBE です。</span><span class="sxs-lookup"><span data-stu-id="e5a1e-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="e5a1e-113">ReversedOpBEA です。</span><span class="sxs-lookup"><span data-stu-id="e5a1e-113">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="e5a1e-114">ReversedOpBEC です。</span><span class="sxs-lookup"><span data-stu-id="e5a1e-114">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [<span data-ttu-id="e5a1e-115">ReversedOpBECA です。</span><span class="sxs-lookup"><span data-stu-id="e5a1e-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)