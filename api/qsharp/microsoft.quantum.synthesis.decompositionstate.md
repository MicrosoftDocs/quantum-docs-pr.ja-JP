---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: DecompositionState ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: 0547c04828a80b4f696cc17e13c8cc57d0379f96
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725211"
---
# <a name="decompositionstate-user-defined-type"></a>DecompositionState ユーザー定義型

名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)

パック [](https://nuget.org/packages/)


変数インデックスに基づく分解中の状態

```qsharp

newtype DecompositionState = (Perm : Int[], Lfunctions : (BigInt, Int)[], Rfunctions : (BigInt, Int)[]);
```



## <a name="named-items"></a>名前付き項目

### <a name="perm--int"></a>Perm: [Int](xref:microsoft.quantum.lang-ref.int)[]


### <a name="lfunctions--bigintint"></a>Lfunctions: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int)) []


### <a name="rfunctions--bigintint"></a>Rfunctions: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int)) []



## <a name="description"></a>説明

状態は、現在の順列と、左側の制御ゲートに対して現在生成されている関数を保持し、右側の制御ゲートを制御します。