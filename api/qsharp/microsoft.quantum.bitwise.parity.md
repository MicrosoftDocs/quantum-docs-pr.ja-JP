---
uid: Microsoft.Quantum.Bitwise.Parity
title: パリティ関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Parity
qsharp.summary: Returns the bitwise PARITY of an integer (1 if its binary representation contains odd number of ones and 0 otherwise).
ms.openlocfilehash: b34ef36b0336ec1dea7fdbd878c6d695b38d623e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842123"
---
# <a name="parity-function"></a>パリティ関数

名前空間: [Microsoft. Quantum. ビット](xref:Microsoft.Quantum.Bitwise)処理

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


整数のビットごとのパリティを返します (そのバイナリ表現に奇数の数値が含まれている場合は1、それ以外の場合は 0)。

```qsharp
function Parity (a : Int) : Int
```


## <a name="input"></a>入力

### <a name="a--int"></a>a: [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)



## <a name="example"></a>例

```qsharp
let a = 248;
let x = Parity(a); // x : Int = 1.
```