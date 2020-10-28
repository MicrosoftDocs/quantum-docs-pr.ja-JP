---
uid: Microsoft.Quantum.Canon.IsResultOne
title: IsResultOne 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultOne
qsharp.summary: Tests if a given Result value is equal to `One`.
ms.openlocfilehash: fa8845fd92e5c16b4ff15436caf42df4f1e151cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716051"
---
# <a name="isresultone-function"></a>IsResultOne 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


指定された結果値がと等しいかどうかをテスト `One` します。

```qsharp
function IsResultOne (input : Result) : Bool
```


## <a name="input"></a>入力

### <a name="input--__invalidresult__"></a>入力: __無効 <Result>__

`Result` テストする値。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` `input` がに等しい場合は、を返し `One` ます。