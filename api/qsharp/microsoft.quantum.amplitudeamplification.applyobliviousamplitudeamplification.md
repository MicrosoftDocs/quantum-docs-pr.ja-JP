---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyObliviousAmplitudeAmplification
title: ApplyObliviousAmplitudeAmplification 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyObliviousAmplitudeAmplification
qsharp.summary: Oblivious amplitude amplification by specifying partial reflections.
ms.openlocfilehash: 9b0060201bcdae02a207362a753a0a403cdbb896
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191518"
---
# <a name="applyobliviousamplitudeamplification-operation"></a>ApplyObliviousAmplitudeAmplification 操作

名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


部分的な反射を指定することによって、振幅増幅を無関係します。

```qsharp
operation ApplyObliviousAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, auxiliaryRegister : Qubit[], systemRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="phases--reflectionphases"></a>フェーズ: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

部分的な反射のフェーズ


### <a name="startstatereflection--reflectionoracle"></a>startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

補助レジスタの開始状態に関するリフレクション演算子


### <a name="targetstatereflection--reflectionoracle"></a>targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

補助レジスタのターゲット状態に関するリフレクション演算子


### <a name="signaloracle--obliviousoracle"></a>signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

`ObliviousOracle`補助レジスタとシステムレジスタに共同で動作する型の、oracle $O $ のユニタリ。


### <a name="auxiliaryregister--qubit"></a>auxiliaryRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

補助レジスタ


### <a name="systemregister--qubit"></a>systemRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

システムレジスタ



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

特定の補助開始状態が指定されている場合 $ \ket{\text{start}} \_ a $, 特定の補助ターゲットの状態 $ \ket{\text{target}} \_ a $、および任意のシステム状態 $ \ket{\psi} \_ s $ では、一部の $U $ について、\begin{align} O\ket {\ text {start}} \_ a\ket {\ psi} \_ s = \lambda\ket{\text{target}} \_ a U \ket{\psi} \_ s + \sqrt{1-| \_ a \ket{\text{target} とします。
のアプリケーションとその adjoint によってインターリーブされる補助レジスタの開始状態とターゲット状態に関する一連の反射によって `signalOracle` 、U を適用する成功確率が変更される可能性があります。

ほとんどの場合、 `auxiliaryRegister` は、$ \ket{\text{start}} a $ という状態で初期化され \_ ます。

## <a name="references"></a>リファレンス

解決方法については、

- [ *D.W. Berry、A.M. Childs、Cleve、Kothari、R.D. Somma、*](https://arxiv.org/abs/1312.1414) standard バージョン。
  解決方法については、
- [ *G.H. Low、I.L. 語*](https://arxiv.org/abs/1610.06546)を部分的な反射に使用します。