---
uid: Microsoft.Quantum.Convert.BoolAsResult
title: ブール Asresult 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolAsResult
qsharp.summary: Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 0ed5c81cb80458e2f56ba2fcaac03eb92a534bea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834170"
---
# <a name="boolasresult-function"></a>ブール Asresult 関数

名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


型を `Bool` 型に変換 `Result` `true` します。ここで、はにマップされ、 `One` `false` はにマップされ `Zero` ます。

```qsharp
function BoolAsResult (input : Bool) : Result
```


## <a name="input"></a>入力

### <a name="input--bool"></a>入力: [Bool](xref:microsoft.quantum.lang-ref.bool)

`Bool` 変換されます。



## <a name="output--__invalidresult__"></a>出力:__無効 <Result>__

`Result` を表す `input`。