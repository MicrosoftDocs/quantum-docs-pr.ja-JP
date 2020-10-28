---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 5e590af581be4e41df9d2081260409c454e3be4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712756"
---
# <a name="equalityfactl-function"></a>EqualityFactL 関数

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


古典 BigInt 変数に予期される値があることをアサートします。

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a>入力

### <a name="actual--bigint"></a>実際: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

確認する数値。


### <a name="expected--bigint"></a>予想される: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

予期される値。


### <a name="message--string"></a>message: [文字列](xref:microsoft.quantum.lang-ref.string)

アサーションがトリガーされたときに使用されるエラーメッセージ文字列。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

