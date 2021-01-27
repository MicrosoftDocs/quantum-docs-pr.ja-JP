---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Fact 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 8e86000f04c01040d420c2f682fc1b4ccf35cf39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853319"
---
# <a name="fact-function"></a>Fact 関数

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


クラシック条件が true であることを宣言します。

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a>入力

### <a name="actual--bool"></a>実際の値: [Bool](xref:microsoft.quantum.lang-ref.bool)

宣言する条件。


### <a name="message--string"></a>message: [文字列](xref:microsoft.quantum.lang-ref.string)

古典条件が false の場合に印刷されるエラーメッセージ文字列。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>例

次の Q # スニペットは失敗します。

```qsharp
Fact(false, "Expected true.");
```

## <a name="see-also"></a>参照

- [Microsoft... 診断の不一致](xref:Microsoft.Quantum.Diagnostics.Contradiction)