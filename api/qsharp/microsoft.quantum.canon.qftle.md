---
uid: Microsoft.Quantum.Canon.QFTLE
title: QFTLE 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: f28f74d34fb4688739646da3dc12ae6734eb4ad4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715640"
---
# <a name="qftle-operation"></a>QFTLE 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


リトルエンディアン表現内の整数を含むクォンタムレジスタに対して、Quantum フーリエ変換を実行します。

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>入力

### <a name="qs--littleendian"></a>qs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

クォンタムのフーリエ変換が適用されるクォンタムレジスタ



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

入力と出力は、リトルエンディアンエンコーディングであると見なされます。

## <a name="see-also"></a>参照

- [Microsoft... Canon. QFT](xref:Microsoft.Quantum.Canon.QFT)