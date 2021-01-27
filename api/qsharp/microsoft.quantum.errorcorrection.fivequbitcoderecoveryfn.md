---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeRecoveryFn
title: Fivvldb Bitcoderecoveryfn 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeRecoveryFn
qsharp.summary: Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 94b6c12f31b0e6367151d0ebb225cff5f82915e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853125"
---
# <a name="fivequbitcoderecoveryfn-function"></a><span data-ttu-id="a1702-102">Fivvldb Bitcoderecoveryfn 関数</span><span class="sxs-lookup"><span data-stu-id="a1702-102">FiveQubitCodeRecoveryFn function</span></span>

<span data-ttu-id="a1702-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="a1702-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="a1702-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a1702-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a1702-105">⟦5、1、3⟧量子コードのテーブル参照によって、エラーより隣人の測定値を適切なエラー修正の値にマップする関数を返します。</span><span class="sxs-lookup"><span data-stu-id="a1702-105">Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="a1702-106">出力: [Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="a1702-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="a1702-107">`RecoveryFn`より隣人の測定値を受け取り、 `Result[]` `Pauli[]` 検出されたエラーを修正する演算子を返す型の関数。</span><span class="sxs-lookup"><span data-stu-id="a1702-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operators that corrects the detected error.</span></span>

## <a name="remarks"></a><span data-ttu-id="a1702-108">解説</span><span class="sxs-lookup"><span data-stu-id="a1702-108">Remarks</span></span>

<span data-ttu-id="a1702-109">Weight $1 $ のすべてのエラーを反復処理することで、合計で $ 3 を5倍にすることができます。これは、可能な非単純な syndromes です。</span><span class="sxs-lookup"><span data-stu-id="a1702-109">By iterating over all errors of weight $1$, we obtain a total of $3\times 5=15$ possible non-trivial syndromes.</span></span>
<span data-ttu-id="a1702-110">Id と共に、エラーのテーブルと対応するより隣人が構築されます。</span><span class="sxs-lookup"><span data-stu-id="a1702-110">Together with the identity, a table of error and corresponding syndrome is built up.</span></span> <span data-ttu-id="a1702-111">5 qubit コードの場合、このテーブルは $X \_ 1: (0, 0, 0, 1); によって指定されます。X \_ 2: (1, 0, 0, 0);X \_ 3: (1, 1, 0, 0);X \_ 4: (0, 1, 1, 0);X \_ 5: (0, 0, 1, 1) $, $Z \_ 1: (1, 0, 1, 0);Z \_ 2: (0, 1, 0, 1);Z \_ 3: (0, 0, 1, 0);Z \_ 4: (1, 0, 0, 1);Z \_ 5: (0, 1, 0, 0) $ $Y _i $ $X _i $ および $Z _i $ syndromes を追加して取得します。</span><span class="sxs-lookup"><span data-stu-id="a1702-111">For the 5 qubit code this table is given by: $X\_1: (0,0,0,1); X\_2: (1,0,0,0); X\_3: (1,1,0,0); X\_4: (0,1,1,0); X\_5: (0,0,1,1)$, $Z\_1: (1,0,1,0); Z\_2: (0,1,0,1); Z\_3: (0,0,1,0); Z\_4: (1,0,0,1); Z\_5: (0,1,0,0)$ with $Y_i$ obtained by adding the $X_i$ and $Z_i$ syndromes.</span></span> <span data-ttu-id="a1702-112">テーブル参照復旧の順序付けは、bitvectors を整数 (リトルエンディアンを使用) に変換することによって与えられます。</span><span class="sxs-lookup"><span data-stu-id="a1702-112">Note that the ordering in the table lookup recovery is given by converting the bitvectors to integers (using little endian).</span></span>

## <a name="see-also"></a><span data-ttu-id="a1702-113">参照</span><span class="sxs-lookup"><span data-stu-id="a1702-113">See Also</span></span>

- [<span data-ttu-id="a1702-114">Microsoft... ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="a1702-114">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)