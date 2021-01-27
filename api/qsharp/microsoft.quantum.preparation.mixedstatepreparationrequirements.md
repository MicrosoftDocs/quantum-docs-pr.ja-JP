---
uid: Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
title: MixedStatePreparationRequirements ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: MixedStatePreparationRequirements
qsharp.summary: Represents the number of qubits required in order to prepare a given mixed state.
ms.openlocfilehash: df57b7b43fc84f7ddf68392f6a2b7013225da730
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856928"
---
# <a name="mixedstatepreparationrequirements-user-defined-type"></a>MixedStatePreparationRequirements ユーザー定義型

名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定された混合状態を準備するために必要な qubits の数を表します。

```qsharp

newtype MixedStatePreparationRequirements = (NTotalQubits : Int, (NIndexQubits : Int, NGarbageQubits : Int));
```



## <a name="named-items"></a>名前付き項目

### <a name="ntotalqubits--int"></a>NTotalQubits: [Int](xref:microsoft.quantum.lang-ref.int)


### <a name="nindexqubits--int"></a>NIndexQubits: [Int](xref:microsoft.quantum.lang-ref.int)


### <a name="ngarbagequbits--int"></a>NGarbageQubits: [Int](xref:microsoft.quantum.lang-ref.int)



## <a name="see-also"></a>参照

- [PurifiedMixedState](xref:Microsoft.Quantum.PurifiedMixedState)