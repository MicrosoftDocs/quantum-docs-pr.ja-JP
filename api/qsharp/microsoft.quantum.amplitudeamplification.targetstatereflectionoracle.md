---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: TargetStateReflectionOracle 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: a6ed0397be57ef6f14a712749cc416e1fd98b71c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721725"
---
# <a name="targetstatereflectionoracle-function"></a>TargetStateReflectionOracle 関数

名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

パック [](https://nuget.org/packages/)


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