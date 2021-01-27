---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLE
title: ReversedOpLE 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLE
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: d02817e5372b841f3ab633cafa22af603c5310c2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846392"
---
# <a name="reversedople-function"></a><span data-ttu-id="4f23d-102">ReversedOpLE 関数</span><span class="sxs-lookup"><span data-stu-id="4f23d-102">ReversedOpLE function</span></span>

<span data-ttu-id="4f23d-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4f23d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4f23d-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4f23d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4f23d-105">リトルエンディアン入力を受け取る操作が指定された場合、は、ビッグエンディアン入力を受け取る新しい操作を返します。</span><span class="sxs-lookup"><span data-stu-id="4f23d-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="4f23d-106">入力</span><span class="sxs-lookup"><span data-stu-id="4f23d-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="4f23d-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4f23d-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4f23d-108">入力を元に戻す操作。</span><span class="sxs-lookup"><span data-stu-id="4f23d-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit"></a><span data-ttu-id="4f23d-109">出力: [bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [ユニット](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4f23d-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4f23d-110">ビッグエンディアンレジスタとしての入力を受け入れる新しい操作。</span><span class="sxs-lookup"><span data-stu-id="4f23d-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f23d-111">参照</span><span class="sxs-lookup"><span data-stu-id="4f23d-111">See Also</span></span>

- [<span data-ttu-id="4f23d-112">ApplyReversedOpLE です。</span><span class="sxs-lookup"><span data-stu-id="4f23d-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="4f23d-113">ReversedOpLEA です。</span><span class="sxs-lookup"><span data-stu-id="4f23d-113">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="4f23d-114">ReversedOpLEC です。</span><span class="sxs-lookup"><span data-stu-id="4f23d-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="4f23d-115">ReversedOpLECA です。</span><span class="sxs-lookup"><span data-stu-id="4f23d-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)