---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: ApplyMajorityInPlace 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 10b512392b2098663c09b2e07a09c4025da90706
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843726"
---
# <a name="applymajorityinplace-operation"></a>ApplyMajorityInPlace 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Qubit のレジスタに対して、3つの qubit マジョリティ操作をインプレースで適用します。

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

この操作では、3つの qubits のインプレース関数を計算します。

出力 qubit を $z $、入力 qubit を $x $ および $y $ として示す場合、この操作では次の変換が実行されます: $ \ket{xyz} \rightarrow \ket{x-oplus z} \ket{y \ oplus z} \ket{\operatorname{MAJ} (x, y, z)} $。

## <a name="input"></a>入力

### <a name="output--qubit"></a>出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

最初の入力 qubit。 出力がインプレースで計算され、この qubit に格納されていることに注意してください。


### <a name="input--qubit"></a>入力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

2番目と3番目の入力 qubits。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

