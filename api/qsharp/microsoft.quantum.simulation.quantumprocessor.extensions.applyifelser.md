---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseR
title: ApplyIfElseR 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseR
qsharp.summary: ''
ms.openlocfilehash: ca9db334bb62e043933f99e405612957831efdcb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724772"
---
# <a name="applyifelser-operation"></a>ApplyIfElseR 操作

名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。

パック [](https://nuget.org/packages/)




```qsharp
operation ApplyIfElseR<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit), zeroArg : 'T), (onResultOneOp : ('U => Unit), oneArg : 'U)) : Unit
```


## <a name="input"></a>入力

### <a name="measurementresult--__invalidresult__"></a>measurementResult: __無効 <Result>__




### <a name="onresultzeroop--t--unit"></a>onResultZeroOp: t => [Unit](xref:microsoft.quantum.lang-ref.unit) 




### <a name="zeroarg--t"></a>ゼロ Arg: ' '




### <a name="onresultoneop--u--unit"></a>onResultOneOp: ' U => [Unit](xref:microsoft.quantum.lang-ref.unit) 




### <a name="onearg--u"></a>On氏 g: ' U





## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&


### <a name="u"></a>' U

