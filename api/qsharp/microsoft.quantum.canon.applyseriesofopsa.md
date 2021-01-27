---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: Applyシリーズ Ofopsa 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: 052cb52d4ee6500e60043ab7f808497058924afe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844667"
---
# <a name="applyseriesofopsa-operation"></a>Applyシリーズ Ofopsa 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Ops とそのターゲットの一覧を配列に順番に適用します。 (Adjoint)

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit is Adj
```


## <a name="input"></a>入力

### <a name="listofops--t--unit--is-adj"></a>listOfOps: ' t [] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 []

適用する操作のリスト。それぞれ t 配列を取得します。 これらは順番に適用され、最下位のインデックスが最初に適用されます。
各には、adjoint ファンクタが必要です。


### <a name="targets--int"></a>ターゲット: [Int](xref:microsoft.quantum.lang-ref.int)[] []

Op のターゲットを記述する入れ子になった配列。 各配列には、使用するインデックスを記述する整数のリストを含める必要があります。


### <a name="register--t"></a>register: t []

操作する qubit レジスタ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&



## <a name="example"></a>例

次の例では、Exp ([P\n Lix, P、pを使用して、0.5) を qubits 0、1//then X to qubits 2 let ops = [Exp ([P\n Lix, P\n の場合は、0.5, _)、ApplyToFirstQubitA (X, _)] に適用します。let インデックス = [[0, 1], [2]];Applyシリーズ Ofopsa (ops, インデックス, qubitArray);

## <a name="see-also"></a>参照

- [Microsoft. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)