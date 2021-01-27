---
title: 標準ライブラリでの型変換 Q#
description: 標準ライブラリの一般的な型変換関数とユーザー定義型変換関数について説明し Q# ます。
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: 67f47339363a52097f342c8ae4e43a8a93d606a8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858020"
---
# <a name="type-conversions"></a><span data-ttu-id="5a3f1-103">型変換</span><span class="sxs-lookup"><span data-stu-id="5a3f1-103">Type Conversions</span></span> #

<span data-ttu-id="5a3f1-104">Q# は、 **厳密に型指定** された言語です。</span><span class="sxs-lookup"><span data-stu-id="5a3f1-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="5a3f1-105">特に、 Q# は、個別の型の間で暗黙的にキャストされません。</span><span class="sxs-lookup"><span data-stu-id="5a3f1-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="5a3f1-106">たとえば、 `1 + 2.0` は有効な式ではありません Q# 。</span><span class="sxs-lookup"><span data-stu-id="5a3f1-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="5a3f1-107">では、には、 Q# 指定された型の新しい値を構築するためのさまざまな型変換関数が用意されています。</span><span class="sxs-lookup"><span data-stu-id="5a3f1-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="5a3f1-108">たとえば、 <xref:Microsoft.Quantum.Core.Length> の出力型はである `Int` ため、その出力は、 `Double` 浮動小数点式の一部として使用する前に、まずに変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a3f1-108">For example, <xref:Microsoft.Quantum.Core.Length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="5a3f1-109">これを行うには、関数を使用し <xref:Microsoft.Quantum.Convert.IntAsDouble> ます。</span><span class="sxs-lookup"><span data-stu-id="5a3f1-109">This can be done using the <xref:Microsoft.Quantum.Convert.IntAsDouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="5a3f1-110"><xref:Microsoft.Quantum.Convert>名前空間は、、、、、などの基本的な組み込み型を操作するための共通の型変換関数を提供し `Int` `Double` `BigInt` `Result` `Bool` ます。</span><span class="sxs-lookup"><span data-stu-id="5a3f1-110">The <xref:Microsoft.Quantum.Convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="5a3f1-111">名前空間には、 <xref:Microsoft.Quantum.Convert> `FunctionAsOperation` 関数を新しい操作に変換するなど、より複雑な変換も用意されて `'T -> 'U` `'T => 'U` います。</span><span class="sxs-lookup"><span data-stu-id="5a3f1-111">The <xref:Microsoft.Quantum.Convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="5a3f1-112">最後に、 Q# 標準ライブラリには、やなどの多数のユーザー定義型が用意されて <xref:Microsoft.Quantum.Math.Complex> <xref:Microsoft.Quantum.Arithmetic.LittleEndian> います。</span><span class="sxs-lookup"><span data-stu-id="5a3f1-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:Microsoft.Quantum.Math.Complex> and <xref:Microsoft.Quantum.Arithmetic.LittleEndian>.</span></span>
<span data-ttu-id="5a3f1-113">これらの型と共に、標準ライブラリには次のような関数が用意されてい <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian> ます。</span><span class="sxs-lookup"><span data-stu-id="5a3f1-113">Along with these types, the standard library provides functions such as <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian>:</span></span>

```qsharp
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
