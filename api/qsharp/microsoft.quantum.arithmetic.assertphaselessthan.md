---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: AssertPhaseLessThan 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: 8a943ff937593801bd308ab4224c7051ff8a10cb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223750"
---
# <a name="assertphaselessthan-operation"></a>AssertPhaseLessThan 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


PhaseLittleEndian でエンコードされたが未満であることをアサート `number` `value` します。

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="value--int"></a>値: [Int](xref:microsoft.quantum.lang-ref.int)

`number` は、このより小さい必要があります。


### <a name="number--phaselittleendian"></a>数値: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

と比較される符号なし整数 `value` 。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

この操作の制御されたバージョンは、コントロールを無視します。