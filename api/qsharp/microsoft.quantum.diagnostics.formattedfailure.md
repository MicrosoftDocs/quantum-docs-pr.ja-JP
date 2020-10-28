---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 0d7fb01ddf23cd6d79f722c8f6b691afa74a8885
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712677"
---
# <a name="formattedfailure-function"></a>FormattedFailure 関数

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


意味のあるエラーメッセージで失敗するために使用される内部関数です。

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a>入力

### <a name="actual--t"></a>実際の:




### <a name="expected--t"></a>' t ' が必要です。




### <a name="message--string"></a>message: [文字列](xref:microsoft.quantum.lang-ref.string)





## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&



## <a name="remarks"></a>解説

この関数は、書式設定された矛盾削除を転送できるように、シミュレーションランタイムによってエミュレートされることを目的としています。