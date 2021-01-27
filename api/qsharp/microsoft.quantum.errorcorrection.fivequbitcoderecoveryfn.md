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
# <a name="fivequbitcoderecoveryfn-function"></a>Fivvldb Bitcoderecoveryfn 関数

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


⟦5、1、3⟧量子コードのテーブル参照によって、エラーより隣人の測定値を適切なエラー修正の値にマップする関数を返します。

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a>出力: [Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

`RecoveryFn`より隣人の測定値を受け取り、 `Result[]` `Pauli[]` 検出されたエラーを修正する演算子を返す型の関数。

## <a name="remarks"></a>解説

Weight $1 $ のすべてのエラーを反復処理することで、合計で $ 3 を5倍にすることができます。これは、可能な非単純な syndromes です。
Id と共に、エラーのテーブルと対応するより隣人が構築されます。 5 qubit コードの場合、このテーブルは $X \_ 1: (0, 0, 0, 1); によって指定されます。X \_ 2: (1, 0, 0, 0);X \_ 3: (1, 1, 0, 0);X \_ 4: (0, 1, 1, 0);X \_ 5: (0, 0, 1, 1) $, $Z \_ 1: (1, 0, 1, 0);Z \_ 2: (0, 1, 0, 1);Z \_ 3: (0, 0, 1, 0);Z \_ 4: (1, 0, 0, 1);Z \_ 5: (0, 1, 0, 0) $ $Y _i $ $X _i $ および $Z _i $ syndromes を追加して取得します。 テーブル参照復旧の順序付けは、bitvectors を整数 (リトルエンディアンを使用) に変換することによって与えられます。

## <a name="see-also"></a>参照

- [Microsoft... ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)