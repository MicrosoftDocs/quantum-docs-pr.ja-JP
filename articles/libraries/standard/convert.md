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
# <a name="type-conversions"></a>型変換 #

Q # は、**厳密に型指定**された言語です。
特に、Q # は個別の型の間で暗黙的にキャストされません。 たとえば、`1 + 2.0` は有効な Q # 式ではありません。
Q # には、特定の型の新しい値を構築するためのさまざまな型変換関数が用意されています。

たとえば、<xref:microsoft.quantum.core.length> の出力型が `Int`であるため、浮動小数点式の一部として使用するには、その出力を最初に `Double` に変換する必要があります。
これを行うには、<xref:microsoft.quantum.convert.intasdouble> 関数を使用します。

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<xref:microsoft.quantum.convert> 名前空間には、`Int`、`Double`、`BigInt`、`Result`、`Bool`などの基本的な組み込み型を操作するための共通の型変換関数が用意されています。

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<xref:microsoft.quantum.convert> 名前空間には、関数 `'T -> 'U` を新しい操作 `'T => 'U`に変換する `FunctionAsOperation`など、より複雑な変換も用意されています。

最後に、Q # 標準ライブラリには、<xref:microsoft.quantum.math.complex> や <xref:microsoft.quantum.arithmetic.littleendian>など、多数のユーザー定義型が用意されています。
これらの型と共に、標準ライブラリには <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>などの関数が用意されています。

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
