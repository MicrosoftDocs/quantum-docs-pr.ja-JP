---
uid: Microsoft.Quantum.Convert.ResultArrayAsBoolArray
title: Resultarrayasブール配列関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultArrayAsBoolArray
qsharp.summary: Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: 384531137474562ebc8cc24dcd1ac976dc91ad9d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832587"
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