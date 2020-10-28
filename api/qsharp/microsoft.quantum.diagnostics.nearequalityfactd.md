---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 5b55f515b27667071218a3f604ef703a6a15206d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712649"
---
# <a name="nearequalityfactd-function"></a>NearEqualityFactD 関数

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


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