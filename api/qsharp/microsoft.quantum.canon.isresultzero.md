---
uid: Microsoft.Quantum.Canon.IsResultZero
title: IsResultZero 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultZero
qsharp.summary: Tests if a given Result value is equal to `Zero`.
ms.openlocfilehash: 790551690cfba42df4cf7aa77e53e303050bdf39
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716032"
---
# <a name="isresultzero-function"></a>IsResultZero 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


指定された結果値がと等しいかどうかをテスト `Zero` します。

```qsharp
function IsResultZero (input : Result) : Bool
```


## <a name="input"></a>入力

### <a name="input--__invalidresult__"></a>入力: __無効 <Result>__

`Result` テストする値。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` `input` がに等しい場合は、を返し `Zero` ます。