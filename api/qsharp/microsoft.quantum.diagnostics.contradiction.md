---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: 不一致関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: a5f3f26c5ada2eea9206699a2cc77575a9b5eebd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712868"
---
# <a name="contradiction-function"></a>不一致関数

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


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



## <a name="see-also"></a>参照

- [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics.Fact)