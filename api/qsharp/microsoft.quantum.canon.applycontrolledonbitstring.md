---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: Applycontrol/Bitstring 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 82adc74e23e1d50cb6436176a973fdd1a0eeb3bd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841941"
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