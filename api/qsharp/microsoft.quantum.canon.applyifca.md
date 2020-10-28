---
uid: Microsoft.Quantum.Canon.ApplyIfCA
title: ApplyIfCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfCA
qsharp.summary: Applies a unitary operation conditioned on a classical bit.
ms.openlocfilehash: 9057c79622f15a082963d94fc261664e00322feb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718231"
---
# <a name="applyifca-operation"></a>ApplyIfCA 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


古典的なビットに対して条件付きのユニタリ操作を適用します。

```qsharp
operation ApplyIfCA<'T> (op : ('T => Unit is Ctl + Adj), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a>説明

操作とビット値を指定した場合は、 `op` `bit` `op` がの場合はに適用され `target` `bit` `true` ます。 `false`の場合、には何も起こりません `target` 。
サフィックスは、 `CA` 適用される操作が、ユニタリ (制御可能および adjointable) であることを示します。

## <a name="input"></a>入力

### <a name="op--t--unit-ctl--adj"></a>op: ' t => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞

条件付きで適用する操作。


### <a name="bit--bool"></a>bit: [Bool](xref:microsoft.quantum.lang-ref.bool)

op が適用されるかどうかを制御するブール値。


### <a name="target--t"></a>ターゲット: \

操作が適用される入力。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

条件付きで適用される操作の入力型。

## <a name="see-also"></a>参照

- [Microsoft. ApplyIfC](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [Microsoft. ApplyIfA](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [Microsoft. Canon. ApplyIfCA](xref:Microsoft.Quantum.Canon.ApplyIfCA)