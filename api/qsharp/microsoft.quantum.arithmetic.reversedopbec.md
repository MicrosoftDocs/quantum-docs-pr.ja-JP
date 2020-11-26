---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEC
title: ReversedOpBEC 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEC
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 5bafe71b665eda082eafbe06be1308d6b042db2c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222271"
---
# <a name="reversedopbec-function"></a><span data-ttu-id="c238c-102">ReversedOpBEC 関数</span><span class="sxs-lookup"><span data-stu-id="c238c-102">ReversedOpBEC function</span></span>

<span data-ttu-id="c238c-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c238c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c238c-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c238c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c238c-105">ビッグエンディアン入力を受け取る操作が指定された場合、は、リトルエンディアン入力を受け取る新しい操作を返します。</span><span class="sxs-lookup"><span data-stu-id="c238c-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="c238c-106">入力</span><span class="sxs-lookup"><span data-stu-id="c238c-106">Input</span></span>

### <a name="op--bigendian--unit--is-ctl"></a><span data-ttu-id="c238c-107">op: [bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [ユニット](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="c238c-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="c238c-108">入力を元に戻す操作。</span><span class="sxs-lookup"><span data-stu-id="c238c-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit--is-ctl"></a><span data-ttu-id="c238c-109">出力: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  は Ctl です。</span><span class="sxs-lookup"><span data-stu-id="c238c-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="c238c-110">入力をリトルエンディアンレジスタとして受け入れる新しい操作。</span><span class="sxs-lookup"><span data-stu-id="c238c-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="c238c-111">参照</span><span class="sxs-lookup"><span data-stu-id="c238c-111">See Also</span></span>

- [<span data-ttu-id="c238c-112">ApplyReversedOpBEC です。</span><span class="sxs-lookup"><span data-stu-id="c238c-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="c238c-113">ReversedOpBE です。</span><span class="sxs-lookup"><span data-stu-id="c238c-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="c238c-114">ReversedOpBEA です。</span><span class="sxs-lookup"><span data-stu-id="c238c-114">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="c238c-115">ReversedOpBECA です。</span><span class="sxs-lookup"><span data-stu-id="c238c-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)