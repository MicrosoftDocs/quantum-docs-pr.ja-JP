---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: d632a7a12c9ebbebfbc7939f2b8a24de8ae1ba2a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827908"
---
# <a name="nearequalityfactd-function"></a>NearEqualityFactD 関数

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


古典的な浮動小数点値が、最小の許容範囲 (1e-10) までの予測値を持つことをアサートします。

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a>入力

### <a name="actual--double"></a>実際: [Double](xref:microsoft.quantum.lang-ref.double)

確認する数値。


### <a name="expected--double"></a>が必要です。 [Double](xref:microsoft.quantum.lang-ref.double)

予期される値。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

これは、 <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> $10 ^ $ のハードコーディングされたトレランスを使用した場合と同じです {-10} 。