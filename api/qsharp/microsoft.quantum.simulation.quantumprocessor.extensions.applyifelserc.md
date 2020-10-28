---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRC
title: ApplyIfElseRC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRC
qsharp.summary: ''
ms.openlocfilehash: 21069c43c16bc9712973ac4e0afea8320c0d83a9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709466"
---
# <a name="applyifelserc-operation"></a>ApplyIfElseRC 操作

名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。

パック [](https://nuget.org/packages/)




```qsharp
operation ApplyIfElseRC<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Ctl), oneArg : 'U)) : Unit
```


## <a name="input"></a>入力

### <a name="measurementresult--__invalidresult__"></a>measurementResult: __無効 <Result>__




### <a name="onresultzeroop--t--unit-ctl"></a>onResultZeroOp: t => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl




### <a name="zeroarg--t"></a>ゼロ Arg: ' '




### <a name="onresultoneop--u--unit-ctl"></a>onResultOneOp: ' U => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl




### <a name="onearg--u"></a>On氏 g: ' U





## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&


### <a name="u"></a>' U

