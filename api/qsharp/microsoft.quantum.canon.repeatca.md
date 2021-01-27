---
uid: Microsoft.Quantum.Canon.RepeatCA
title: RepeatCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatCA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: af93220562d6be27b2f41e770bd953e5e808fcbf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852204"
---
# <a name="repeatca-operation"></a>RepeatCA 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定された回数だけ操作を繰り返します。

```qsharp
operation RepeatCA<'TInput> (op : ('TInput => Unit is Adj + Ctl), nTimes : Int, input : 'TInput) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="op--tinput--unit--is-adj--ctl"></a>op: ' TInput => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です

繰り返し呼び出す操作。


### <a name="ntimes--int"></a>nTimes: [Int](xref:microsoft.quantum.lang-ref.int)

を呼び出す回数 `op` 。


### <a name="input--tinput"></a>入力: ' TInput

に渡される入力 `op` 。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="tinput"></a>'TInput



## <a name="example"></a>例

同等のものを次に示します。

```qsharp
RepeatCA(U, 17, target);
(BoundCA(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a>参照

- [Microsoft.... Arrays. DrawMany](xref:Microsoft.Quantum.Arrays.DrawMany)
- [Microsoft.................](xref:Microsoft.Quantum.Canon.Repeat)
- [Microsoft. RepeatA](xref:Microsoft.Quantum.Canon.RepeatA)
- [Microsoft. RepeatC](xref:Microsoft.Quantum.Canon.RepeatC)