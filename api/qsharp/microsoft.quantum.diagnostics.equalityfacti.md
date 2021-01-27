---
uid: Microsoft.Quantum.Diagnostics.EqualityFactI
title: EqualityFactI 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactI
qsharp.summary: Asserts that a classical Int variable has the expected value.
ms.openlocfilehash: c41cb5548e8dfebb4d1c1a1c052306878c85e821
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853346"
---
# <a name="equalityfacti-function"></a>EqualityFactI 関数

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

