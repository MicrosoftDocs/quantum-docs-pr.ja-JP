---
uid: Microsoft.Quantum.Preparation.MixedStatePreparation
title: MixedStatePreparation ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: MixedStatePreparation
qsharp.summary: Represents a particular mixed state that can be prepared on an index and a garbage register.
ms.openlocfilehash: 7e5b6ca755aac19a31b7e27e32e934bb823b128e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842401"
---
# <a name="mixedstatepreparation-user-defined-type"></a>MixedStatePreparation ユーザー定義型

名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


インデックスとガベージレジスタで準備できる特定の混合状態を表します。

```qsharp

newtype MixedStatePreparation = (Requirements : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements, Norm : Double, Prepare : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a>名前付き項目

### <a name="requirements--mixedstatepreparationrequirements"></a>要件: [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)


### <a name="norm--double"></a>標準: [Double](xref:microsoft.quantum.lang-ref.double)


### <a name="prepare--littleendianqubitqubit--unit--is-adj--ctl"></a>準備: ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)、[qubit](xref:microsoft.quantum.lang-ref.qubit)[]、[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl



## <a name="see-also"></a>参照

- [PurifiedMixedState](xref:Microsoft.Quantum.PurifiedMixedState)