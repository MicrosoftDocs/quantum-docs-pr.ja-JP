---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Fact 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 6a08703f68f9f38f2224fe4c6a4d255b00756908
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712686"
---
# <a name="fact-function"></a>Fact 関数

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


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



## <a name="see-also"></a>参照

- [Microsoft... 診断の不一致](xref:Microsoft.Quantum.Diagnostics.Contradiction)