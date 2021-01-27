---
uid: Microsoft.Quantum.Canon.GrayCode
title: グレーのコード関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: 0a9a19685f0511c44942df7d0bc8d257ad6b18c6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840494"
---
# <a name="graycode-function"></a>グレーのコード関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


グレーのコードシーケンスを作成します

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a>入力

### <a name="n--int"></a>n: [Int](xref:microsoft.quantum.lang-ref.int)

ビット数



## <a name="output--intint"></a>出力: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []

タプルの配列。 組の最初の値は、タプル内のグレーのコードシーケンスの2番目の値の値で、次の値を取得するために現在の値を変更する位置です。

## <a name="example"></a>例

```qsharp
GrayCode(2); // [(0, 0),(1, 1),(3, 0),(2, 1)]
```