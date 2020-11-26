---
uid: Microsoft.Quantum.Convert.ResultArrayAsBoolArray
title: Resultarrayasブール配列関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultArrayAsBoolArray
qsharp.summary: Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: f3af3abd4ee58f495d4ea60ec4f21a2690abec1d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224226"
---
# <a name="resultarrayasboolarray-function"></a>Resultarrayasブール配列関数

名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


型を `Result[]` 型に変換 `Bool[]` `One` します。ここで、はにマップされ、 `true` `Zero` はにマップされ `false` ます。

```qsharp
function ResultArrayAsBoolArray (input : Result[]) : Bool[]
```


## <a name="input"></a>入力

### <a name="input--__invalidresult__"></a>入力:__無効 <Result>__[]

`Result[]` 変換されます。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)[]

`Bool[]` を表す `input`。