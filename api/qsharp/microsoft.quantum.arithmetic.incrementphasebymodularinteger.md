---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger
title: IncrementPhaseByModularInteger 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 6a39ce49dfa28c1f1cbe6b29e526144c3ac19e53
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222883"
---
# <a name="incrementphasebymodularinteger-operation"></a>IncrementPhaseByModularInteger 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


整数定数によって、qubit レジスタのモジュール単位インクリメントを実行します。

```qsharp
operation IncrementPhaseByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

$ `increment` `modulus` と `target` $y $ によってエンコードされた整数を $N $a $ を意味します。
その後、次の変換が実行されます。 \begin{align} \ket{y} \ mapare \ket{(y + a) \ 演算子名 {mod} N} \end{align} 整数は、QFT ではリトルエンディアン形式でエンコードされます。

## <a name="input"></a>入力

### <a name="increment--int"></a>increment: [Int](xref:microsoft.quantum.lang-ref.int)

$Y $ に加算する $ $a 整数値。


### <a name="modulus--int"></a>剰余: [Int](xref:microsoft.quantum.lang-ref.int)

Mods $y + a $ の整数 $N $。


### <a name="target--phaselittleendian"></a>ターゲット: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

$ が追加さ $a れる、フェーズでエンコードされたリトルエンディアン形式の整数 $y $ `increment` 。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

は `target` 、の最上位ビットが0に設定されていることを前提としています。
また、target の値が $N $ 未満であることを前提としています。

回路図と説明については、 [arXiv: quant-ph/0205095v3 のページ 5](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5)の図5を参照してください。

## <a name="see-also"></a>参照

- [IncrementByModularInteger です。](xref:Microsoft.Quantum.Arithmetic.IncrementByModularInteger)