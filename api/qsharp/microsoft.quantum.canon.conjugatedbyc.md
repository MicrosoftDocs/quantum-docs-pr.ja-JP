---
uid: Microsoft.Quantum.Canon.ConjugatedByC
title: ConjugatedByC 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByC
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: 622b1d93dcbd02d000a68de23c66537b24d36c99
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840837"
---
# <a name="conjugatedbyc-function"></a>ConjugatedByC 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


外部操作と内部操作では、外部操作によって内部操作を活用する新しい操作が返されます。

```qsharp
function ConjugatedByC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl)) : ('T => Unit is Ctl)
```


## <a name="input"></a>入力

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です

$ $V を共役するために使用する必要がある操作 $U $。 外部操作 $U $ は adjointable である必要があることに注意してください。ただし、制御可能である必要はありません。


### <a name="inneroperation--t--unit--is-ctl"></a>innerOperation: ' t => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl

操作 $V $ conjugated。



## <a name="output--t--unit--is-ctl"></a>出力: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です

そのアクションが、$U ^ {-dagger} V U $ という、1つのユニタリによって表される新しい操作です。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

内部および外部の各操作が動作するターゲットの型。

## <a name="remarks"></a>解説

外部操作は常に adjointable と見なされますが、結合された操作を制御可能にするために制御する必要はありません。

## <a name="see-also"></a>参照

- [Microsoft. ConjugatedBy](xref:Microsoft.Quantum.Canon.ConjugatedBy)
- [Microsoft. ConjugatedByA](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [Microsoft. ConjugatedByCA](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [Microsoft.......](xref:Microsoft.Quantum.Canon.ApplyWith)