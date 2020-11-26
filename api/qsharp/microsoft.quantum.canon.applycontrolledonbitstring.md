---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: Applycontrol/Bitstring 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 6947d2dbdec4cfbb592143024a7c8ccd53a32029
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219075"
---
# <a name="applycontrolledonbitstring-operation"></a>Applycontrol/Bitstring 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


ターゲットレジスタに対して、指定されたビットマスクによって指定された状態で制御される、一連の処理を実行します。

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="bits--bool"></a>bits: [Bool](xref:microsoft.quantum.lang-ref.bool)[]

指定されたユニタリ操作を制御するビット文字列。


### <a name="oracle--t--unit--is-adj--ctl"></a>oracle: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です

ターゲットレジスタに適用されるユニタリ操作。


### <a name="controlregister--qubit"></a>controlRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

のアプリケーションを制御するクォンタムレジスタ `oracle` 。


### <a name="targetregister--t"></a>targetRegister: ' t '

入力としてに渡されるターゲットレジスタ `oracle` 。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&



## <a name="remarks"></a>解説

によって指定されたパターンは `bits` よりも短い場合があります `controlRegister` 。この場合、追加の制御 qubits は無視されます (つまり、$ \ket $ と $ \ket $ で制御されません {0} {1} )。
`bits`がより長い場合は `controlRegister` 、エラーが発生します。

たとえば、は、 `bits = [0,1,0,0,1]` `oracle` `controlRegister` が $ \ket {0} \ket {1} \ket {0} \ket \ket $ という状態である場合にのみ適用され {0} {1} ます。