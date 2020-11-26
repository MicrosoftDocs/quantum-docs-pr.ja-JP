---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: 09de63d615a4d80e2b59deeddc07567aefe7660e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193830"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a>ReflectionOracleFromDeterministicStateOracle 関数

名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Oracle から特定の状態に関するリフレクションを構築します。

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a>説明

配列 $O によって表される決定的な状態準備 oracle があるとします。この関数の結果は oracle で、oracle $O $; によって準備された状態 $ \ket{\psi} $ の周りにリフレクションが適用されます。つまり、$ \ket{\psi} $ という状態で、\ket {0} = \ket{\psi} $ という $O ます。

## <a name="input"></a>入力

### <a name="oracle--deterministicstateoracle"></a>oracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

$ \Ket{\psi} $ の状態のコピーを準備する oracle。



## <a name="output--reflectionoracle"></a>出力: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

状態 $ \ket{\psi} $ を反映する oracle。

## <a name="see-also"></a>参照

- [Oracles. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Oracles. ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)