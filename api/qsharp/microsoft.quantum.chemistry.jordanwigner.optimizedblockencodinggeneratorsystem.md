---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBlockEncodingGeneratorSystem
title: OptimizedBlockEncodingGeneratorSystem 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBlockEncodingGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.
ms.openlocfilehash: c3e48cb5dde36b694a5b16f25333cf0dad6c0f61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713895"
---
# <a name="optimizedblockencodinggeneratorsystem-function"></a>OptimizedBlockEncodingGeneratorSystem 関数

名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)

パック [](https://nuget.org/packages/)


によって記述された Hamiltonian を、 `JWOptimizedHTerms` `GeneratorSystem` p li の観点から表現されたに変換 `GeneratorIndex` します。

```qsharp
function OptimizedBlockEncodingGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem
```


## <a name="input"></a>入力

### <a name="data--jwoptimizedhterms"></a>データ: [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)

形式の Hamiltonian の説明 `JWOptimizedHTerms` 。



## <a name="output--optimizedbegeneratorsystem"></a>出力: [OptimizedBEGeneratorSystem](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem)

Hamiltonian の表現 `GeneratorSystem` 。