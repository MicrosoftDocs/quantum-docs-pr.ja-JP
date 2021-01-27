---
uid: Microsoft.Quantum.Simulation.BlockEncodingReflectionByLCU
title: BlockEncodingReflectionByLCU 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingReflectionByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncodingReflection`.

  This constructs a `BlockEncodingReflection` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: ef92e517ae40e76c94aff1121c78ece9985109fc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857724"
---
# <a name="blockencodingreflectionbylcu-function"></a>BlockEncodingReflectionByLCU 関数

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


対象の演算子をにエンコード `BlockEncodingReflection` します。

これにより、 `BlockEncodingReflection` 一部の演算子 $H = \ sum_ {j} | \ alpha_j | をエンコードする、$U = P\ cdot V\ Cdot P ^/ダガー $ が構築されます。U_j $ は、unitaries います。 通常、$P $ は、$P \ket {0} \_ a \ sum_j \ sqrt{\ alpha_j/ \| \ vec-alpha \| \_ 2} \ket{j} \_ a $、$V = \ sum_ {j} \ket{j}\bra{j} \_ aotimes U_j $ という状態の準備を行うためのものです。

```qsharp
function BlockEncodingReflectionByLCU (statePreparation : (Qubit[] => Unit is Adj + Ctl), selector : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a>入力

### <a name="statepreparation--qubit--unit--is-adj--ctl"></a>statePreparation: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl

いくつかのターゲット状態を準備する、$P の1つのユニタリ。


### <a name="selector--qubitqubit--unit--is-adj--ctl"></a>セレクター: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl

$H $ のコンポーネント unitaries エンコードする、$V の $。



## <a name="output--blockencodingreflection"></a>出力: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

レジスタに対して共同で動作し `a` 、 `s` $H $ をブロックエンコードし、$U ' ^ = U $ を満たす $U の、1つのユニタリ {-1} です。

## <a name="remarks"></a>解説

この `BlockEncoding` 実装は、のプロパティを提供 `BlockEncodingReflection` します。

## <a name="see-also"></a>参照

- [Microsoft. クォンタム. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [BlockEncodingReflection です。](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)