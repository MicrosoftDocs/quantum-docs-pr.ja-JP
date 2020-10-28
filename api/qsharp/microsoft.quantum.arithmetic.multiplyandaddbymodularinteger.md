---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger
title: MultiplyAndAddByModularInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddByModularInteger
qsharp.summary: Performs a modular multiply-and-add by integer constants on a qubit register.
ms.openlocfilehash: 3f85f6aaea1d6f8095709c6f387322df7a5e047c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719810"
---
# <a name="multiplyandaddbymodularinteger-operation"></a>MultiplyAndAddByModularInteger 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パック [](https://nuget.org/packages/)


Qubit レジスタに対して、モジュールの乗算および加算による整数定数を実行します。

```qsharp
operation MultiplyAndAddByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, summand : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>説明

指定された剰余 $N $、定数乗数 $a $、および \ket{$y $ に対して、map $ $ \begin{align} \ket{x} \ket{b}/map\end{align} $ $ summand (b + a/cdot x) $ $ を実装します。

## <a name="input"></a>入力

### <a name="constmultiplier--int"></a>[型の型: Int](xref:microsoft.quantum.lang-ref.int)

各 basis 状態ラベルに追加する整数 $a $。


### <a name="modulus--int"></a>剰余: [Int](xref:microsoft.quantum.lang-ref.int)

に関して、加算と乗算が行われる剰余 $N $。


### <a name="multiplier--littleendian"></a>乗数: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

の各 basis 状態ラベルに値を追加する符号なし整数を表すクォンタムレジスタ `summand` 。


### <a name="summand--littleendian"></a>summand: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

この操作のターゲットとして使用する符号なし整数を表すクォンタムレジスタ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

- 回路図と説明については、arXiv のページ7の図6を参照してください [: quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)
- この操作は[Arxiv: quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)の CMULT (a) MOD (N) に対応します。

## <a name="see-also"></a>参照

- [MultiplyAndAddPhaseByModularInteger です。](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger)