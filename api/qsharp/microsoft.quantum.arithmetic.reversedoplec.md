---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEC
title: ReversedOpLEC 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEC
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 2dc6a596970f909af9c329dbe7002c165854cfec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846378"
---
# <a name="reversedoplec-function"></a><span data-ttu-id="39df3-102">ReversedOpLEC 関数</span><span class="sxs-lookup"><span data-stu-id="39df3-102">ReversedOpLEC function</span></span>

<span data-ttu-id="39df3-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="39df3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="39df3-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="39df3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="39df3-105">リトルエンディアン入力を受け取る操作が指定された場合、は、ビッグエンディアン入力を受け取る新しい操作を返します。</span><span class="sxs-lookup"><span data-stu-id="39df3-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="39df3-106">入力</span><span class="sxs-lookup"><span data-stu-id="39df3-106">Input</span></span>

### <a name="op--littleendian--unit--is-ctl"></a><span data-ttu-id="39df3-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="39df3-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="39df3-108">入力を元に戻す操作。</span><span class="sxs-lookup"><span data-stu-id="39df3-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit--is-ctl"></a><span data-ttu-id="39df3-109">出力: [bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [ユニット](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="39df3-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="39df3-110">ビッグエンディアンレジスタとしての入力を受け入れる新しい操作。</span><span class="sxs-lookup"><span data-stu-id="39df3-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="39df3-111">参照</span><span class="sxs-lookup"><span data-stu-id="39df3-111">See Also</span></span>

- [<span data-ttu-id="39df3-112">ApplyReversedOpLEC です。</span><span class="sxs-lookup"><span data-stu-id="39df3-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="39df3-113">ReversedOpLE です。</span><span class="sxs-lookup"><span data-stu-id="39df3-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="39df3-114">ReversedOpLEA です。</span><span class="sxs-lookup"><span data-stu-id="39df3-114">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="39df3-115">ReversedOpLECA です。</span><span class="sxs-lookup"><span data-stu-id="39df3-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)