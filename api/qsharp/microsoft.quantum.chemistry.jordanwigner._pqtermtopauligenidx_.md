---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQTermToPauliGenIdx_
title: _Pqtermtop# ligenidx_ 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 046b3b7b78cee7f046607277896100e20c33a32d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839308"
---
# <a name="_pqtermtopauligenidx_-function"></a>_Pqtermtop# ligenidx_ 関数

名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)

パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


PQ 用語を記述する GeneratorIndex を、Paulis の観点で式 ' GeneratorIndex [] ' に変換します。

```qsharp
function _PQTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a>入力

### <a name="term--generatorindex"></a>用語: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` PQ 用語を表します。



## <a name="output--generatorindex"></a>出力: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]

' GeneratorIndex [] ' は、PQ term としての用語を表現します。