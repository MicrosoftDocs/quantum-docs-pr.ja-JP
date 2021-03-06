---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 82b5e433f79c93c640b89e6365e5f468bacd892e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839529"
---
# <a name="_computejordanwignerbitstring-function"></a>_ComputeJordanWignerBitString 関数

名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)

パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


2つの作成/annihilation 演算子を使用して、fermionic 演算子内のインデックスに対して、よりも多くの型の配列の Z 成分を計算します。

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a>入力

### <a name="nfermions--int"></a>Nの Mi: [Int](xref:microsoft.quantum.lang-ref.int)

システムに搭載されているアドオンの数。


### <a name="idxfermions--int"></a>Idxが Mion: [Int](xref:microsoft.quantum.lang-ref.int)[]

fermionic 演算子のインデックス。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)[]

`Bool[]` `true` の適用先となる bitstring `PauliZ` 。

## <a name="example"></a>例

let bitString = _ComputeJordanWignerBitString (6, [0, 1, 2, 6]);bitString は [false、false、false、true、true、true、false] です。