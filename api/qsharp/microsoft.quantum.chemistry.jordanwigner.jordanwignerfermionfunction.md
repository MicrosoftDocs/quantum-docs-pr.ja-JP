---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionFunction
title: JordanWignerFermionFunction 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: 7d29393293acfc1748a1805f339951b1ff0f9b10
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714030"
---
# <a name="jordanwignerfermionfunction-function"></a>JordanWignerFermionFunction 関数

名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)

パック [](https://nuget.org/packages/)


Dynamical generator を simulatable ゲートと JordanWigner ベースの拡張のセットとして表します。

```qsharp
function JordanWignerFermionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a>入力

### <a name="generatorindex--generatorindex"></a>generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

JordanWigner での、ユニタリの発展として表現されるジェネレーターインデックス。



## <a name="output--evolutionunitary"></a>出力: [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)

`EvolutionUnitary`' GeneratorIndex ' で参照されている用語による時間の推移を表す。