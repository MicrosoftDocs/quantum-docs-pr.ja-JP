---
title: 標準ライブラリでの型変換 Q#
description: 標準ライブラリの一般的な型変換関数とユーザー定義型変換関数について説明し Q# ます。
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: aa8a1ad624067906998d2735c7a95174a163ce97
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835606"
---
# <a name="type-conversions"></a>型変換 #

Q# は、 **厳密に型指定** された言語です。
特に、 Q# は、個別の型の間で暗黙的にキャストされません。 たとえば、 `1 + 2.0` は有効な式ではありません Q# 。
では、には、 Q# 指定された型の新しい値を構築するためのさまざまな型変換関数が用意されています。

たとえば、 <xref:microsoft.quantum.core.length> の出力型はである `Int` ため、その出力は、 `Double` 浮動小数点式の一部として使用する前に、まずに変換する必要があります。
これを行うには、関数を使用し <xref:microsoft.quantum.convert.intasdouble> ます。

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<xref:microsoft.quantum.convert>名前空間は、、、、、などの基本的な組み込み型を操作するための共通の型変換関数を提供し `Int` `Double` `BigInt` `Result` `Bool` ます。

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

名前空間には、 <xref:microsoft.quantum.convert> `FunctionAsOperation` 関数を新しい操作に変換するなど、より複雑な変換も用意されて `'T -> 'U` `'T => 'U` います。

最後に、 Q# 標準ライブラリには、やなどの多数のユーザー定義型が用意されて <xref:microsoft.quantum.math.complex> <xref:microsoft.quantum.arithmetic.littleendian> います。
これらの型と共に、標準ライブラリには次のような関数が用意されてい <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> ます。

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
