---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: 73324a48cc4b42de0d5d8618ad9e833d289125f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714856"
---
# <a name="htermstogenidx-function"></a>HTermsToGenIdx 関数

名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Chemistry)

パック [](https://nuget.org/packages/)


インデックスをデータ形式の Hamiltonian term から `HTerm[]` GeneratorIndex に変換します。

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>入力

### <a name="data--hterm"></a>データ: [Hterm](xref:Microsoft.Quantum.Chemistry.HTerm)[]

形式でデータを入力 `HTerm[]` します。


### <a name="termtype--int"></a>termType: [Int](xref:microsoft.quantum.lang-ref.int)[]

GeneratorIndex に追加される追加情報。


### <a name="idx--int"></a>idx: [Int](xref:microsoft.quantum.lang-ref.int)

Hamiltonian の用語のインデックス



## <a name="output--generatorindex"></a>出力: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

で表される Hamiltonian term と `data[idx]` 、によって追加された追加情報を表す GeneratorIndex `termType` 。