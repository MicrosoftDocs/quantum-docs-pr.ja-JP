---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: BlockEncodingByLCU 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 04738aa54ce8b719b05954824e3553388a995df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724861"
---
# <a name="blockencodingbylcu-function"></a>BlockEncodingByLCU 関数

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パック [](https://nuget.org/packages/)


対象の演算子をにエンコード `BlockEncoding` します。

これにより、 `BlockEncoding` 一部の演算子 $H = \ sum_ {j} | \ alpha_j | をエンコードする、$U = P\ cdot V\ Cdot P ^/ダガー $ が構築されます。U_j $ は、unitaries います。 通常、$P $ は、$P \ket {0} \_ a = \ sum_j \ sqrt{\ alpha_j/ \| \ vec-alpha \| \_ 2} \ket{j} \_ a $、$V = \ sum_ {j} \ket{j}\bra{j} \_ aotimes U_j $ という状態の準備を行うためのものです。

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a>入力

### <a name="statepreparation--t--unit-adj--ctl"></a>statePreparation: ' t => [ユニット](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl

いくつかのターゲット状態を準備する、$P の1つのユニタリ。


### <a name="selector--ts--unit-adj--ctl"></a>セレクター: (' t, s) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl

$H $ のコンポーネント unitaries エンコードする、$V の $。



## <a name="output--ts--unit-adj--ctl"></a>出力: (t, s) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl

$U $ はレジスタに対して共同で動作し、 `a` `s` $H $ をブロックエンコードし、$U ^ ダガー = U $ を満たすことができます。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&


### <a name="s"></a>Emc



## <a name="remarks"></a>解説

この `BlockEncoding` 実装は、のプロパティを提供 `BlockEncodingReflection` します。

## <a name="see-also"></a>参照

- [Microsoft. クォンタム. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [BlockEncodingReflection です。](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)