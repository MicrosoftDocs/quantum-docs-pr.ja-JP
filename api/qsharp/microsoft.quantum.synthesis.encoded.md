---
uid: Microsoft.Quantum.Synthesis.Encoded
title: エンコードされた関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 803f35b9e7af547bc34f21de74684fba885bfda9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203180"
---
# <a name="encoded-function"></a>エンコードされた関数

名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


コーディングでの真実テーブルのエンコード {1,-1}

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a>入力

### <a name="table--bool"></a>テーブル: [Bool](xref:microsoft.quantum.lang-ref.bool)[]

真理値の配列としての真理値テーブル



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)[]

整数の配列としての真理値テーブル {1,-1}