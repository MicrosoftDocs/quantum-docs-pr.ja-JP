---
uid: Microsoft.Quantum.Canon.AndLadder
title: AndLadder 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: d44c462c7a9fc9521bdecfe2ca7f607e90482baf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845221"
---
# <a name="andladder-operation"></a>AndLadder 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


ターゲット qubits のレジスタで、制御された "AND はしご" を実行します。

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj
```


## <a name="description"></a>説明

この操作は、次の計算基準のマッピングによって記述された変換を適用します $ $ \begin{align} \ket{x \_ 1, \ ドット, x \_ n} \ket{y \_ 1, \ ドット, y \_ {n-1}} \ map\ket{\ket{x \_ 1, \ ドット, x \_ n} y \_ 1 \ oplus (x \_ 1 \ 陸 x \_ 2), \ ドット, y \_ {n-1} \ oplus (x \_ 1 \ \ket{x x \_ \_ {n-1}}, \end{align} $ $ where $ \_ 1, \ \ ($ 1, \) ドット, x \_ n} $ は、の計算ベースの状態を示し `controls` \_ ます。 $ \ket{y 1、\ ドット、y \_ {n-1}} $ は、の計算ベースの状態を表し `targets` ます。

## <a name="input"></a>入力

### <a name="ccnot--ccnotop"></a>ccnot: [Ccnotop](xref:Microsoft.Quantum.Canon.CCNOTop)

構築に使用する CCNOT ゲート。


### <a name="controls--qubit"></a>コントロール: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

およびはしごのコントロールとして使用される qubits のレジスタ。
この操作では、計算ベースの状態が `controls` 不変になります。
の長さは2以上でなければなりません。また、の長さは `controls` 1 以上にする必要があり `targets` ます。


### <a name="targets--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

の長さは `targets` 1 以上、の長さから1を引いた値にする必要があり `controls` ます。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

- およびの一部として使用され <xref:microsoft.quantum.canon.applymulticontrolledc> <xref:microsoft.quantum.canon.applymulticontrolledca> ます。
- 説明とサーキットの図については、図4.10 のセクション4.3 を参照してください & 語。

## <a name="references"></a>References

- [*Michael、Isaac、語*、量子計算、およびクォンタム情報](http://doi.org/10.1017/CBO9780511976667)