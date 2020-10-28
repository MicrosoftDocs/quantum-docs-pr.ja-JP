---
uid: Microsoft.Quantum.Convert.BoolAsResult
title: ブール Asresult 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolAsResult
qsharp.summary: Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: eea6c062afdbb3172e63261e52a82e2576c14011
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713587"
---
# <a name="boolasresult-function"></a>ブール Asresult 関数

名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)

パック [](https://nuget.org/packages/)


型を `Bool` 型に変換 `Result` `true` します。ここで、はにマップされ、 `One` `false` はにマップされ `Zero` ます。

```qsharp
function BoolAsResult (input : Bool) : Result
```


## <a name="input"></a>入力

### <a name="input--bool"></a>入力: [Bool](xref:microsoft.quantum.lang-ref.bool)

`Bool` 変換されます。



## <a name="output--__invalidresult__"></a>出力: __無効 <Result>__

`Result` を表す `input`。