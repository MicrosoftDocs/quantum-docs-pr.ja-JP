---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: bf63ce308679cef97c776d3383ff732ed4d4e500
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846203"
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



## <a name="example"></a>例

次の例では、一度に1ビットをサンプリングする操作を指定して、整数を示します。

```qsharp
let randomInteger = BoolArrayAsInt(DrawMany(SampleRandomBit, 16, ()));
```

## <a name="see-also"></a>参照

- [Microsoft.................](xref:Microsoft.Quantum.Canon.Repeat)