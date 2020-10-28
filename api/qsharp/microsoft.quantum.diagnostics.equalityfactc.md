---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: EqualityFactC 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 4c7256f9a8c84b4e105b1cbff6b18d6dd99cc441
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712784"
---
# <a name="equalityfactc-function"></a>EqualityFactC 関数

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


複素数に予期される値があることをアサートします。

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a>入力

### <a name="actual--complex"></a>実績: [Complex](xref:Microsoft.Quantum.Math.Complex)

チェックする値。


### <a name="expected--complex"></a>必要: [Complex](xref:Microsoft.Quantum.Math.Complex)

予期される値。


### <a name="message--string"></a>message: [文字列](xref:microsoft.quantum.lang-ref.string)

アサーションがトリガーされたときに使用されるエラーメッセージ文字列。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

