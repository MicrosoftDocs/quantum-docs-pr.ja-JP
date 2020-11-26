---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: DivideI 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 4cff191e1f9d42659768b4059e477f1a07948ba1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223308"
---
# <a name="dividei-operation"></a>DivideI 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. 数値](https://nuget.org/packages/Microsoft.Quantum.Numerics)


2つのクォンタム整数を除算します。

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

`xs` は残りを保持し、を `xs - floor(xs/ys) * ys` `result` 保持 `floor(xs/ys)` します。

## <a name="input"></a>入力

### <a name="xs--littleendian"></a>xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-bit 被除数は、剰余に置き換えられます。


### <a name="ys--littleendian"></a>y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-bit 除数


### <a name="result--littleendian"></a>結果: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$ bit の結果 $n は、最初は状態 $ \ket $ である必要があり、 {0} 整数除算の結果に置き換えられます。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

は、標準のシフトと減算のアプローチを使用して除算を実装します。
コントロールバージョンは特化されているので、減算には追加の制御は必要ありません。