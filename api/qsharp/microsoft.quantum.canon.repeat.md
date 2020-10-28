---
uid: Microsoft.Quantum.Canon.Repeat
title: 繰り返し操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Repeat
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 5aedd056b851b8d8d7c25a32eb22587292e132a8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715598"
---
# <a name="repeat-operation"></a>繰り返し操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


指定された回数だけ操作を繰り返します。

```qsharp
operation Repeat<'TInput> (op : ('TInput => Unit), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a>入力

### <a name="op--tinput--unit"></a>op: ' TInput => [単位](xref:microsoft.quantum.lang-ref.unit) 

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
- [Microsoft. RepeatA](xref:Microsoft.Quantum.Canon.RepeatA)
- [Microsoft. RepeatC](xref:Microsoft.Quantum.Canon.RepeatC)
- [Microsoft. Canon. RepeatCA](xref:Microsoft.Quantum.Canon.RepeatCA)