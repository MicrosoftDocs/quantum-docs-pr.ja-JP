---
uid: Microsoft.Quantum.Logical.Xor
title: Xor 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: 4a4af7f628ca64170e046584d9caffe7ceee3d56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848448"
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