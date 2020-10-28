---
uid: Microsoft.Quantum.Canon.ApplyWith
title: ApplyWith 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWith
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: 61047ea2ea249e5a4d39b5747c542462c9632138
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716947"
---
# <a name="applywith-operation"></a>ApplyWith 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


2つの操作を指定した場合、1つは conjugated として適用されます。

```qsharp
operation ApplyWith<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit), target : 'T) : Unit
```


## <a name="description"></a>説明

指定された2つの操作は、それぞれが $U $ および $V $ という順序で記述されていますが、これらはシーケンス $U ^ {\ dagger} V U $ に適用されます。 つまり、この操作では、$V $ conjugated によって指定された、$U $ のユニタリ演算子が実装されます。

## <a name="input"></a>入力

### <a name="outeroperation--t--unit-adj"></a>outerOperation: t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞

$ $V を共役するために使用する必要がある操作 $U $。 外部操作 $U $ は adjointable である必要があることに注意してください。ただし、制御可能である必要はありません。


### <a name="inneroperation--t--unit"></a>innerOperation: t => [Unit](xref:microsoft.quantum.lang-ref.unit) 

操作 $V $ conjugated。


### <a name="target--t"></a>ターゲット: \

外部操作と内部操作に提供する入力。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

内部および外部の各操作が動作するターゲット。

## <a name="remarks"></a>解説

外部操作は常に adjointable と見なされますが、結合された操作を制御可能にするために制御する必要はありません。

## <a name="see-also"></a>参照

- [Microsoft...。](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [Microsoft...。](xref:Microsoft.Quantum.Canon.ApplyWithC)
- [Microsoft...。](xref:Microsoft.Quantum.Canon.ApplyWithCA)