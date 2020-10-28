---
uid: Microsoft.Quantum.Convert.ResultArrayAsBoolArray
title: Resultarrayasブール配列関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultArrayAsBoolArray
qsharp.summary: Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: 0356fe9c98306ee3e1857f4af311aef9b3789a7d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713358"
---
# <a name="resultarrayasboolarray-function"></a>Resultarrayasブール配列関数

名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)

パック [](https://nuget.org/packages/)


型を `Result[]` 型に変換 `Bool[]` `One` します。ここで、はにマップされ、 `true` `Zero` はにマップされ `false` ます。

```qsharp
function ResultArrayAsBoolArray (input : Result[]) : Bool[]
```


## <a name="input"></a>入力

### <a name="input--__invalidresult__"></a>入力: __無効 <Result>__ []

`Result[]` 変換されます。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)[]

`Bool[]` を表す `input`。