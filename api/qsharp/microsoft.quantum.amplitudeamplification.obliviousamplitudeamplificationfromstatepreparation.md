---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation
title: ObliviousAmplitudeAmplificationFromStatePreparation 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromStatePreparation
qsharp.summary: Oblivious amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 9975d26af8f9beb2b91e409ad78159d6f04936e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721832"
---
# <a name="obliviousamplitudeamplificationfromstatepreparation-function"></a>ObliviousAmplitudeAmplificationFromStatePreparation 関数

名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

パック [](https://nuget.org/packages/)


部分的な反射のために oracles による振幅増幅を無関係します。

```qsharp
function ObliviousAmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a>入力

### <a name="phases--reflectionphases"></a>フェーズ: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

部分的な反射のフェーズ


### <a name="startstateoracle--deterministicstateoracle"></a>startStateOracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

補助開始状態を準備する oracle $A $ のユニタリ


### <a name="signaloracle--obliviousoracle"></a>signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

`ObliviousOracle`補助レジスタとシステムレジスタに共同で動作する型の、oracle $O $ のユニタリ


### <a name="idxflagqubit--int"></a>idxFlagQubit: [Int](xref:microsoft.quantum.lang-ref.int)

シングル qubit フラグ登録のインデックス



## <a name="output--qubitqubit--unit-adj--ctl"></a>出力: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [単位](xref:microsoft.quantum.lang-ref.unit) の調整 + Ctl

部分的な反射に基づいて無関係の振幅増幅を実装する操作。

## <a name="remarks"></a>解説

これにより、のような補助開始状態とターゲット状態の形式に対して、より厳密な条件が課さ `AmpAmpObliviousByReflectionPhases` れます。
$A \ket {0} \_ f\ket {0} \_ A = \ket{\text{start}} \_ {fa} $ は、 \_ 計算ベース $ \ket f\ket $ から補助開始状態 $ \ket{\text{start}} {fa} $ を準備 {0} \_ {0} することを前提としています。
ターゲットの状態が $ \ket f $ によってマークされていることを前提としてい {1} \_ ます。
\Begin{align} O\ket {\ text {start}} \_ {fa} \ket{\psi} \_ s = \lambda\ket {1} \_ f\ket {\ text {すべて}} \_ a\ket {\ text {target}} \_ s U \ket{\psi} \_ s + \sqrt{1-| \ lambda | ^ 2} \ket \end{align}; {0} \_ (一部のユニタリ $U $) を想定しています。