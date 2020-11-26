---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 388fb67ba33810fc813fb646577bfa7f4a2b51ae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224464"
---
# <a name="boolarrayasresultarray-function"></a>BoolArrayAsResultArray 関数

名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


型を `Bool[]` 型に変換 `Result[]` `true` します。ここで、はにマップされ、 `One` `false` はにマップされ `Zero` ます。

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a>入力

### <a name="input--bool"></a>入力: [Bool](xref:microsoft.quantum.lang-ref.bool)[]

`Bool[]` 変換されます。



## <a name="output--__invalidresult__"></a>出力:__無効 <Result> な__[]

`Result[]` を表す `input`。