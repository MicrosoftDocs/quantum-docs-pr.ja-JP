---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: PurifiedMixedState 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 73b031f1082d0a12975abad074b07184dcbabdbe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230023"
---
# <a name="purifiedmixedstate-function"></a>PurifiedMixedState 関数

名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定された混合状態の purification を準備する操作を返します。
"Purified mixed state" は、係数 {pi} のベクターによって指定されたフォーム | ψ⟩ = Σi √ pi | i ⟩ | garbagei ⟩の状態を示します。 このフォームの状態は、混合状態複素数≔ pi | i ⟩⟨ i | に減らすことができます。"ガベージ" レジスタをトレースする (つまり、コンピューティングのために対角線が斜めである混合状態)。

詳細については、「」を参照してください https://arxiv.org/pdf/1805.03662.pdf?page=15 。

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a>説明

クォンタム ROM 手法を使用して特定の密度マトリックスを表現し、その表現を状態準備操作として返します。

特に、$N $ 係数 $ \ alpha_j $ のリストがあるとします。この関数は、\tilde\rho = \ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} \end{align} $ $ の混合状態 $ $ \begin{align} \rho = \ sum_ {j = 0} ^ {N-1} \ frac {| alpha_j |} の近似値を準備するために、クォンタム ROM の手法を使用する操作を返します。{\ sum_k | \ alpha_k |}\ket{j}\bra{j}, \end{align} $ $ (各 $p _j $ は、$ $ \begin{align}/left | を含む指定された係数 $ \ alpha_j $ に対する近似値です。p_j-\frac{| \ alpha_j |}{\ sum_k | \ alpha_k |}\ le \frac{\epsilon}{N} \end{align} $ $ $j $。

インデックスレジスタとガベージ qubits のレジスタが渡された場合 state $ \ket \ket{00\cdots 0} の初期状態では {0} 、返された操作は両方のレジスタを $ \ チルダ \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \ sqrt{p_j} \ket{j}\ket{\text{garbage} _j}, \end{align} $ $ の purification に準備します。これにより、対象のエラー $ $ の前に、必要な準備

## <a name="input"></a>入力

### <a name="targeterror--double"></a>targetError: [Double](xref:microsoft.quantum.lang-ref.double)

ターゲットエラー $ \ イプシロン $。


### <a name="coefficients--double"></a>係数: [Double](xref:microsoft.quantum.lang-ref.double)[]

ベース状態の確率を指定する $N $ 係数の配列。
負の値 $-\ alpha_j $ は、正の $ | \ alpha_j | $ として処理されます。



## <a name="output--mixedstatepreparation"></a>出力: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)

結合インデックスとガベージレジスタに対する purification として $ \ チルダ \rho $ を準備する操作。

## <a name="remarks"></a>解説

この演算に指定された係数は、1基準に従って正規化されます。そのため、係数は常に有効なカテゴリ確率分布を表していると見なされます。

## <a name="references"></a>リファレンス

- Babbush、Spectra、Gidney、Dominic W Berry、Nathan Wiebe、Jarrod McClean、Alexandru Er、オースティン Fowler、Hartmut Neven の各クォンタム回線での電子商取引のエンコード https://arxiv.org/abs/1805.03662

## <a name="see-also"></a>参照

- [PurifiedMixedStateWithData の準備](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)