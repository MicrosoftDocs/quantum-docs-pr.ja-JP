---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: bada0dcc54d2a8d67cf7383d7153c7f46a4a8415
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847259"
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

## <a name="references"></a>References

- Hamiltonian シミュレーション Qubitization Guang Hao Low、Isaac L. 語 https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>参照

- [Microsoft. クォンタム. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [BlockEncodingReflection です。](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)