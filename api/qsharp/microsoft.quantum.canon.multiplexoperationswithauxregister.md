---
uid: Microsoft.Quantum.Canon.MultiplexOperationsWithAuxRegister
title: MultiplexOperationsWithAuxRegister 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsWithAuxRegister
qsharp.summary: Implementation step of MultiplexOperations.
ms.openlocfilehash: f6a90657324f8528aaa2e9e511a7f8cbcd2f540f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715794"
---
# <a name="multiplexoperationswithauxregister-operation"></a>MultiplexOperationsWithAuxRegister 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


MultiplexOperations の実装手順。

```qsharp
operation MultiplexOperationsWithAuxRegister<'T> (unitaries : ('T => Unit is Adj + Ctl)[], auxillaryRegister : Qubit[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a>入力

### <a name="unitaries--t--unit-adj--ctl"></a>unitaries: ' t => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl []




### <a name="auxillaryregister--qubit"></a>auxillaryRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="index--littleendian"></a>index: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)




### <a name="target--t"></a>ターゲット: \





## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&



## <a name="see-also"></a>参照

- [Microsoft. MultiplexOperations](xref:Microsoft.Quantum.Canon.MultiplexOperations)