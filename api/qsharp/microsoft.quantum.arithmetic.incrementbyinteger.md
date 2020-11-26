---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: IncrementByInteger 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: fa5e75e91206aa5f33233c8a54d6e9e7ac2950e3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222968"
---
# <a name="incrementbyinteger-operation"></a>IncrementByInteger 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


フェーズ回転を使用して、古典的な整数によって署名されていないクォンタムレジスタをインクリメントします。

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

は、 `target` リトルエンディアンエンコーディングで $ $x $ の符号なし整数をエンコードし、 `increment` $a $ と等しいとします。
次に、この操作では、ユニタリ $ \ket{x} \ map\ket{x + a} $ を実装します。この場合、加算は $ 2 ^ n $ という剰余が実行されます。ここで、$n = \texttt{Length (target!)}$.

## <a name="input"></a>入力

### <a name="increment--int"></a>increment: [Int](xref:microsoft.quantum.lang-ref.int)

のインクリメントに使用する整数 `target` 。


### <a name="target--littleendian"></a>ターゲット: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

リトルエンディアンエンコーディングを使用して、符号なし整数をエンコードするクォンタムレジスタ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

