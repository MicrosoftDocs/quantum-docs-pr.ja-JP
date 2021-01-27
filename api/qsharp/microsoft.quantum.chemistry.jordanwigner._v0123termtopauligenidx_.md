---
uid: Microsoft.Quantum.Chemistry.JordanWigner._V0123TermToPauliGenIdx_
title: _V0123TermToPauliGenIdx_ 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _V0123TermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 8893d7c5479409a0ff98aa0b9e58f34fd3d274f7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839191"
---
# <a name="_v0123termtopauligenidx_-function"></a>_V0123TermToPauliGenIdx_ 関数

名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)

パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Paulis の観点から、PQRS 用語を記述する GeneratorIndex を式 ' GeneratorIndex [] ' に変換します。

```qsharp
function _V0123TermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a>入力

### <a name="term--generatorindex"></a>用語: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` PQRS 用語を表す。



## <a name="output--generatorindex"></a>出力: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]

' GeneratorIndex [] ' は、PQRS 用語として表現されています。