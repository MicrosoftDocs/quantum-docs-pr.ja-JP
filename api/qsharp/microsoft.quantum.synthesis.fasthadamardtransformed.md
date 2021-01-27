---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: be54413ef2d3fdaf7ddc726bc0906adb4ec382ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855451"
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

## <a name="example"></a>例

```qsharp
FastHadamardTransformed([1, 1, 1, -1]); // [2, 2, 2, -2]
```