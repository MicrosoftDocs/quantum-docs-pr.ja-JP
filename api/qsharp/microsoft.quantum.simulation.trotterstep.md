---
uid: Microsoft.Quantum.Simulation.TrotterStep
title: TrotterStep 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStep
qsharp.summary: Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.
ms.openlocfilehash: 7a1a27ba4dc4b8b7bbc4da6a378d4a1494bc9415
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725351"
---
# <a name="trotterstep-function"></a>TrotterStep 関数

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パック [](https://nuget.org/packages/)


Trotter – Suzuki 分解を使用して、「」で説明されているシステムによる時間の短縮の単一の時間ステップを実装 `EvolutionGenerator` します。

```qsharp
function TrotterStep (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, trotterOrder : Int, trotterStepSize : Double) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>入力

### <a name="evolutiongenerator--evolutiongenerator"></a>evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

シミュレートするシステムの完全な説明。


### <a name="trotterorder--int"></a>trotterOrder: [Int](xref:microsoft.quantum.lang-ref.int)

Trotter インテグレーターの順序。 この値には、1または偶数を指定する必要があります。


### <a name="trotterstepsize--double"></a>trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)

単一の Trotter ステップでシミュレートされた時間の進化の期間。



## <a name="output--qubit--unit-adj--ctl"></a>出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl

時間の短縮の1つのステップに近似する、期間の単一のステップを近似する、ユニタリ操作 `trotterStepSize` 。

## <a name="remarks"></a>解説

Trotter – Suzuki 分解の詳細については、「 [時間順序の構成](/quantum/libraries/control-flow#time-ordered-composition)」を参照してください。