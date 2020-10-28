---
uid: Microsoft.Quantum.Canon.RepeatA
title: RepeatA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 89d34e5a30a61dee392904ce1076605432e21395
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715561"
---
# <a name="repeata-operation"></a>RepeatA 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


指定された回数だけ操作を繰り返します。

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a>入力

### <a name="op--tinput--unit-adj"></a>op: ' TInput => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞

繰り返し呼び出す操作。


### <a name="ntimes--int"></a>nTimes: [Int](xref:microsoft.quantum.lang-ref.int)

を呼び出す回数 `op` 。


### <a name="input--tinput"></a>入力: ' TInput

に渡される入力 `op` 。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="tinput"></a>'TInput



## <a name="see-also"></a>参照

- [Microsoft.... Arrays. DrawMany](xref:Microsoft.Quantum.Arrays.DrawMany)
- [Microsoft.................](xref:Microsoft.Quantum.Canon.Repeat)
- [Microsoft. RepeatC](xref:Microsoft.Quantum.Canon.RepeatC)
- [Microsoft. Canon. RepeatCA](xref:Microsoft.Quantum.Canon.RepeatCA)