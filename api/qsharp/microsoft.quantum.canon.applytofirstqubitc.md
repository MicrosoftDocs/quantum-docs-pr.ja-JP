---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitC
title: ApplyToFirstQubitC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitC
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: a36d20e03ebed82435d1d4136f4ce777eb468926
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850711"
---
# <a name="applytofirstqubitc-operation"></a>ApplyToFirstQubitC 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


レジスタ内の最初の qubit に操作 op を適用します。
修飾子は、 `C` 操作が制御可能であることを示します。

```qsharp
operation ApplyToFirstQubitC (op : (Qubit => Unit is Ctl), register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a>入力

### <a name="op--qubit--unit--is-ctl"></a>op: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です

最初の qubit に適用する操作


### <a name="register--qubit"></a>register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

操作が適用されている最初の qubit への qubit 配列



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>参照

- [Microsoft... "."。](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)