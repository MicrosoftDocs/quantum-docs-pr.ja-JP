---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: ca22b090f2b2613f07caef698941ea608374ab1e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203316"
---
# <a name="applytransposition-operation"></a>ApplyTransposition 操作

名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

この操作では、インデックスの振幅を、 `a` `b` 長さ $n $ の指定した状態ベクトルのインデックス位置の振幅でスワップし `register` ます。  が `a` に等しい場合 `b` 、状態ベクトルは変更されません。

## <a name="input"></a>入力

### <a name="a--int"></a>a: [Int](xref:microsoft.quantum.lang-ref.int)

最初のインデックス (0 ~ $ 2 ^ n-$1 の値である必要があります)


### <a name="b--int"></a>b: [Int](xref:microsoft.quantum.lang-ref.int)

2番目のインデックス (0 ~ $ 2 ^ n-$1 の値である必要があります)


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

転調が適用される $n $ qubits の一覧。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

