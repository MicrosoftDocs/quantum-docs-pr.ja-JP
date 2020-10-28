---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: Controlは Onint 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 4c48f3257f91fc50040d02cae7c2f7bdf87ea7c5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716415"
---
# <a name="controlledonint-function"></a>Controlは Onint 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


制御レジスタの状態が指定した正の整数に対応する場合に、ターゲットレジスタに oracle を適用する、ユニタリ演算子を返します。

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>入力

### <a name="numberstate--int"></a>数値の状態: [Int](xref:microsoft.quantum.lang-ref.int)

正の整数。


### <a name="oracle--t--unit-adj--ctl"></a>oracle: t => [ユニット](xref:microsoft.quantum.lang-ref.unit) の調整 + Ctl

ユニタリ演算子。



## <a name="output--qubitt--unit-adj--ctl"></a>出力: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[], ' t) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl

`oracle`コントロールの登録状態が数値の状態に対応している場合にターゲットレジスタに適用される、ユニタリ演算子 `numberState` 。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&



## <a name="remarks"></a>解説

の値は、リトルエン `numberState` ディアンエンコーディングを使用して解釈されます。