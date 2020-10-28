---
uid: Microsoft.Quantum.Diagnostics.EqualityFactI
title: EqualityFactI 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactI
qsharp.summary: Asserts that a classical Int variable has the expected value.
ms.openlocfilehash: 34bb38a9447f71372ec0b234731f31a5818d3af1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712761"
---
# <a name="equalityfacti-function"></a>EqualityFactI 関数

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


クラシック Int 変数に予期される値があることをアサートします。

```qsharp
function EqualityFactI (actual : Int, expected : Int, message : String) : Unit
```


## <a name="input"></a>入力

### <a name="actual--int"></a>実際の: [Int](xref:microsoft.quantum.lang-ref.int)

確認する数値。


### <a name="expected--int"></a>予期される値: [Int](xref:microsoft.quantum.lang-ref.int)

予期される値。


### <a name="message--string"></a>message: [文字列](xref:microsoft.quantum.lang-ref.string)

アサーションがトリガーされたときに使用されるエラーメッセージ文字列。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

