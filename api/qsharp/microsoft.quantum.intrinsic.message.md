---
uid: Microsoft.Quantum.Intrinsic.Message
title: Message 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 4eb55dd4fd8d78e4b5a9bb289dacfbdb3aa4beb8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199014"
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