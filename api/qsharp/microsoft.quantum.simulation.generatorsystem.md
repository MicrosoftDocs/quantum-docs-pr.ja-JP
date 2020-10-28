---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: c03caf99b197410c7fa15021c8acaaf55a728781
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724562"
---
# <a name="generatorsystem-user-defined-type"></a>GeneratorSystem ユーザー定義型

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パック [](https://nuget.org/packages/)


Es のコレクションを表し `GeneratorIndex` ます。

このコレクションを1つのインデックス整数を使用して繰り返し処理します。コレクションのサイズは既知であると見なされます。

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a>解説

`GeneratorSystem`関数を使用すると、のインスタンスを簡単に定義でき <xref:microsoft.quantum.arrays.lookupfunction> ます。

## <a name="see-also"></a>参照

- [Microsoft. Quantum. LookupFunction](xref:Microsoft.Quantum.Arrays.LookupFunction)