---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: すべての関数の関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: 8f5a2319b5839d0d9e47972389330dc16dffcaf0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713713"
---
# <a name="expandedcoefficients-function"></a>すべての関数の関数

名前空間: [JordanWigner です。 VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

パック [](https://nuget.org/packages/)


Jordan-Wigner 係数のコンパクト表現を拡張して、これらの用語と、それらの用語の間の一対一のマッピングを取得します。

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a>入力

### <a name="coeff--double"></a>係数: [Double](xref:microsoft.quantum.lang-ref.double)[]

Jordan-Wigner Hamiltonian データ構造体から読み取られる係数の配列。


### <a name="termtype--int"></a>termType: [Int](xref:microsoft.quantum.lang-ref.int)

Jordan-Wigner 用語の型。



## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)[]

係数の拡張された配列 (1 つの条件につき1つ)。