---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerGeneratorSystem
title: JordanWignerGeneratorSystem 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: 30da4129278f83633c2cc76489c7c81304a1f565
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713988"
---
# <a name="jordanwignergeneratorsystem-function"></a>JordanWignerGeneratorSystem 関数

名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)

パック [](https://nuget.org/packages/)


によって記述された Hamiltonian を `JWOptimizedHTerms` 、 `GeneratorSystem` `GeneratorIndex` このファイルで定義されている規則に従って表現したに変換します。

```qsharp
function JordanWignerGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>入力

### <a name="data--jwoptimizedhterms"></a>データ: [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)

形式の Hamiltonian の説明 `JWOptimizedHTerms` 。



## <a name="output--generatorsystem"></a>出力: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Hamiltonian の表現 `GeneratorSystem` 。