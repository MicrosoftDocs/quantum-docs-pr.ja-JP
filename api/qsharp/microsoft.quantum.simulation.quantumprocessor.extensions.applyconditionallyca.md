---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyCA
title: Applyconditionの Ca 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyCA
qsharp.summary: ''
ms.openlocfilehash: e456ed5d8f7f17a914401473948c89c020174903
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720175"
---
# <a name="applyconditionallyca-operation"></a>Applyconditionの Ca 操作

名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。

パック [](https://nuget.org/packages/)




```qsharp
operation ApplyConditionallyCA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl + Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl + Adj), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a>入力

### <a name="measurementresults--__invalidresult__"></a>measurementResults: __無効 <Result> な__ []




### <a name="resultsvalues--__invalidresult__"></a>値の値 __: <Result> 無効__ []




### <a name="onequalop--t--unit-ctl--adj"></a>onEqualOp: t => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞




### <a name="equalarg--t"></a>equalArg: t




### <a name="onnonequalop--u--unit-ctl--adj"></a>onNonEqualOp: ' U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞




### <a name="nonequalarg--u"></a>nonEqualArg: ' U





## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&


### <a name="u"></a>' U

