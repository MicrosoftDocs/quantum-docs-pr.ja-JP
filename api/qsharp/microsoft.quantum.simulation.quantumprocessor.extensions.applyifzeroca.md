---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroCA
title: ApplyIfZeroCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroCA
qsharp.summary: ''
ms.openlocfilehash: 978964888a89ca46847ae7aa01a2c180ee322436
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725673"
---
# <a name="applyifzeroca-operation"></a>ApplyIfZeroCA 操作

名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。

パック [](https://nuget.org/packages/)




```qsharp
operation ApplyIfZeroCA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl + Adj), zeroArg : 'T)) : Unit
```


## <a name="input"></a>入力

### <a name="measurementresult--__invalidresult__"></a>measurementResult: __無効 <Result>__




### <a name="onresultzeroop--t--unit-ctl--adj"></a>onResultZeroOp: t => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞




### <a name="zeroarg--t"></a>ゼロ Arg: ' '





## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

