---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 408e50ed9f2e6c8ba35db20855608d2bd1f24eea
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721382"
---
# <a name="assertmostsignificantbit-operation"></a>AssertMostSignificantBit 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パック [](https://nuget.org/packages/)


符号なし整数を表す qubit レジスタの最上位の qubit が特定の状態であることをアサートします。

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>入力

### <a name="value--__invalidresult__"></a>値: __無効 <Result>__

アサートされる最上位ビットの値。


### <a name="number--littleendian"></a>数値: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

最上位ビットがチェックされる符号なし整数。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

この操作の制御されたバージョンは、コントロールを無視します。

## <a name="see-also"></a>参照

- [Microsoft. Quantum. Assert](xref:Microsoft.Quantum.Intrinsic.Assert)