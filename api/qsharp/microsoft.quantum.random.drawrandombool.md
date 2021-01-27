---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 7c13f8305756421b8d07baf22ff87764efac0418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853689"
---
# <a name="drawrandombool-operation"></a>DrawRandomBool 操作

名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


成功の確率が指定された場合、は、指定された確率で true である単一のベルヌーイ評価を返します。

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a>入力

### <a name="successprobability--double"></a>successProbability: [Double](xref:microsoft.quantum.lang-ref.double)

が返される確率 `true` 。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` 確率 `successProbability` と確率を使用 `false` `1.0 - successProbability` します。

## <a name="example"></a>例

次の Q # スニペットのサンプルでは、バイアスをかけるコインからフリップします。

```qsharp
let flips = DrawMany(DrawRandomBool, 10, 0.6);
```