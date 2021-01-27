---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: b0b52a4ba7492d68896669aeb0b6b550d2f27f64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843420"
---
# <a name="assertmostsignificantbit-operation"></a>AssertMostSignificantBit 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


符号なし整数を表す qubit レジスタの最上位の qubit が特定の状態であることをアサートします。

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="value--__invalidresult__"></a>値:__無効 <Result>__

アサートされる最上位ビットの値。


### <a name="number--littleendian"></a>数値: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

最上位ビットがチェックされる符号なし整数。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

この操作の制御されたバージョンは、コントロールを無視します。

## <a name="see-also"></a>参照

- [Microsoft. Quantum. Assert](xref:Microsoft.Quantum.Intrinsic.Assert)