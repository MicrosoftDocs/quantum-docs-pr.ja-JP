---
uid: Microsoft.Quantum.Math.ComplexPolar
title: ComplexPolar ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 0c18c3f02cb036f22a68b6e4b46fd19049dc34cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709648"
---
# <a name="complexpolar-user-defined-type"></a>ComplexPolar ユーザー定義型

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パック [](https://nuget.org/packages/)


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