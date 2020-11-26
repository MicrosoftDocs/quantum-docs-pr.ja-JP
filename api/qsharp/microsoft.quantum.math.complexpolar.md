---
uid: Microsoft.Quantum.Math.ComplexPolar
title: ComplexPolar ユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: a4f3a7b6ffa73271d7ac9674d8c718f6f09c0291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210983"
---
# <a name="complexpolar-user-defined-type"></a>ComplexPolar ユーザー定義型

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


極座標形式の複素数を表します。

複素数の極座標表現は $c = r e ^ {i t} $ です。

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a>名前付き項目

### <a name="magnitude--double"></a>マグニチュード: [Double](xref:microsoft.quantum.lang-ref.double)

$C $ の $0 $r の絶対値。
### <a name="argument--double"></a>引数: [Double](xref:microsoft.quantum.lang-ref.double)

フェーズ $t、$c $ の \mathbb R $。