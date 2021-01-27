---
uid: Microsoft.Quantum.Math.ModulusI
title: ModulusI 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 7bad044db9e2229c85cb3909dc4802bceaee6382
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847304"
---
# <a name="modulusi-function"></a>ModulusI 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


剰余の正規の residue を計算 `value` `modulus` します。

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a>入力

### <a name="value--int"></a>値: [Int](xref:microsoft.quantum.lang-ref.int)

Residue が計算される値


### <a name="modulus--int"></a>剰余: [Int](xref:microsoft.quantum.lang-ref.int)

Residues の取得に使用する剰余。正の整数である必要があります



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

0から、 `modulus - 1` `value - r` 剰余で割り切れた整数 $r $

## <a name="remarks"></a>解説

この関数の動作は、 `%` C# および Q # での演算子の動作によって異なります。結果は、 `modulus - 1` 値が負の場合でも、常に 0 ~ の範囲の負でない整数になります。