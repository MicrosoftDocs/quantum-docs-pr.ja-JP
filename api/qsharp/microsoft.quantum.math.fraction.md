---
uid: Microsoft.Quantum.Math.Fraction
title: ユーザー定義型の分数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a56d28e34938729a8e4ffda5f870e0b6a25be017
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857513"
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