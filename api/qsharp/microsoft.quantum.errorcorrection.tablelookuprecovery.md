---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: TableLookupRecovery 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: e4136add99ab7fb6904d7cac3c7f3e5076cc3176
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213669"
---
# <a name="tablelookuprecovery-function"></a><span data-ttu-id="073f7-102">TableLookupRecovery 関数</span><span class="sxs-lookup"><span data-stu-id="073f7-102">TableLookupRecovery function</span></span>

<span data-ttu-id="073f7-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="073f7-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="073f7-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="073f7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="073f7-105">指定された qubits のレジスタに対する P# li 操作の特定のテーブルに対して、この関数は、型のオブジェクトを返します。このオブジェクトには、 `RecoveryFn` 指定された Pan li 操作の配列に対してテーブル参照のデコードを実行するために必要なすべての情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="073f7-105">For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.</span></span>

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a><span data-ttu-id="073f7-106">入力</span><span class="sxs-lookup"><span data-stu-id="073f7-106">Input</span></span>

### <a name="table--pauli"></a><span data-ttu-id="073f7-107">テーブル: [P# li](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="073f7-107">table : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="073f7-108">指定された qubit レジスタで動作する P# li 操作のテーブル</span><span class="sxs-lookup"><span data-stu-id="073f7-108">Table of Pauli operations that operate on a given qubit register</span></span>



## <a name="output--recoveryfn"></a><span data-ttu-id="073f7-109">出力: [Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="073f7-109">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="073f7-110">型のオブジェクト `RecoveryFn` 。つまり、 `Syndrome -> Pauli[]` 特定のより隣人配列に関連付けられているマップで、対応する p li 修正操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="073f7-110">An object of type `RecoveryFn`, i.e., a map `Syndrome -> Pauli[]` that associates with a given syndrome array a corresponding Pauli correction operation.</span></span>