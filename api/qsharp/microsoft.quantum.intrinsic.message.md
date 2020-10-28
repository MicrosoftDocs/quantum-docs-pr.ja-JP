---
uid: Microsoft.Quantum.Intrinsic.Message
title: Message 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 0428a46bc639bc8a0697f5bd392f85b8b9f40ee5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711426"
---
# <a name="message-function"></a>Message 関数

名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)

パック [](https://nuget.org/packages/)


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