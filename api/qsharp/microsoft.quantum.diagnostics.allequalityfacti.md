---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 9ccd212010ae557de5ca4ab2a38d4724c5c29aa8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713069"
---
# <a name="allequalityfacti-function"></a>AllEqualityFactI 関数

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


整数値の2つの配列が等しいことをアサートします。

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a>入力

### <a name="actual--int"></a>実際: [Int](xref:microsoft.quantum.lang-ref.int)[]

対象のテストケースによって生成される配列。


### <a name="expected--int"></a>[Int](xref:microsoft.quantum.lang-ref.int)[] が必要です

対象のテストケースからの予期される配列。


### <a name="message--string"></a>message: [文字列](xref:microsoft.quantum.lang-ref.string)

配列が等しくない場合に出力されるメッセージ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

