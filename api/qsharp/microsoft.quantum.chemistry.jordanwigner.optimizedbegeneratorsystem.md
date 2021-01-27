---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem
title: OptimizedBEGeneratorSystem ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBEGeneratorSystem
qsharp.summary: Function that returns `OptimizedBETermIndex` data for term `n` given an integer `n`, together with the number of terms in the first `Int` and the sum of absolute-values of all term coefficients in the `Double`.
ms.openlocfilehash: eb274420a2fb813b1e34cea42bf1336e592feaae
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98837402"
---
# <a name="optimizedbegeneratorsystem-user-defined-type"></a>OptimizedBEGeneratorSystem ユーザー定義型

名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)

パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


`OptimizedBETermIndex` `n` 整数が指定された用語のデータを返す関数 `n` 。最初の用語の数 `Int` と、内のすべての項係数の絶対値の合計を返し `Double` ます。

```qsharp

newtype OptimizedBEGeneratorSystem = (Int, Double, (Int -> Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex));
```

