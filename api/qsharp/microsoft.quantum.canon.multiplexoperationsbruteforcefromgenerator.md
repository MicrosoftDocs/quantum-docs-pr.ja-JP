---
uid: Microsoft.Quantum.Canon.MultiplexOperationsBruteForceFromGenerator
title: MultiplexOperationsBruteForceFromGenerator 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsBruteForceFromGenerator
qsharp.summary: >-
  Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 2a9bb083b121745bd556aac692d5dc85ffec3791
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715822"
---
# <a name="multiplexoperationsbruteforcefromgenerator-operation"></a>MultiplexOperationsBruteForceFromGenerator 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


N-qubit number 状態 $ \ket{j} $ によって制御されている場合に、_j $ $V を適用する $U $ に、乗算によって制御される数値演算を適用します。

$U = \ sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $。

```qsharp
operation MultiplexOperationsBruteForceFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a>入力

### <a name="unitarygenerator--intint---t--unit-adj--ctl"></a>unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl)

1番目の要素 `Int` が unitaries $ の数で、2番目の要素 `(Int -> ('T => () is Adj + Ctl))` が $ [0, n-1] $ の $ $j 整数を取得して、_j $ の $V の型指定操作を出力する関数です。


### <a name="index--littleendian"></a>index: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

数値の状態をリトルエンディアン形式でエンコードする $-qubit コントロールレジスタ $n ます。


### <a name="target--t"></a>ターゲット: \

_J $ act に $V する汎用 qubit レジスタ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&



## <a name="remarks"></a>解説

`coefficients` $ 2 ^ n $ 未満の値が指定されている場合、id 要素が埋め込まれます。 このバージョンは、n の制御されたユニタリ演算子によって直接実装されます。