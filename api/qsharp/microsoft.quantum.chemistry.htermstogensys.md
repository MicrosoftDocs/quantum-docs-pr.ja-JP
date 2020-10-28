---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: b78ff393fa1e51c38028ef56bb3c61b8f1d5e478
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714842"
---
# <a name="htermstogensys-function"></a>HTermsToGenSys 関数

名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Chemistry)

パック [](https://nuget.org/packages/)


データ形式の Hamiltonian を `HTerm[]` GeneratorSystem に変換します。

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>入力

### <a name="data--hterm"></a>データ: [Hterm](xref:Microsoft.Quantum.Chemistry.HTerm)[]

形式でデータを入力 `HTerm[]` します。


### <a name="termtype--int"></a>termType: [Int](xref:microsoft.quantum.lang-ref.int)[]

GeneratorIndex に追加される追加情報。



## <a name="output--generatorsystem"></a>出力: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

入力によって表される Hamiltonian を表す GeneratorSystem `data` 。