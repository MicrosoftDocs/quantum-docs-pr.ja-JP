---
uid: Microsoft.Quantum.Canon.Angle
title: Angle 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: 0528f21b2d9c98b6497e28741964e6497d4d0fb9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842051"
---
# <a name="angle-function"></a>Angle 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


の値が奇数の場合は1を返し、 `index` が偶数の場合は-1 を返し `index` ます。

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a>説明

値は、反転の角度を決定する特定の代入について、n 変数および関数の Rademacher-Walsh スペクトルの係数の符号に対応します。

## <a name="input"></a>入力

### <a name="index--int"></a>index: [Int](xref:microsoft.quantum.lang-ref.int)

整数としての入力割り当て (0 から 2 ^ n-1)



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

