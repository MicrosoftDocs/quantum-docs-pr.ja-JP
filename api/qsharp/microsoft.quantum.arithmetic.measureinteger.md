---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: MeasureInteger 演算
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 7cd2d93332eb168c7c2be92a3b910033ca8c10ae
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720967"
---
# <a name="measureinteger-operation"></a>MeasureInteger 演算

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パック [](https://nuget.org/packages/)


クォンタムレジスタの内容を測定し、整数に変換します。 測定は、標準の計算基準 (つまり、の eigenbasis) に対して実行され `PauliZ` ます。

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a>入力

### <a name="target--littleendian"></a>ターゲット: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

リトルエンディアンエンコーディングでのクォンタムレジスタ。



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

の測定値を格納する符号なし整数 `target` 。

## <a name="remarks"></a>解説

この操作では、入力レジスタが $ \ket{00\cdots 0} $ 状態にリセットされ、ターゲットコンピューターへの解放に適しています。

## <a name="see-also"></a>参照

- [Microsoft...。](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)