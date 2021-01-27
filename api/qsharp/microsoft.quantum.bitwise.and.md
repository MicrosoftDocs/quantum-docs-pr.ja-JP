---
uid: Microsoft.Quantum.Bitwise.And
title: And 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: And
qsharp.summary: Returns the bitwise AND of two integers. This performs the same computation as the built-in `&&&` operator.
ms.openlocfilehash: 56eae4ef222a6593fd97966a9af21d559f613bc3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842161"
---
# <a name="and-function"></a>And 関数

名前空間: [Microsoft. Quantum. ビット](xref:Microsoft.Quantum.Bitwise)処理

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


2つの整数のビットごとの AND を返します。
これにより、組み込み演算子と同じ計算が実行され `&&&` ます。

```qsharp
function And (a : Int, b : Int) : Int
```


## <a name="input"></a>入力

### <a name="a--int"></a>a: [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="b--int"></a>b: [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)



## <a name="example"></a>例

```qsharp
let a = 248;       //                11111000₂
let b = 63;        //                00111111₂
let x = And(a, b); // x : Int = 56 = 00111000₂.
```

## <a name="remarks"></a>解説

詳細については、「 [C# &amp; 演算子](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/and-operator) (バイナリ)」を参照してください。