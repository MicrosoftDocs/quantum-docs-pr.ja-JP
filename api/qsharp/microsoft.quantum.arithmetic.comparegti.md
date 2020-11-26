---
uid: Microsoft.Quantum.Arithmetic.CompareGTI
title: CompareGTI 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTI
qsharp.summary: 'Wrapper for integer comparison: `result = x > y`.'
ms.openlocfilehash: b6e82eb7e9c068eff5bb320bb797a8fb0f8f921b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223478"
---
# <a name="comparegti-operation"></a>CompareGTI 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. 数値](https://nuget.org/packages/Microsoft.Quantum.Numerics)


整数比較の `result = x > y` ラッパー:

```qsharp
operation CompareGTI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="xs--littleendian"></a>xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

最初の $n $-bit number


### <a name="ys--littleendian"></a>y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

2番目の $n $-bit number


### <a name="result--qubit"></a>結果: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

$X > y $ の場合は反転されます



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

