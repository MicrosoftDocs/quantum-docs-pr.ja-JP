---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 20916d8462288395384aa875bfae4f042ba6b6ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228255"
---
# <a name="realmod-function"></a>RealMod 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


2つの実数の間の剰余を計算します。

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a>入力

### <a name="value--double"></a>値: [Double](xref:microsoft.quantum.lang-ref.double)

の剰余を取得するための実数 ($ $x)。


### <a name="modulo--double"></a>剰余: [Double](xref:microsoft.quantum.lang-ref.double)

に関して $x $ の剰余を取得する実数。


### <a name="minvalue--double"></a>minValue: [Double](xref:microsoft.quantum.lang-ref.double)

この関数によって返される最小値。



## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>解説

この関数は、単位の円に関する実際の線をラップし、入力に対応する単位の円の角度を検索することによって、実数の剰余を計算します。
入力によって、 `minValue` 実際には、単位の円を切り取る場所が指定されます。