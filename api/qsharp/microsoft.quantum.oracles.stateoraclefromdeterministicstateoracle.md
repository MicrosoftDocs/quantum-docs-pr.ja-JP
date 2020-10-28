---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: StateOracleFromDeterministicStateOracle 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: ccb083dbaaec2f306ba0740ef364ebb22408ed98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724217"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a>StateOracleFromDeterministicStateOracle 関数

名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)

パック [](https://nuget.org/packages/)


型の oracle `DeterministicStateOracle` をに変換 `StateOracle` します。

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a>入力

### <a name="deterministicstateoracle--deterministicstateoracle"></a>deterministicStateOracle: [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

型の状態準備 oracle $A $ `DeterministicStateOracle` 。



## <a name="output--stateoracle"></a>出力: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)

同じ状態準備 oracle $A $ が、現在は型になって `StateOracle` います。 こののフラグインデックス `StateOracle` はダミー変数であり、効果はありません。

## <a name="see-also"></a>参照

- [Oracles. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Oracles. StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)