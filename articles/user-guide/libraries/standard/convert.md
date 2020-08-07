---
title: 標準ライブラリでの型変換 Q#
description: 標準ライブラリの一般的な型変換関数とユーザー定義型変換関数について説明し Q# ます。
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2319bf453f5fbf6bd068859ea65562423d3ff4d0
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868517"
---
# <a name="type-conversions"></a><span data-ttu-id="82d66-103">型変換</span><span class="sxs-lookup"><span data-stu-id="82d66-103">Type Conversions</span></span> #

<span data-ttu-id="82d66-104">Q#は、**厳密に型指定**された言語です。</span><span class="sxs-lookup"><span data-stu-id="82d66-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="82d66-105">特に、 Q# は、個別の型の間で暗黙的にキャストされません。</span><span class="sxs-lookup"><span data-stu-id="82d66-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="82d66-106">たとえば、 `1 + 2.0` は有効な式ではありません Q# 。</span><span class="sxs-lookup"><span data-stu-id="82d66-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="82d66-107">では、には、 Q# 指定された型の新しい値を構築するためのさまざまな型変換関数が用意されています。</span><span class="sxs-lookup"><span data-stu-id="82d66-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="82d66-108">たとえば、 <xref:microsoft.quantum.core.length> の出力型はである `Int` ため、その出力は、 `Double` 浮動小数点式の一部として使用する前に、まずに変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82d66-108">For example, <xref:microsoft.quantum.core.length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="82d66-109">これを行うには、関数を使用し <xref:microsoft.quantum.convert.intasdouble> ます。</span><span class="sxs-lookup"><span data-stu-id="82d66-109">This can be done using the <xref:microsoft.quantum.convert.intasdouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="82d66-110"><xref:microsoft.quantum.convert>名前空間は、、、、、などの基本的な組み込み型を操作するための共通の型変換関数を提供し `Int` `Double` `BigInt` `Result` `Bool` ます。</span><span class="sxs-lookup"><span data-stu-id="82d66-110">The <xref:microsoft.quantum.convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="82d66-111">名前空間には、 <xref:microsoft.quantum.convert> `FunctionAsOperation` 関数を新しい操作に変換するなど、より複雑な変換も用意されて `'T -> 'U` `'T => 'U` います。</span><span class="sxs-lookup"><span data-stu-id="82d66-111">The <xref:microsoft.quantum.convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="82d66-112">最後に、 Q# 標準ライブラリには、やなどの多数のユーザー定義型が用意されて <xref:microsoft.quantum.math.complex> <xref:microsoft.quantum.arithmetic.littleendian> います。</span><span class="sxs-lookup"><span data-stu-id="82d66-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:microsoft.quantum.math.complex> and <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>
<span data-ttu-id="82d66-113">これらの型と共に、標準ライブラリには次のような関数が用意されてい <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> ます。</span><span class="sxs-lookup"><span data-stu-id="82d66-113">Along with these types, the standard library provides functions such as <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span></span>

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
