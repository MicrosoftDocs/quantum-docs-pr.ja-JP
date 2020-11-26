---
uid: Microsoft.Quantum.Math.ModulusI
title: ModulusI 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6bbb3877b93e1fc6b38f85a716ba617311c7cfba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227779"
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

この関数は、演算子が `%` C# および Q # で動作する方法とは異なり、 `modulus - 1` 値が負の場合でも、結果は常に 0 ~ の正の整数になります。