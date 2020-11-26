---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: 乗算 Yi 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 96922f0147788b37cc9bace5154288a722d4ba95
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222509"
---
# <a name="multiplyi-operation"></a>乗算 Yi 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. 数値](https://nuget.org/packages/Microsoft.Quantum.Numerics)


整数 `xs` を整数で乗算 `ys` し、結果をに格納し `result` ます。最初はゼロである必要があります。

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="xs--littleendian"></a>xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-bit 被乗数 (LittleEndian)


### <a name="ys--littleendian"></a>y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-bit 乗数 (LittleEndian)


### <a name="result--littleendian"></a>結果: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$ 2n $ ビット結果 (LittleEndian) は、初期状態で $ \ket $ である必要があり {0} ます。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

標準のシフトアンド追加アプローチを使用して乗算を実装します。
制御されたバージョンを改善するには、コントロール qubit の ancilla qubit に $x _i $ をコピーし、ancilla qubit に対する加算を制御します。