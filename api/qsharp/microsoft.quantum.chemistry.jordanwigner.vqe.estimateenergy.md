---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateEnergy
title: EstimateEnergy 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateEnergy
qsharp.summary: Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.
ms.openlocfilehash: 52e527a68818c80f93bc177d3563064fd0f2aea3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713750"
---
# <a name="estimateenergy-operation"></a>EstimateEnergy 操作

名前空間: [JordanWigner です。 VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

パック [](https://nuget.org/packages/)


個々の Jordan-Wigner の条件によって得たエネルギーを合計することによって、分子のエネルギーを見積もります。

```qsharp
operation EstimateEnergy (jwHamiltonian : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, nSamples : Int) : Double
```


## <a name="description"></a>説明

この操作は、スピンアップダウンインデックス作成規則に暗黙的に依存します。

## <a name="input"></a>入力

### <a name="jwhamiltonian--jordanwignerencodingdata"></a>Jwhamiltonwh: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)

Jordan-Wigner Hamiltonian。


### <a name="nsamples--int"></a>nSamples: [Int](xref:microsoft.quantum.lang-ref.int)

期待される用語の推定に使用するサンプルの数。



## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)

分子の予測エネルギー