---
uid: Microsoft.Quantum.Synthesis.Encoded
title: エンコードされた関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 6b9d21969ee90f3928b65a1c97a5b0f15157e381
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725206"
---
# <a name="encoded-function"></a>エンコードされた関数

名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)

パック [](https://nuget.org/packages/)


コーディングでの真実テーブルのエンコード {1,-1}

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a>入力

### <a name="table--bool"></a>テーブル: [Bool](xref:microsoft.quantum.lang-ref.bool)[]

真理値の配列としての真理値テーブル



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)[]

整数の配列としての真理値テーブル {1,-1}