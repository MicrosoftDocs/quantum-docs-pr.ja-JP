---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQandPQQRTermToPauliGenIdx_
title: _Pqandpqqrtermtop/の Genidx_ 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQandPQQRTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 44a6d6b63d2f6bc8b628603e78931570d1ec22eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714371"
---
# <a name="_pqandpqqrtermtopauligenidx_-function"></a>_Pqandpqqrtermtop/の Genidx_ 関数

名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)

パック [](https://nuget.org/packages/)


PQ または PQQR 用語を記述する GeneratorIndex を、Paulis の観点で式 ' GeneratorIndex [] ' に変換します。

```qsharp
function _PQandPQQRTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a>入力

### <a name="term--generatorindex"></a>用語: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` PQ または PQQR 用語を表します。



## <a name="output--generatorindex"></a>出力: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]

' GeneratorIndex [] ' は、PQ または PQQR 用語を p の用語として表現します。