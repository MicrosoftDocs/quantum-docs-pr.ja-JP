---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements
title: PurifiedMixedStateRequirements 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateRequirements
qsharp.summary: Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".
ms.openlocfilehash: 9b8861a4112c4e6c9db994339353c771a3de81a6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229989"
---
# <a name="purifiedmixedstaterequirements-function"></a>PurifiedMixedStateRequirements 関数

名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


によって返された操作を適用するために割り当てる必要がある qubits の合計数を返し @"microsoft.quantum.preparation.purifiedmixedstate" ます。

```qsharp
function PurifiedMixedStateRequirements (targetError : Double, nCoefficients : Int) : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
```


## <a name="input"></a>入力

### <a name="targeterror--double"></a>targetError: [Double](xref:microsoft.quantum.lang-ref.double)

ターゲットエラー $ \ イプシロン $。


### <a name="ncoefficients--int"></a>n 係数: [Int](xref:microsoft.quantum.lang-ref.int)

混合状態を準備するときに指定する係数の数。



## <a name="output--mixedstatepreparationrequirements"></a>出力: [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)

合計で必要とされる qubits の数、および関数によって使用される各インデックスとガベージレジスタについての説明 @"microsoft.quantum.preparation.purifiedmixedstate" 。

## <a name="see-also"></a>参照

- [PurifiedMixedState の準備](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)