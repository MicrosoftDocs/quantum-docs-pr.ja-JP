---
uid: Microsoft.Quantum.Math.Fraction
title: ユーザー定義型の分数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 350d470c374fc8e0a3f4c4a9a68ad8566ab88727
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723657"
---
# <a name="fraction-user-defined-type"></a>ユーザー定義型の分数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パック [](https://nuget.org/packages/)


フォームの有理数を表し `p/q` ます。 Integer `p` は組の最初の要素で、 `q` は組の2番目の要素です。

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a>名前付き項目

### <a name="numerator--int"></a>分子: [Int](xref:microsoft.quantum.lang-ref.int)

分数の分子。
### <a name="denominator--int"></a>分母: [Int](xref:microsoft.quantum.lang-ref.int)

分数/の分母