---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 92b57f49407d558e5f8d0365c168b7890f1f4981
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223886"
---
# <a name="allequalityfacti-function"></a>AllEqualityFactI 関数

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

