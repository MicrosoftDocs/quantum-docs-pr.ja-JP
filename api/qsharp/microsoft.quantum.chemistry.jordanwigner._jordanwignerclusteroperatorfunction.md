---
uid: Microsoft.Quantum.Chemistry.JordanWigner._JordanWignerClusterOperatorFunction
title: _JordanWignerClusterOperatorFunction 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _JordanWignerClusterOperatorFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: 71aa0256b4d2911fe9d8e3ca091735d6375ed23e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839502"
---
# <a name="_jordanwignerclusteroperatorfunction-function"></a>_JordanWignerClusterOperatorFunction 関数

名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)

パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Dynamical generator を simulatable ゲートと JordanWigner ベースの拡張のセットとして表します。

```qsharp
function _JordanWignerClusterOperatorFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a>入力

### <a name="generatorindex--generatorindex"></a>generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

JordanWigner での、ユニタリの発展として表現されるジェネレーターインデックス。



## <a name="output--evolutionunitary"></a>出力: [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)

`EvolutionUnitary`' GeneratorIndex ' で参照されている用語による時間の推移を表す。