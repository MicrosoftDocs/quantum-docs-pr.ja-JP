---
title: 'Q # 標準ライブラリ-型変換 |Microsoft Docs'
description: 'Q # 標準ライブラリ-型変換'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 4716f0d9562229f08ef6f0f5f80961f793de4c5c
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184476"
---
# <a name="type-conversions"></a><span data-ttu-id="5c50b-103">型変換</span><span class="sxs-lookup"><span data-stu-id="5c50b-103">Type Conversions</span></span> #

<span data-ttu-id="5c50b-104">Q # は、**厳密に型指定**された言語です。</span><span class="sxs-lookup"><span data-stu-id="5c50b-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="5c50b-105">特に、Q # は個別の型の間で暗黙的にキャストされません。</span><span class="sxs-lookup"><span data-stu-id="5c50b-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="5c50b-106">たとえば、`1 + 2.0` は有効な Q # 式ではありません。</span><span class="sxs-lookup"><span data-stu-id="5c50b-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="5c50b-107">Q # には、特定の型の新しい値を構築するためのさまざまな型変換関数が用意されています。</span><span class="sxs-lookup"><span data-stu-id="5c50b-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="5c50b-108">たとえば、<xref:microsoft.quantum.core.length> の出力型が `Int`であるため、浮動小数点式の一部として使用するには、その出力を最初に `Double` に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c50b-108">For example, <xref:microsoft.quantum.core.length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="5c50b-109">これを行うには、<xref:microsoft.quantum.convert.intasdouble> 関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="5c50b-109">This can be done using the <xref:microsoft.quantum.convert.intasdouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="5c50b-110"><xref:microsoft.quantum.convert> 名前空間には、`Int`、`Double`、`BigInt`、`Result`、`Bool`などの基本的な組み込み型を操作するための共通の型変換関数が用意されています。</span><span class="sxs-lookup"><span data-stu-id="5c50b-110">The <xref:microsoft.quantum.convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="5c50b-111"><xref:microsoft.quantum.convert> 名前空間には、関数 `'T -> 'U` を新しい操作 `'T => 'U`に変換する `FunctionAsOperation`など、より複雑な変換も用意されています。</span><span class="sxs-lookup"><span data-stu-id="5c50b-111">The <xref:microsoft.quantum.convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="5c50b-112">最後に、Q # 標準ライブラリには、<xref:microsoft.quantum.math.complex> や <xref:microsoft.quantum.arithmetic.littleendian>など、多数のユーザー定義型が用意されています。</span><span class="sxs-lookup"><span data-stu-id="5c50b-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:microsoft.quantum.math.complex> and <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>
<span data-ttu-id="5c50b-113">これらの型と共に、標準ライブラリには <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>などの関数が用意されています。</span><span class="sxs-lookup"><span data-stu-id="5c50b-113">Along with these types, the standard library provides functions such as <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span></span>

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
