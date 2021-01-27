---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: 不一致関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: 7d62c9341b768dfdfbfbf8e73e64748f04317595
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829361"
---
# <a name="contradiction-function"></a>不一致関数

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


クラシック条件が false であることを宣言します。

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a>入力

### <a name="actual--bool"></a>実際の値: [Bool](xref:microsoft.quantum.lang-ref.bool)

宣言する条件。


### <a name="message--string"></a>message: [文字列](xref:microsoft.quantum.lang-ref.string)

クラシック条件が true の場合に印刷されるエラーメッセージ文字列。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>例

次の Q # コードは、"Hello, world" を出力します。

```qsharp
Contradiction(2 == 3, "2 is not equal to 3.");
Message("Hello, world.");
```

## <a name="see-also"></a>参照

- [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics.Fact)