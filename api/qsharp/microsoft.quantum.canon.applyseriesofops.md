---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: Applyシリーズ Ofops 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: b8810e7d31689046e72905195a3a25ef80fc8d67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218004"
---
# <a name="applyseriesofops-operation"></a>Applyシリーズ Ofops 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Ops とそのターゲットの一覧を配列に順番に適用します。

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a>入力

### <a name="listofops--t--unit-"></a>listOfOps: ' t [] => [Unit](xref:microsoft.quantum.lang-ref.unit) []

適用する操作のリスト。それぞれ t 配列を取得します。 これらは順番に適用され、最下位のインデックスが最初に適用されます。


### <a name="targets--int"></a>ターゲット: [Int](xref:microsoft.quantum.lang-ref.int)[] []

Op のターゲットを記述する入れ子になった配列。 各配列には、使用するインデックスを記述する整数のリストを含める必要があります。


### <a name="register--t"></a>register: t []

操作する qubit レジスタ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&



## <a name="see-also"></a>参照

- [Microsoft. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)