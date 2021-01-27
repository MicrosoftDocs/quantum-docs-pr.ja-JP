---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA
title: ApplyReversedOpLECA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLECA
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: d0d444afcc1fa760f3035101e82cf8043c6541c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843492"
---
# <a name="applyreversedopleca-operation"></a>ApplyReversedOpLECA 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


ビッグエンディアン形式を使用して符号なし整数をエンコーディングするレジスタに、リトルエンディアン入力を受け取る操作を適用します。

```qsharp
operation ApplyReversedOpLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl + Adj), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="op--littleendian--unit--is-adj--ctl"></a>op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です

リトルエンディアンレジスタに対して動作する操作。


### <a name="register--bigendian"></a>register: [Bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian)

変換されるビッグエンディアンレジスタ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>参照

- [ApplyReversedOpLE です。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [ApplyReversedOpLEA です。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [ApplyReversedOpLEC です。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)