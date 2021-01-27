---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: StateGenerator ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: b4f6c3ca28e2976b6a0d58f4ef25ea943de9811e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854870"
---
# <a name="stategenerator-user-defined-type"></a>StateGenerator ユーザー定義型

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


指定された入力をシーケンシャルな分類子に準備する操作を記述します。

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a>名前付き項目

### <a name="nqubits--int"></a>NQubits: [Int](xref:microsoft.quantum.lang-ref.int)

エンコードされた入力が定義されている qubits の数。
### <a name="prepare--littleendian--unit--is-adj--ctl"></a>準備: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  が形容詞 + Ctl である

Qubits のリトルエンディアンレジスタでエンコードされた入力を準備する操作 `NQubits` 。