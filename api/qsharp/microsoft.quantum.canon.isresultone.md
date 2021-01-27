---
uid: Microsoft.Quantum.Canon.IsResultOne
title: IsResultOne 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultOne
qsharp.summary: Tests if a given Result value is equal to `One`.
ms.openlocfilehash: f259c21e6cc0a4886332e9ffcb546e527ec7def1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840328"
---
# <a name="isresultone-function"></a>IsResultOne 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定された結果値がと等しいかどうかをテスト `One` します。

```qsharp
function IsResultOne (input : Result) : Bool
```


## <a name="input"></a>入力

### <a name="input--__invalidresult__"></a>入力:__無効 <Result>__

`Result` テストする値。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` `input` がに等しい場合は、を返し `One` ます。