---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZZTermToPauliMajIdx_
title: _ZZTermToPauliMajIdx_ 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZZTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: b18529182083ae6a905036ce6c00c3a0695ffccf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839051"
---
# <a name="_zztermtopaulimajidx_-function"></a>_ZZTermToPauliMajIdx_ 関数

名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)

パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Paulis の観点から、ZZ 用語を記述する GeneratorIndex を式 ' GeneratorIndex [] ' に変換します。

```qsharp
function _ZZTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a>入力

### <a name="term--generatorindex"></a>用語: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` ZZ 用語を表します。



## <a name="output--optimizedbetermindex"></a>出力: [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)

ZZ term を ' GeneratorIndex [] ' として表現します。