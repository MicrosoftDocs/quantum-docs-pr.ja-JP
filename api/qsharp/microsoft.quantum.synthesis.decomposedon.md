---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: b033723a50fb85e77c9d4baec1f94231327e9b25
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725220"
---
# <a name="decomposedon-function"></a>DecomposedOn 関数

名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)

パック [](https://nuget.org/packages/)


分解され変数の順列の並べ替え

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a>説明

順列 $ \ pi $ ( `perm` ) とインデックス $i $ () に指定されてい `index` ます。このメソッドは3つの順列 $ ((\ pi_l, \ pi_r), \ pi ') $ を返します。 $ \ pi_l $ と $ \ pi_r $ のイメージでは、要素内の要素のビットを変更しないようにして、$-pi ' $ のイメージは、要素内でビット $i $ を変更しないようにします。

## <a name="input"></a>入力

### <a name="perm--int"></a>perm: [Int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="index--int"></a>index: [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--intintint"></a>出力: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])

