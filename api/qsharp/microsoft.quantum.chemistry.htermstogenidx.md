---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: 84dc132528f8fd1c45fb2f7345111a05626ee686
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839625"
---
# <a name="htermstogenidx-function"></a>HTermsToGenIdx 関数

名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Chemistry)

パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


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