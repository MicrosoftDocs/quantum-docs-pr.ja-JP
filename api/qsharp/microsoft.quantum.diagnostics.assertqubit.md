---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: AssertQubit 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: fa1f52da5a011cd914a0fda69b78cf5a4fd71e16
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712943"
---
# <a name="assertqubit-operation"></a>AssertQubit 操作

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


Qubit `q` が Pauli Z 演算子の予期される eigenstate にあることをアサートします。

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a>入力

### <a name="expected--__invalidresult__"></a>想定: __無効 <Result>__

Qubit があることが予期されている状態: `Zero` または `One` 。


### <a name="q--qubit"></a>q: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

状態がアサートされる qubit。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

<xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> $Z $ eigenstates だけでなく、任意の qubit 状態をアサートできるようにします。

## <a name="see-also"></a>参照

- [AssertQubitIsInStateWithinTolerance です。](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)