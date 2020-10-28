---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 2b84e92d08a3baad2552780cae91f447830cac82
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725183"
---
# <a name="fasthadamardtransformed-function"></a>FastHadamardTransformed 関数

名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)

パック [](https://nuget.org/packages/)


{-1,1}Yates のメソッドを使用して、エンコードのブール関数の変換を計算します。

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a>入力

### <a name="func--int"></a>func: [Int](xref:microsoft.quantum.lang-ref.int)[]

エンコードの真理表 {-1,1}



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)[]

関数のスペクトル係数