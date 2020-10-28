---
uid: Microsoft.Quantum.Chemistry.JordanWigner._V0123TermToPauliMajIdx_
title: _V0123TermToPauliMajIdx_ 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _V0123TermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 7295b510de2621698d48d40ac28e234d0c8915eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714189"
---
# <a name="_v0123termtopaulimajidx_-function"></a>_V0123TermToPauliMajIdx_ 関数

名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)

パック [](https://nuget.org/packages/)


Paulis の観点から、PQRS 用語を記述する GeneratorIndex を式 ' GeneratorIndex [] ' に変換します。

```qsharp
function _V0123TermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex[]
```


## <a name="input"></a>入力

### <a name="term--generatorindex"></a>用語: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` PQRS 用語を表す。



## <a name="output--optimizedbetermindex"></a>出力: [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)[]

' GeneratorIndex [] ' は、PQRS 用語として表現されています。