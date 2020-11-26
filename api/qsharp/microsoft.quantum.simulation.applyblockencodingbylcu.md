---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: ApplyBlockEncodingByLCU 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: 8ce6eb16b1dc5a83dd3a9559592c20d6b7b999b6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225484"
---
# <a name="applyblockencodingbylcu-operation"></a>ApplyBlockEncodingByLCU 操作

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


`BlockEncodingByLCU` の実装です。

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="statepreparation--t--unit--is-adj--ctl"></a>statePreparation: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です




### <a name="selector--ts--unit--is-adj--ctl"></a>セレクター: (' t, s) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です




### <a name="auxiliary--t"></a>補助: \




### <a name="system--s"></a>システム:





## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&


### <a name="s"></a>Emc

