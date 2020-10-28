---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: Applycontrol/Int 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: c8ea76946143967de4b6ac65986a1c4407ecb633
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718351"
---
# <a name="applycontrolledonint-operation"></a>Applycontrol/Int 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


コントロールの登録状態が指定した正の整数に対応する場合は、ターゲットレジスタに対して、値の指定操作を適用します。

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a>入力

### <a name="numberstate--int"></a>数値の状態: [Int](xref:microsoft.quantum.lang-ref.int)

操作を制御する必要がある負で `oracle` ない整数。


### <a name="oracle--t--unit-adj--ctl"></a>oracle: t => [ユニット](xref:microsoft.quantum.lang-ref.unit) の調整 + Ctl

制御される、ユニタリ操作。


### <a name="controlregister--qubit"></a>controlRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

のアプリケーションを制御するクォンタムレジスタ `oracle` 。


### <a name="targetregister--t"></a>targetRegister: ' t '

適用するレジスタ `oracle` 。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&



## <a name="remarks"></a>解説

の値は、リトルエン `numberState` ディアンエンコーディングを使用して解釈されます。

`numberState` は最大で $ 2 ^ \texttt{Length (controlRegister)}-$1 である必要があります。
たとえば、 `numberState = 537` `oracle` は、 `controlRegister` が $ \ket $ という状態にある場合にのみ適用されることを意味し {537} ます。