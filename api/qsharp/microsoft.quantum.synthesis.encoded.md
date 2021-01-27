---
uid: Microsoft.Quantum.Synthesis.Encoded
title: エンコードされた関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 44f6b247e6bfab7b55c46146cb63f8b6d219955b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855497"
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

## <a name="example"></a>例

```qsharp
Encoded([false, false, false, true]); // [1, 1, 1, -1]
```