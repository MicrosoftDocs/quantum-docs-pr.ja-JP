---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: QuantumPhaseEstimation 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 4bdf3de9dab20fa97ba47f15efec4b41a10709f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839672"
---
# <a name="quantumphaseestimation-operation"></a>QuantumPhaseEstimation 操作

名前空間: [Microsoft. 量子. 特性](xref:Microsoft.Quantum.Characterization)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定された oracle に対してクォンタムフェーズ推定アルゴリズムを実行し `U` `targetState` 、フェーズをビッグエンディアンクォンタムレジスタに読み込みます。

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="oracle--discreteoracle"></a>oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

指定された整数の $U ^ m $ を実装する操作は、m を累乗します。


### <a name="targetstate--qubit"></a>targetState: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

$U $ によって操作された状態 $ \ket{\phi} $ を表すクォンタムレジスタ。 $ \Ket{\phi} $ が $U $ の eigenstate の場合、$U \ket{\phi} = e ^ {i\ phi} \ket{\phi} $ for $ \ phi \ in [0, 2 \ pi) $ 不明なフェーズです。


### <a name="controlregister--bigendian"></a>controlRegister: [Bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian)

指定された oracle の制御に使用できるビッグエンディアン表現整数レジスタ。このレジスタには、この操作の適用後に $ + phi $ の表現が含まれます。 ControlRegister は初期状態 $ \ket{00\cdots 0} $ で開始することを前提としています。レジスタの長さは、必要な有効桁数を示しています。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

