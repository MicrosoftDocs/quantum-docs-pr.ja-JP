---
uid: Microsoft.Quantum.Math.ModulusL
title: ModulusL 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: e7e692059051fde295634c37892ec54e2cf1b095
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725099"
---
# <a name="modulusl-function"></a>ModulusL 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パック [](https://nuget.org/packages/)


剰余の正規の residue を計算 `value` `modulus` します。

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a>入力

### <a name="value--bigint"></a>値: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Residue が計算される値


### <a name="modulus--bigint"></a>剰余: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Residues の取得に使用する剰余。正の整数である必要があります



## <a name="output--bigint"></a>出力: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

0から、 `modulus - 1` `value - r` 剰余で割り切れた整数 $r $

## <a name="remarks"></a>解説

この関数は、演算子が `%` C# および Q # で動作する方法とは異なり、 `modulus - 1` 値が負の場合でも、結果は常に 0 ~ の正の整数になります。