---
uid: Microsoft.Quantum.Canon.ConjugatedBy
title: ConjugatedBy 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedBy
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: 37fbee9a7c11991645933a372f9f12c1fd696b66
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716471"
---
# <a name="conjugatedby-function"></a>ConjugatedBy 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


外部操作と内部操作では、外部操作によって内部操作を活用する新しい操作が返されます。

```qsharp
function ConjugatedBy<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit)) : ('T => Unit)
```


## <a name="input"></a>入力

### <a name="outeroperation--t--unit-adj"></a>outerOperation: t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞

$ $V を共役するために使用する必要がある操作 $U $。 外部操作 $U $ は adjointable である必要があることに注意してください。ただし、制御可能である必要はありません。


### <a name="inneroperation--t--unit"></a>innerOperation: t => [Unit](xref:microsoft.quantum.lang-ref.unit) 

操作 $V $ conjugated。



## <a name="output--t--unit"></a>出力: t => [Unit](xref:microsoft.quantum.lang-ref.unit) 

そのアクションが、$U ^ {-dagger} V U $ という、1つのユニタリによって表される新しい操作です。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

内部および外部の各操作が動作するターゲットの型。

## <a name="remarks"></a>解説

外部操作は常に adjointable と見なされますが、結合された操作を制御可能にするために制御する必要はありません。

## <a name="see-also"></a>参照

- [Microsoft. ConjugatedByA](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [Microsoft. ConjugatedByC](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [Microsoft. ConjugatedByCA](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [Microsoft.......](xref:Microsoft.Quantum.Canon.ApplyWith)