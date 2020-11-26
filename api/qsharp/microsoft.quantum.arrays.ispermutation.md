---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: IsPermutation 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 144f683818b5d75de5b075328365d3e994de29d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220928"
---
# <a name="ispermutation-function"></a>IsPermutation 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定された配列が順列を表す場合にのみ、true を出力します。

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a>説明

長さの配列を指定した場合は `array` `n` 、の各整数がに `0` `n - 1` 1 回だけ出現し `array` 、 `array` 要素の順列として解釈できる場合にのみ、true を返し `n` ます。

## <a name="input"></a>入力

### <a name="permuation--int"></a>permuation: [Int](xref:microsoft.quantum.lang-ref.int)[]

順列を表すか、または表現できない配列。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)



## <a name="remarks"></a>解説

長さゼロの配列は、普通の順列です。