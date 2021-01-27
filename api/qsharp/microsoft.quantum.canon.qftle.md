---
uid: Microsoft.Quantum.Canon.QFTLE
title: QFTLE 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: 893366833e5bd6b358884c11f4534609efd72d24
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852276"
---
# <a name="qftle-operation"></a>QFTLE 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


リトルエンディアン表現内の整数を含むクォンタムレジスタに対して、Quantum フーリエ変換を実行します。

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="qs--littleendian"></a>qs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

クォンタムのフーリエ変換が適用されるクォンタムレジスタ



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

入力と出力は、リトルエンディアンエンコーディングであると見なされます。

## <a name="see-also"></a>参照

- [Microsoft... Canon. QFT](xref:Microsoft.Quantum.Canon.QFT)