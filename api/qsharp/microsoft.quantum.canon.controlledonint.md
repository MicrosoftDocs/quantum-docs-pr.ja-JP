---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: Controlは Onint 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 6c7f46c44f2a2427f702e463195f26660cb4fca1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840783"
---
# <a name="controlledonint-function"></a>Controlは Onint 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


制御レジスタの状態が指定した正の整数に対応する場合に、ターゲットレジスタに oracle を適用する、ユニタリ演算子を返します。

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>入力

### <a name="numberstate--int"></a>数値の状態: [Int](xref:microsoft.quantum.lang-ref.int)

正の整数。


### <a name="oracle--t--unit--is-adj--ctl"></a>oracle: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です

ユニタリ演算子。



## <a name="output--qubitt--unit--is-adj--ctl"></a>出力: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[], ' t) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です

`oracle`コントロールの登録状態が数値の状態に対応している場合にターゲットレジスタに適用される、ユニタリ演算子 `numberState` 。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&



## <a name="remarks"></a>解説

の値は、リトルエン `numberState` ディアンエンコーディングを使用して解釈されます。