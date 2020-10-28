---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZ
title: _JWOptimizedZ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZ
qsharp.summary: Applies a Rz rotation, with a C-NOT trick to double phase in phase estimation.
ms.openlocfilehash: 8bbd4af0389a7b748be11dc50bacd2c178521adc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724632"
---
# <a name="_jwoptimizedz-operation"></a>_JWOptimizedZ 操作

名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Research.Chemistry)

パック [](https://nuget.org/packages/)


フェーズの推定で、C ではなく C の Rz を2つのフェーズに回転させます。

```qsharp
operation _JWOptimizedZ (angle : Double, parityQubit : Qubit, qubit : Qubit) : Unit
```


## <a name="input"></a>入力

### <a name="angle--double"></a>angle: [Double](xref:microsoft.quantum.lang-ref.double)

Rz の回転角度。


### <a name="parityqubit--qubit"></a>parityQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

タイム進化の符号を決定する qubit。


### <a name="qubit--qubit"></a>qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

