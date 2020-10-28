---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: Control/Bitstring 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: ca5a6e116eff187060f7a160e42836b170f0362d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716443"
---
# <a name="controlledonbitstring-function"></a>Control/Bitstring 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


制御レジスタの状態が指定したビットマスクに対応する場合に、ターゲットレジスタに oracle を適用する、ユニタリ操作を返します。

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a>説明

この関数の出力は、\begin{align} U \ket{b_0 b_1/cドット b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \ cドット b_ {n-1}} という $U の、単位の変換で表すことができる演算です。 \ otimes \begin{cases} V \ket{\psi} & \t extrm{if} (b_0 b_1 \ cドット b_ {n-1}) = \texttt{bits} \\ \\ \ket{\psi} & \textrm{otherwise} \end{cases}, \end{align} ここで $V $ は、操作のアクションを表すミリ秒変換です `oracle` 。

## <a name="input"></a>入力

### <a name="bits--bool"></a>bits: [Bool](xref:microsoft.quantum.lang-ref.bool)[]

指定されたユニタリ操作を制御するビット文字列。


### <a name="oracle--t--unit-adj--ctl"></a>oracle: t => [ユニット](xref:microsoft.quantum.lang-ref.unit) の調整 + Ctl

ターゲットレジスタに適用されるユニタリ操作。



## <a name="output--qubitt--unit-adj--ctl"></a>出力: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[], ' t) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl

`oracle`コントロールのレジスタの状態がビットマスクに対応している場合に、ターゲットのレジスタに適用されるユニタリ操作 `bits` 。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&



## <a name="remarks"></a>解説

によって指定されたパターンは `bits` よりも短い場合があります `controlRegister` 。この場合、追加の制御 qubits は無視されます (つまり、$ \ket $ と $ \ket $ で制御されません {0} {1} )。
`bits`がより長い場合は `controlRegister` 、エラーが発生します。

ブール型の配列と1つの値を指定する `bits` と、 `oracle` この関数の出力は、次の手順を実行する操作になります。

* `X`の要素に対応する制御レジスタの各 qubit に操作を適用 `false` し `bits` ます。
* `Controlled oracle`コントロールとターゲットレジスタに適用します。
* コントロールレジスタを `X` `false` `bits` 元の状態に戻すために、の要素に対応する各 qubit に操作を適用します。

ファンクタの出力 `Controlled` は、 `ControlledOnBitString` `bits` がと等しい特殊なケースです `[true, ..., true]` 。