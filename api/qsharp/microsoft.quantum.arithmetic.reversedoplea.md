---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEA
title: ReversedOpLEA 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: b0fcf1c735bb19308a381307e64314d9d961e5da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846430"
---
# <a name="reversedoplea-function"></a><span data-ttu-id="f08a0-102">ReversedOpLEA 関数</span><span class="sxs-lookup"><span data-stu-id="f08a0-102">ReversedOpLEA function</span></span>

<span data-ttu-id="f08a0-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f08a0-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f08a0-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f08a0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f08a0-105">リトルエンディアン入力を受け取る操作が指定された場合、は、ビッグエンディアン入力を受け取る新しい操作を返します。</span><span class="sxs-lookup"><span data-stu-id="f08a0-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="f08a0-106">入力</span><span class="sxs-lookup"><span data-stu-id="f08a0-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj"></a><span data-ttu-id="f08a0-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="f08a0-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="f08a0-108">入力を元に戻す操作。</span><span class="sxs-lookup"><span data-stu-id="f08a0-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit--is-adj"></a><span data-ttu-id="f08a0-109">出力: [bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [ユニット](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="f08a0-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="f08a0-110">ビッグエンディアンレジスタとしての入力を受け入れる新しい操作。</span><span class="sxs-lookup"><span data-stu-id="f08a0-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="f08a0-111">参照</span><span class="sxs-lookup"><span data-stu-id="f08a0-111">See Also</span></span>

- [<span data-ttu-id="f08a0-112">ApplyReversedOpLEA です。</span><span class="sxs-lookup"><span data-stu-id="f08a0-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="f08a0-113">ReversedOpLE です。</span><span class="sxs-lookup"><span data-stu-id="f08a0-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="f08a0-114">ReversedOpLEC です。</span><span class="sxs-lookup"><span data-stu-id="f08a0-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="f08a0-115">ReversedOpLECA です。</span><span class="sxs-lookup"><span data-stu-id="f08a0-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)