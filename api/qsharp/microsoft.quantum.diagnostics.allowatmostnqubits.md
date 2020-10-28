---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: AllowAtMostNQubits 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: ddbed96df0d95cfd78730c091a6a81ee6e49c349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713055"
---
# <a name="allowatmostnqubits-operation"></a>AllowAtMostNQubits 操作

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


この操作とその adjoint の呼び出しの間には、指定された数の追加の qubits が使用され、ステートメントを使用して割り当てられます。

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit
```


## <a name="input"></a>入力

### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

割り当てることができる qubits の最大数。


### <a name="message--string"></a>message: [文字列](xref:microsoft.quantum.lang-ref.string)

失敗したときに表示されるメッセージ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

この操作は、サポートされていない非 op ターゲットに置き換えることができます。