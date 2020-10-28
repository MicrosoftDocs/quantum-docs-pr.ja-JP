---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 1ea790debb5a9123fb8bee3a5f8a1fde0a050b37
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712770"
---
# <a name="equalityfactcp-function"></a>EqualityFactCP 関数

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


複素数に予期される値があることをアサートします。

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a>入力

### <a name="actual--complexpolar"></a>実績: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)

チェックする値。


### <a name="expected--complexpolar"></a>期待される結果: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)

予期される値。


### <a name="message--string"></a>message: [文字列](xref:microsoft.quantum.lang-ref.string)

アサーションがトリガーされたときに使用されるエラーメッセージ文字列。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

