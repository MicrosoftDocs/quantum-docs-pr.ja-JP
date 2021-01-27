---
uid: Microsoft.Quantum.Intrinsic.Message
title: Message 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 652e33de69ffb725f117db3beeffa66558776f49
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849375"
---
# <a name="message-function"></a>Message 関数

名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


メッセージのログを記録します。

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a>入力

### <a name="msg--string"></a>msg: [文字列](xref:microsoft.quantum.lang-ref.string)

報告されるメッセージ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

この関数の特定の動作はシミュレーターに依存しますが、ほとんどの場合、指定されたメッセージはコンソールに書き込まれます。