---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 2b293dc581ed58f7e3864a952fb3ecafa68e759c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712742"
---
# <a name="equalityfactr-function"></a>EqualityFactR 関数

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


古典的な結果変数に予期される値があることをアサートします。

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a>入力

### <a name="actual--__invalidresult__"></a>実績: __無効 <Result>__

チェックする変数。


### <a name="expected--__invalidresult__"></a>想定: __無効 <Result>__

予期される値。


### <a name="message--string"></a>message: [文字列](xref:microsoft.quantum.lang-ref.string)

アサーションがトリガーされたときに使用されるエラーメッセージ文字列。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

