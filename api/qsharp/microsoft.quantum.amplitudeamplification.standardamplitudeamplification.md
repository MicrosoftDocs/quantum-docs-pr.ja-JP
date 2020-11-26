---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification
title: StandardAmplitudeAmplification 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardAmplitudeAmplification
qsharp.summary: Standard Amplitude Amplification algorithm
ms.openlocfilehash: 23a2b3dbe5ea404059994167f69e11458c0c22ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191178"
---
# <a name="standardamplitudeamplification-function"></a>StandardAmplitudeAmplification 関数

名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


標準の振幅増幅アルゴリズム

```qsharp
function StandardAmplitudeAmplification (nIterations : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>入力

### <a name="niterations--int"></a>nIterations: [Int](xref:microsoft.quantum.lang-ref.int)

振幅増幅数 $n の反復回数


### <a name="stateoracle--stateoracle"></a>stateOracle: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)

開始状態を準備する oracle $A $ のユニタリ


### <a name="idxflagqubit--int"></a>idxFlagQubit: [Int](xref:microsoft.quantum.lang-ref.int)

フラグ qubit へのインデックス



## <a name="output--qubit--unit--is-adj--ctl"></a>出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl

標準の振幅増幅クォンタムアルゴリズムを実装する操作

## <a name="remarks"></a>解説

これは、 `AmpAmpPhasesStandard` \Begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ text {target}} s + \sqrt{1-| \ ラムダ | ^ 2} \ket fcドットを想定して計算された、標準の振幅増幅アルゴリズムです。 \_ {0} \_ \end{align} この操作により、\begin{align} \operatorname{AmpAmpByOracle}\ket {0} \_ {f} \ket {0} \_ s = \ sin ((2n + 1) \ sin ^ {-1} (\ ラムダ)) \ket {1} \_ f\ket {\ text {target}} \_ s + \cdots\ket f \end{align} の状態がほとんどの {0} \_ 場合に準備され、 `flagQubit` `auxiliaryRegister` 状態が $ \ket {0} \_ f\ket a $ に初期化され {0} \_ ます。

## <a name="references"></a>リファレンス

- [*Hoyer、m.、M、Mosca、A. Tapp。*](https://arxiv.org/abs/quant-ph/0005055)