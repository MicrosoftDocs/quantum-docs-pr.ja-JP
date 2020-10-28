---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: d3163281772bda392fbdd61ad58543e22022a600
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712775"
---
# <a name="equalityfactb-function"></a>EqualityFactB 関数

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


クラシック Bool 変数に予期される値があることをアサートします。

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a>入力

### <a name="actual--bool"></a>実際の値: [Bool](xref:microsoft.quantum.lang-ref.bool)

チェックする変数。


### <a name="expected--bool"></a>必要: [Bool](xref:microsoft.quantum.lang-ref.bool)

予期される値。


### <a name="message--string"></a>message: [文字列](xref:microsoft.quantum.lang-ref.string)

アサーションがトリガーされたときに使用されるエラーメッセージ文字列。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

