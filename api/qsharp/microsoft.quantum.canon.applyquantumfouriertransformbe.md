---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: ApplyQuantumFourierTransformBE 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: 39db7b4c69f7f06418ec257c013837c65b9cc67a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209045"
---
# <a name="applyquantumfouriertransformbe-operation"></a>ApplyQuantumFourierTransformBE 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


ビッグエンディアン表現に整数を含むクォンタムレジスタに対して、Quantum フーリエ変換を実行します。

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="qs--bigendian"></a>qs: [Bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian)

クォンタムのフーリエ変換が適用されるクォンタムレジスタ



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

入力と出力はビッグエンディアンエンコーディングであると見なされます。

## <a name="see-also"></a>参照

- [Microsoft. ApproximateQFT](xref:Microsoft.Quantum.Canon.ApproximateQFT)
- [Microsoft. QFTLE](xref:Microsoft.Quantum.Canon.QFTLE)