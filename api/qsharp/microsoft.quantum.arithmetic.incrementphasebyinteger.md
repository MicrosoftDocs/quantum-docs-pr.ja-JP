---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: IncrementPhaseByInteger 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 54b83b3d4460c05478543c51f8f9c0b0e7f5b1fa
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222917"
---
# <a name="incrementphasebyinteger-operation"></a>IncrementPhaseByInteger 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


フェーズ回転を使用して、古典的な整数によって署名されていないクォンタムレジスタをインクリメントします。

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

は、 `target` リトルエンディアンエンコーディングで $ $x $ の符号なし整数をエンコードし、 `increment` $a $ と等しいとします。
次に、この操作では、ユニタリ $ \ket{x} \ map\ket{x + a} $ を実装します。この場合、加算は $ 2 ^ n $ という剰余が実行されます。ここで、$n = \texttt{Length (target!)}$.

## <a name="input"></a>入力

### <a name="increment--int"></a>increment: [Int](xref:microsoft.quantum.lang-ref.int)

のインクリメントに使用する整数 `target` 。


### <a name="target--phaselittleendian"></a>ターゲット: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

デュアルエンディアンエンコーディング (QFT) を使用して、符号なし整数をエンコードするクォンタムレジスタ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

回線は単純化されています。これは、増分が、クォンタムレジスタではなく、古典的な定数であるためです。

サーキットの図と説明については、 [ arXiv のページ6の図である quant-ph/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) を参照してください。

## <a name="references"></a>リファレンス

- [*Draper*, arxiv: quant-ph/0008033](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a>参照

- [IncrementByInteger です。](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)