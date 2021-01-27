---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 56da313fabb20655ec358120b8d9b435e4971159
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848345"
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



## <a name="example"></a>例

```qsharp
    // Returns 3 π / 2.
    let y = RealMod(5.5 * PI(), 2.0 * PI(), 0.0);
    // Returns -1.2, since +3.6 and -1.2 are 4.8 apart on the real line,
    // which is a multiple of 2.4.
    let z = RealMod(3.6, 2.4, -1.2);
```

## <a name="remarks"></a>解説

この関数は、単位の円に関する実際の線をラップし、入力に対応する単位の円の角度を検索することによって、実数の剰余を計算します。
入力によって、 `minValue` 実際には、単位の円を切り取る場所が指定されます。