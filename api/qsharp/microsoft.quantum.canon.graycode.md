---
uid: Microsoft.Quantum.Canon.GrayCode
title: グレーのコード関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: fc673ae21a952788b5beb74c1bad94ee9fe54480
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716163"
---
# <a name="graycode-function"></a>グレーのコード関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


グレーのコードシーケンスを作成します

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a>入力

### <a name="n--int"></a>n: [Int](xref:microsoft.quantum.lang-ref.int)

ビット数



## <a name="output--intint"></a>出力: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []

タプルの配列。 組の最初の値は、タプル内のグレーのコードシーケンスの2番目の値の値で、次の値を取得するために現在の値を変更する位置です。