---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: AllEqualityFactB 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 100aacccbfd5b45ac9f859cd89424b0ed4007f72
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713078"
---
# <a name="allequalityfactb-function"></a>AllEqualityFactB 関数

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


ブール値の2つの配列が等しいことをアサートします。

```qsharp
function AllEqualityFactB (actual : Bool[], expected : Bool[], message : String) : Unit
```


## <a name="input"></a>入力

### <a name="actual--bool"></a>実際: [Bool](xref:microsoft.quantum.lang-ref.bool)[]

対象のテストケースによって生成される配列。


### <a name="expected--bool"></a>必要: [Bool](xref:microsoft.quantum.lang-ref.bool)[]

対象のテストケースからの予期される配列。


### <a name="message--string"></a>message: [文字列](xref:microsoft.quantum.lang-ref.string)

配列が等しくない場合に出力されるメッセージ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

