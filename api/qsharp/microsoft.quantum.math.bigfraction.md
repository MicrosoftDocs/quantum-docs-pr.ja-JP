---
uid: Microsoft.Quantum.Math.BigFraction
title: ユーザー定義型の BigFraction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1c9b9e350c4fa3664b2c66da05149005b1170ec3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211085"
---
# <a name="bigfraction-user-defined-type"></a>ユーザー定義型の BigFraction

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


フォームの有理数を表し `p/q` ます。 Integer `p` は組の最初の要素で、 `q` は組の2番目の要素です。

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a>名前付き項目

### <a name="numerator--bigint"></a>分子: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

分数の分子。
### <a name="denominator--bigint"></a>分母: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

分数/の分母