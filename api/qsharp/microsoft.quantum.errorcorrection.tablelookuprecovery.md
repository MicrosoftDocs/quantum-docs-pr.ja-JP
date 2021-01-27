---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: TableLookupRecovery 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: 9f957155e42bb6b5163521171fcba5897f290335
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98824398"
---
# <a name="tablelookuprecovery-function"></a>TableLookupRecovery 関数

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定された qubits のレジスタに対する P# li 操作の特定のテーブルに対して、この関数は、型のオブジェクトを返します。このオブジェクトには、 `RecoveryFn` 指定された Pan li 操作の配列に対してテーブル参照のデコードを実行するために必要なすべての情報が含まれています。

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a>入力

### <a name="table--pauli"></a>テーブル: [P# li](xref:microsoft.quantum.lang-ref.pauli)[] []

指定された qubit レジスタで動作する P# li 操作のテーブル



## <a name="output--recoveryfn"></a>出力: [Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

型のオブジェクト `RecoveryFn` 。つまり、 `Syndrome -> Pauli[]` 特定のより隣人配列に関連付けられているマップで、対応する p li 修正操作を実行します。