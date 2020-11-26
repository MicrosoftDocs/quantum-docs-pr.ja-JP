---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: ecbc66a8851f23187e0c0ea53ce121442323733b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227303"
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