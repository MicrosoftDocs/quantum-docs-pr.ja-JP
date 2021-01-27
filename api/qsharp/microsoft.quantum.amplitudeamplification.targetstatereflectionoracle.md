---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: TargetStateReflectionOracle 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: 4169ccf3e210e27f779311553b845ea04f2c7dc6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843905"
---
# <a name="targetstatereflectionoracle-function"></a>TargetStateReflectionOracle 関数

名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


`ReflectionOracle`フラグ qubit で一意にマークされたターゲット状態に関するを構築します。

ターゲット状態では、1つの qubit が1に設定され、それ以外の場合は 0: $ \ket {1} _f $ になります。

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a>入力

### <a name="idxflagqubit--int"></a>idxFlagQubit: [Int](xref:microsoft.quantum.lang-ref.int)

Oracle のフラグ qubit $f $ にインデックスを作成します。



## <a name="output--reflectionoracle"></a>出力: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

`ReflectionOracle`$ \Ket _f $ によってマークされた状態に関する情報を反映する {1} 。

## <a name="see-also"></a>参照

- [Microsoft. ReflectionOracle](xref:Microsoft.Quantum.Canon.ReflectionOracle)