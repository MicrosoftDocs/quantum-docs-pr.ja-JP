---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsC
title: Applyシリーズ Ofopsc 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsC
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Controlled)
ms.openlocfilehash: 308256833dc607f685e3a5f2278e374cf3b6ce22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844642"
---
# <a name="applyseriesofopsc-operation"></a>Applyシリーズ Ofopsc 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Ops とそのターゲットの一覧を配列に順番に適用します。 た

```qsharp
operation ApplySeriesOfOpsC<'T> (listOfOps : ('T[] => Unit is Ctl)[], targets : Int[][], register : 'T[]) : Unit is Ctl
```


## <a name="input"></a>入力

### <a name="listofops--t--unit--is-ctl"></a>listOfOps: ' t [] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl []

適用する操作のリスト。それぞれ t 配列を取得します。 これらは順番に適用され、最下位のインデックスが最初に適用されます。
各には、管理されたファンクタが必要です。


### <a name="targets--int"></a>ターゲット: [Int](xref:microsoft.quantum.lang-ref.int)[] []

Op のターゲットを記述する入れ子になった配列。 各配列には、使用するインデックスを記述する整数のリストを含める必要があります。


### <a name="register--t"></a>register: t []

操作する qubit レジスタ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&



## <a name="example"></a>例

次のようになります。 Exp ([P\n Lix, P、p、p、および 0.5) を qubits 0、1//then X to qubits 2 let ops = [Exp ([P\n Lix, Pて Liy], 0.5, _)、ApplyToFirstQubitC (X, _)] です。let インデックス = [[0, 1], [2]];Applyシリーズ Ofopsc (ops, インデックス, qubitArray);

## <a name="see-also"></a>参照

- [Microsoft. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)