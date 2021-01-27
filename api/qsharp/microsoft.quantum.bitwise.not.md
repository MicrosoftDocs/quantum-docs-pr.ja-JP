---
uid: Microsoft.Quantum.Bitwise.Not
title: Not 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Not
qsharp.summary: Returns the bitwise NOT of an integer. This performs the same computation as the built-in `~~~` operator.
ms.openlocfilehash: 9c7642770c4f1db4878ccc1aba288fb9254e017e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842108"
---
# <a name="not-function"></a>Not 関数

名前空間: [Microsoft. Quantum. ビット](xref:Microsoft.Quantum.Bitwise)処理

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


整数のビットごとの NOT を返します。
これにより、組み込み演算子と同じ計算が実行され `~~~` ます。

```qsharp
function Not (a : Int) : Int
```


## <a name="input"></a>入力

### <a name="a--int"></a>a: [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)



## <a name="example"></a>例

```qsharp
let a = 248;
let x = Not(a); // x : Int = -249, due to two's complement representation.
```

## <a name="remarks"></a>解説

詳細については、「 [~ 演算子](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/bitwise-complement-operator) 」を参照してください。