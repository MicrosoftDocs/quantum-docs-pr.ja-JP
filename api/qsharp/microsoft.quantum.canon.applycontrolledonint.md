---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: Applycontrol/Int 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 499a25104742b2d03886065baad4d535ea92e83b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845101"
---
# <a name="applycontrolledonint-operation"></a>Applycontrol/Int 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


コントロールの登録状態が指定した正の整数に対応する場合は、ターゲットレジスタに対して、値の指定操作を適用します。

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="numberstate--int"></a>数値の状態: [Int](xref:microsoft.quantum.lang-ref.int)

操作を制御する必要がある負で `oracle` ない整数。


### <a name="oracle--t--unit--is-adj--ctl"></a>oracle: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です

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