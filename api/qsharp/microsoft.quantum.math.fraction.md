---
uid: Microsoft.Quantum.Math.Fraction
title: ユーザー定義型の分数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1838bb2b605b109742948ec0633b08ca01baea98
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210677"
---
# <a name="fraction-user-defined-type"></a>ユーザー定義型の分数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


フォームの有理数を表し `p/q` ます。 Integer `p` は組の最初の要素で、 `q` は組の2番目の要素です。

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a>名前付き項目

### <a name="numerator--int"></a>分子: [Int](xref:microsoft.quantum.lang-ref.int)

分数の分子。
### <a name="denominator--int"></a>分母: [Int](xref:microsoft.quantum.lang-ref.int)

分数/の分母