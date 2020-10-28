---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 31b957a435c3f578bc03d432609cde14c2ef5ced
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714702"
---
# <a name="_computejordanwignerbitstring-function"></a>_ComputeJordanWignerBitString 関数

名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)

パック [](https://nuget.org/packages/)


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