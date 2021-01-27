---
uid: Microsoft.Quantum.Math.ComplexPolar
title: ComplexPolar ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 174e75b82a3ee740cd4d07e5bcd091de65bbc6b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847345"
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