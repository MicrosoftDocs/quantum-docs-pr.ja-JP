---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: AssertQubitWithinTolerance 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 7f57fc7a29d3eb86dc94cb24230d52b37eb6971d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853430"
---
# <a name="assertqubitwithintolerance-operation"></a>AssertQubitWithinTolerance 操作

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


`q`指定された許容範囲を上限として、Pauli Z 演算子の予期される eigenstate に qubit があることをアサートします。

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a>入力

### <a name="expected--__invalidresult__"></a>想定:__無効 <Result>__

Qubit があることが予期されている状態: `Zero` または `One` 。


### <a name="q--qubit"></a>q: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

状態がアサートされる qubit。


### <a name="tolerance--double"></a>tolerance: [Double](xref:microsoft.quantum.lang-ref.double)

Qubit の測定値が予想される結果を返す確率の許容範囲です。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

<xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> $Z $ eigenstates だけでなく、任意の qubit 状態をアサートできるようにします。

## <a name="see-also"></a>参照

- [AssertQubitIsInStateWithinTolerance です。](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)