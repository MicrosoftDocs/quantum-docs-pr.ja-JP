---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyA
title: ApplyConditionallyA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyA
qsharp.summary: ''
ms.openlocfilehash: b6f7e7d6d51e531b0ec9e7e4f2f5772038421933
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710530"
---
# <a name="applyconditionallya-operation"></a>ApplyConditionallyA 操作

名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。

パック [](https://nuget.org/packages/)




```qsharp
operation ApplyConditionallyA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Adj), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a>入力

### <a name="measurementresults--__invalidresult__"></a>measurementResults: __無効 <Result> な__ []




### <a name="resultsvalues--__invalidresult__"></a>値の値 __: <Result> 無効__ []




### <a name="onequalop--t--unit-adj"></a>onEqualOp: t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞




### <a name="equalarg--t"></a>equalArg: t




### <a name="onnonequalop--u--unit-adj"></a>onNonEqualOp: ' U => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞




### <a name="nonequalarg--u"></a>nonEqualArg: ' U





## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&


### <a name="u"></a>' U

