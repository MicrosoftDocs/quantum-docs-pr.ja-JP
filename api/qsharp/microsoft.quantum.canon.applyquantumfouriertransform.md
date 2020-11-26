---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransform
title: ApplyQuantumFourierTransform 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransform
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: 6d3ad9ca2e0d10c264f8020e1f34687f6cbc9f94
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218191"
---
# <a name="applyquantumfouriertransform-operation"></a>ApplyQuantumFourierTransform 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


リトルエンディアン表現内の整数を含むクォンタムレジスタに対して、Quantum フーリエ変換を実行します。

```qsharp
operation ApplyQuantumFourierTransform (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="qs--littleendian"></a>qs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

クォンタムのフーリエ変換が適用されるクォンタムレジスタ



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

入力と出力は、リトルエンディアンエンコーディングであると見なされます。

## <a name="see-also"></a>参照

- [Microsoft. ApplyQuantumFourierTransformBE](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)