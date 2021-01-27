---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: ApplyToEach 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 61dda69751989ef8a98fa8fb01d832014ec4ad35
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844623"
---
# <a name="applytoeach-operation"></a>ApplyToEach 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


レジスタ内の各要素に単一の qubit 演算を適用します。

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a>入力

### <a name="singleelementoperation--t--unit"></a>singleElementOperation: t => [Unit](xref:microsoft.quantum.lang-ref.unit) 

各 qubit に適用する操作。


### <a name="register--t"></a>register: t []

指定された操作を適用する qubits の配列。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

操作が動作するターゲット。

## <a name="example"></a>例

3 qubit $ \ket{+} $ 状態を準備します。

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a>参照

- [Microsoft................](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [Microsoft.......](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [Microsoft... の各 Ca](xref:Microsoft.Quantum.Canon.ApplyToEachCA)