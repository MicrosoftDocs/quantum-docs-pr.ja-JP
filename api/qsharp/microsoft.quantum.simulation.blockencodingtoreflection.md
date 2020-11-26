---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: 742d4f5623c7c26810998f6c96e2c7b05cc452d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225348"
---
# <a name="blockencodingtoreflection-function"></a>BlockEncodingToReflection 関数

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


を等価のに変換 `BlockEncoding` `BLockEncodingReflection` します。

つまり、 `BlockEncoding` $H $ of 演算子をエンコードする $U $ という文字列を指定した場合は、 `BlockEncodingReflection` 同じ演算子をエンコードする $U ' $ に変換しますが $U ' ^ ダガー = U ' $ も満たされます。
これにより、$U $ の補助レジスタのサイズが 1 qubit だけ増加します。

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a>入力

### <a name="blockencoding--blockencoding"></a>blockEncoding: [Blockencoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)

リフレクションに変換される、$U の ' $ ' という1つの `BlockEncoding` を指定します。



## <a name="output--blockencodingreflection"></a>出力: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

$U ' $ はレジスタに対して共同で動作し、 `a` `s` $H $ をブロックエンコードし $U ' ^ ダガー = U ' $ を満たすことができます。

## <a name="remarks"></a>解説

これにより、$U $ の補助レジスタのサイズが 1 qubit だけ増加します。

## <a name="references"></a>リファレンス

- Hamiltonian シミュレーション Qubitization Guang Hao Low、Isaac L. 語 https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>参照

- [Microsoft. クォンタム. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [BlockEncodingReflection です。](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)