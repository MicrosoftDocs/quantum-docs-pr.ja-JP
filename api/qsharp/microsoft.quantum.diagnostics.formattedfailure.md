---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 6b1202c8897d67e3089a88a0855c8008b3a8c2ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828276"
---
# <a name="formattedfailure-function"></a>FormattedFailure 関数

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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