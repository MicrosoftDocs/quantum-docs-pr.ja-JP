---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 95b4c2df05f32cb937ec2cf421f43f2fdbf319da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710852"
---
# <a name="_deltaparitycnotbitstring-function"></a>_DeltaParityCNOTbitstring 関数

名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Research.Chemistry)

パック [](https://nuget.org/packages/)


の従来の処理手順 `ApplyDeltaParity` 。
これにより、2つの PQRS 間でパリティの違いを評価するためのコントロール qubits の一覧が計算されます。長さが偶数の用語。

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a>入力

### <a name="prevfermionicterm--int"></a>Prevterm: [Int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="nextfermionicterm--int"></a>Nextの Mimionicterm: [Int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--intbool"></a>出力: ([Int](xref:microsoft.quantum.lang-ref.int)、[Bool](xref:microsoft.quantum.lang-ref.bool)[])



## <a name="remarks"></a>解説

これは、用語の長さが偶数であることを前提としています。
任意の2つの用語間のパリティの違いについて、コントロールの一覧を計算します。
これは、入力リストが昇順で並べ替えられていることを前提としています。