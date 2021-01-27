---
uid: Microsoft.Quantum.Math.ModulusL
title: ModulusL 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6be2edb052cf55f8e8465c76b5dcadeb61ff11ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842743"
---
# <a name="modulusl-function"></a>ModulusL 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

この関数の動作は、 `%` C# および Q # での演算子の動作によって異なります。結果は、 `modulus - 1` 値が負の場合でも、常に 0 ~ の範囲の負でない整数になります。