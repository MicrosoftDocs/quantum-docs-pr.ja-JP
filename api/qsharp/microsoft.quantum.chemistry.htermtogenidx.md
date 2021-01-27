---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: 46745632e2f6bafad0d7359141522b84f48c039d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839616"
---
# <a name="htermtogenidx-function"></a>HTermToGenIdx 関数

名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Chemistry)

パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


データ形式の Hamiltonian term を `HTerm` GeneratorIndex に変換します。

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>入力

### <a name="term--hterm"></a>用語: [Hterm](xref:Microsoft.Quantum.Chemistry.HTerm)

形式でデータを入力 `HTerm` します。


### <a name="termtype--int"></a>termType: [Int](xref:microsoft.quantum.lang-ref.int)[]

GeneratorIndex に追加される追加情報。



## <a name="output--generatorindex"></a>出力: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

で表される Hamiltonian term と `term` 、によって追加された追加情報を表す GeneratorIndex `termType` 。