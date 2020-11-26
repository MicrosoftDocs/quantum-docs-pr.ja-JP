---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracleFromStateOracle
title: DeterministicStateOracleFromStateOracle 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracleFromStateOracle
qsharp.summary: Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.
ms.openlocfilehash: 183b1108ead6239e26bb0b38144cb9374e7bf285
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226759"
---
# <a name="deterministicstateoraclefromstateoracle-function"></a>DeterministicStateOracleFromStateOracle 関数

名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


型の oracle `StateOracle` をに変換 `DeterministicStateOracle` します。

```qsharp
function DeterministicStateOracleFromStateOracle (idxFlagQubit : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle) : Microsoft.Quantum.Oracles.DeterministicStateOracle
```


## <a name="input"></a>入力

### <a name="idxflagqubit--int"></a>idxFlagQubit: [Int](xref:microsoft.quantum.lang-ref.int)

$A $ のフラグ qubit のインデックス。 `stateOracle` 2 つのレジスタを明示的に処理します。フラグ $f $、システム $s $ (例: $A \ket {0} \_ f\ket {\ psi} \_ s $)。


### <a name="stateoracle--stateoracle"></a>stateOracle: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)

型の状態準備 oracle $A $ `StateOracle` 。



## <a name="output--deterministicstateoracle"></a>出力: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

同じ状態準備 oracle $A $ ですが、現在は型 `DeterministicStateOracle` であるため、$a、s $ は明示的に分離されています。たとえば、 \Ket{0\psi} \_ {as} $ を $A します。

## <a name="see-also"></a>参照

- [Oracles. StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)
- [Oracles. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)