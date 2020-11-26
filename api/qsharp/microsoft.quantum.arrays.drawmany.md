---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 3185f2ec01a2b9d01cff82a0c4667f12483801a7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209997"
---
# <a name="drawmany-operation"></a>DrawMany 操作

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定された数のサンプルに対して操作を繰り返し、配列内の出力を収集します。

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a>入力

### <a name="op--tinput--toutput"></a>op: ' TInput => ' TOutput 

繰り返し呼び出す操作。


### <a name="nsamples--int"></a>nSamples: [Int](xref:microsoft.quantum.lang-ref.int)

を呼び出して収集するサンプルの数 `op` 。


### <a name="input--tinput"></a>入力: ' TInput

に渡される入力 `op` 。



## <a name="output--toutput"></a>出力: ' TOutput []



## <a name="type-parameters"></a>型パラメーター

### <a name="tinput"></a>'TInput


### <a name="toutput"></a>'TOutput



## <a name="see-also"></a>参照

- [Microsoft.................](xref:Microsoft.Quantum.Canon.Repeat)