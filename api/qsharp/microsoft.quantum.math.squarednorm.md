---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 72ae8266492bef64eaec34cd70c5fe725ee1e8c9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848209"
---
# <a name="squarednorm-function"></a>SquaredNorm 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


ベクターの2乗値を返します。

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a>説明

ベクターの2乗を返します。つまり、入力 $ \vec{x} $ を指定すると、$ \ sum_i x_i ^ 2 $ が返されます。

## <a name="input"></a>入力

### <a name="array--double"></a>array: [Double](xref:microsoft.quantum.lang-ref.double)[]

2乗値が返されるベクトル。



## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)

の2乗の二乗 `array` 。