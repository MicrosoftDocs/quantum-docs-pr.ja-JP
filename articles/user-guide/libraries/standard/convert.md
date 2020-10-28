---
title: '標準ライブラリでの型変換 :::no-loc(Q#):::'
description: '標準ライブラリの一般的な型変換関数とユーザー定義型変換関数について説明し :::no-loc(Q#)::: ます。'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: article
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 9ec3a2ecd2aa59a10a7033e7b3067eb147ce4035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691104"
---
# <a name="type-conversions"></a><span data-ttu-id="de212-103">型変換</span><span class="sxs-lookup"><span data-stu-id="de212-103">Type Conversions</span></span> #

<span data-ttu-id="de212-104">:::no-loc(Q#)::: は、 **厳密に型指定** された言語です。</span><span class="sxs-lookup"><span data-stu-id="de212-104">:::no-loc(Q#)::: is a **strongly-typed** language.</span></span>
<span data-ttu-id="de212-105">特に、 :::no-loc(Q#)::: は、個別の型の間で暗黙的にキャストされません。</span><span class="sxs-lookup"><span data-stu-id="de212-105">In particular, :::no-loc(Q#)::: does not implicitly cast between distinct types.</span></span> <span data-ttu-id="de212-106">たとえば、 `1 + 2.0` は有効な式ではありません :::no-loc(Q#)::: 。</span><span class="sxs-lookup"><span data-stu-id="de212-106">For instance, `1 + 2.0` is not a valid :::no-loc(Q#)::: expression.</span></span>
<span data-ttu-id="de212-107">では、には、 :::no-loc(Q#)::: 指定された型の新しい値を構築するためのさまざまな型変換関数が用意されています。</span><span class="sxs-lookup"><span data-stu-id="de212-107">Rather, :::no-loc(Q#)::: provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="de212-108">たとえば、 <xref:Microsoft.Quantum.Core.Length> の出力型はである `Int` ため、その出力は、 `Double` 浮動小数点式の一部として使用する前に、まずに変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de212-108">For example, <xref:Microsoft.Quantum.Core.Length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="de212-109">これを行うには、関数を使用し <xref:Microsoft.Quantum.Convert.IntAsDouble> ます。</span><span class="sxs-lookup"><span data-stu-id="de212-109">This can be done using the <xref:Microsoft.Quantum.Convert.IntAsDouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="de212-110"><xref:Microsoft.Quantum.Convert>名前空間は、、、、、などの基本的な組み込み型を操作するための共通の型変換関数を提供し `Int` `Double` `BigInt` `Result` `Bool` ます。</span><span class="sxs-lookup"><span data-stu-id="de212-110">The <xref:Microsoft.Quantum.Convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="de212-111">名前空間には、 <xref:Microsoft.Quantum.Convert> `FunctionAsOperation` 関数を新しい操作に変換するなど、より複雑な変換も用意されて `'T -> 'U` `'T => 'U` います。</span><span class="sxs-lookup"><span data-stu-id="de212-111">The <xref:Microsoft.Quantum.Convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="de212-112">最後に、 :::no-loc(Q#)::: 標準ライブラリには、やなどの多数のユーザー定義型が用意されて <xref:Microsoft.Quantum.Math.Complex> <xref:Microsoft.Quantum.Arithmetic.LittleEndian> います。</span><span class="sxs-lookup"><span data-stu-id="de212-112">Finally, the :::no-loc(Q#)::: standard library provides a number of user-defined types such as <xref:Microsoft.Quantum.Math.Complex> and <xref:Microsoft.Quantum.Arithmetic.LittleEndian>.</span></span>
<span data-ttu-id="de212-113">これらの型と共に、標準ライブラリには次のような関数が用意されてい <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian> ます。</span><span class="sxs-lookup"><span data-stu-id="de212-113">Along with these types, the standard library provides functions such as <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian>:</span></span>

```:::no-loc(Q#):::
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
