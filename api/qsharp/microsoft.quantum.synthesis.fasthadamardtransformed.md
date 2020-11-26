---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 3e48701f22ddf154721355866e15a85fca0bc7df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203095"
---
# <a name="fasthadamardtransformed-function"></a>FastHadamardTransformed 関数

名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


{-1,1}Yates のメソッドを使用して、エンコードのブール関数の変換を計算します。

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a>入力

### <a name="func--int"></a>func: [Int](xref:microsoft.quantum.lang-ref.int)[]

エンコードの真理表 {-1,1}



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)[]

関数のスペクトル係数