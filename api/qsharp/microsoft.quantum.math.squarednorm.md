---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 4165a761753f336cb7b94ad36b11ac324ad4e5c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725024"
---
# <a name="squarednorm-function"></a>SquaredNorm 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パック [](https://nuget.org/packages/)


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