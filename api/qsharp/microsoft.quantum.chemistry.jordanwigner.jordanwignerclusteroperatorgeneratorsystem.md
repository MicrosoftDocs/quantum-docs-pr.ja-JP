---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerClusterOperatorGeneratorSystem
title: JordanWignerClusterOperatorGeneratorSystem 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerClusterOperatorGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: 685ae508e7c2f04ff0de48ecc0a39e80d6d9f2cb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839002"
---
# <a name="jordanwignerclusteroperatorgeneratorsystem-function"></a>JordanWignerClusterOperatorGeneratorSystem 関数

名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)

パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


によって記述された Hamiltonian を `JWOptimizedHTerms` 、 `GeneratorSystem` `GeneratorIndex` このファイルで定義されている規則に従って表現したに変換します。

```qsharp
function JordanWignerClusterOperatorGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>入力

### <a name="data--jordanwignerinputstate"></a>データ: [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]

形式の Hamiltonian の説明 `JWOptimizedHTerms` 。



## <a name="output--generatorsystem"></a>出力: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Hamiltonian の表現 `GeneratorSystem` 。