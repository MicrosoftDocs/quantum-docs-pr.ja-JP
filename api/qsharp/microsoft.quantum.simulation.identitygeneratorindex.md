---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: IdentityGeneratorIndex 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: d2af2dafaf75a68546cb3f16c04cf4c7ee50c6ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724539"
---
# <a name="identitygeneratorindex-function"></a>IdentityGeneratorIndex 関数

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パック [](https://nuget.org/packages/)


Id の進化操作に対応する、ゼロ Hamiltonian () と一致するジェネレーターインデックスを返し `H = 0` ます。

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>入力

### <a name="idxterm--int"></a>idxTerm: [Int](xref:microsoft.quantum.lang-ref.int)

この入力は無視され、ユーザー定義型との一貫性のために定義されてい <xref:microsoft.quantum.simulation.generatorsystem> ます。



## <a name="output--generatorindex"></a>出力: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Hamiltonian $H = $0 での進化を表すジェネレーターインデックス。