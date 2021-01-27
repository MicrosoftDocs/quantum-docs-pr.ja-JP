---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: AssertQubit 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: 8fcdd8de9250348e1dd1173052b53be978f2a0c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853447"
---
# <a name="assertqubit-operation"></a>AssertQubit 操作

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


Qubit `q` が Pauli Z 演算子の予期される eigenstate にあることをアサートします。

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a>入力

### <a name="expected--__invalidresult__"></a>想定:__無効 <Result>__

Qubit があることが予期されている状態: `Zero` または `One` 。


### <a name="q--qubit"></a>q: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

状態がアサートされる qubit。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

<xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> $Z $ eigenstates だけでなく、任意の qubit 状態をアサートできるようにします。

## <a name="see-also"></a>参照

- [AssertQubitIsInStateWithinTolerance です。](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)