---
uid: Microsoft.Quantum.Logical.Xor
title: Xor 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: afb94bd1fd0b791a9a7d84bc28b0cc2baf9a0938
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197094"
---
# <a name="xor-function"></a>Xor 関数

名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


2つの値のブール型の排他的和を返します。

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>入力

### <a name="a--bool"></a>a: [Bool](xref:microsoft.quantum.lang-ref.bool)

考慮される最初の値。


### <a name="b--bool"></a>b: [Bool](xref:microsoft.quantum.lang-ref.bool)

考慮する2番目の値。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` とのいずれかだけがの `a` 場合 `b` にのみ `true` 。