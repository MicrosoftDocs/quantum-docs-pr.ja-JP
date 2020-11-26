---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateWithData
title: PurifiedMixedStateWithData 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateWithData
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed\rstate, entangled with a register representing a given collection of data.\rA \"purified mixed state with data\" refers to a state of the form Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |\U0001D465ᵢ⟩ |garbageᵢ⟩,\rwhere each \U0001D465ᵢ is a bitstring encoding additional data associated with the register |\U0001D456⟩.\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: c89ee8f5df58e5d6b154b67d2b39db208bc8a215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229955"
---
# <a name="purifiedmixedstatewithdata-function"></a>PurifiedMixedStateWithData 関数

名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定されたデータのコレクションを表すレジスタを使用して、指定された混合状態の purification を準備する操作を返します。
"Purified mixed state with data" は、Σi √ pi | i ⟩ | xi ⟩ | garbagei ⟩という形式の状態を示します。各 xi は、register | i ⟩に関連付けられたビット文字列エンコーディングです。

詳細については、「」を参照してください https://arxiv.org/pdf/1805.03662.pdf?page=15 。

```qsharp
function PurifiedMixedStateWithData (targetError : Double, coefficients : (Double, Bool[])[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a>説明

クォンタム ROM 手法を使用して特定の密度マトリックスを表現し、その表現を状態準備操作として返します。

特に、$N $ 係数 $ \ alpha_j $ と、各係数に関連付けられている bitstring $ \vec{x} j $ のリストがあるとします。この関数は、\tilde\rho = \ sum {j = 0} ^ {\begin{align}} p_j \ket{j}\bra{j}/otimes \ket{\vec{x} _j} \bra{\vec{x}_j} \end{align} $ $ 混合状態 $ $ \begin{align} \rho = \ sum_{j = 0} ^ {N-1} \ frac {| alpha_j |} の _近似を準備するために、クォンタム ROM の手法を使用する操作を返します_。{\ sum_k | \ alpha_k |}\ket{j}\bra{j}/otimes \ket{\vec{x} _j} \bra{\vec{x} _j}、\end{align} $ $。各 $p _j $ は、$ $ \begin{align}/left | を含む、指定された係数 $ \ alpha_j $ に対する近似値です。p_j-\frac{| \ alpha_j |}{\ sum_k | \ alpha_k |}\ le \frac{\epsilon}{N} \end{align} $ $ $j $。

インデックスレジスタとガベージ qubits のレジスタが渡されたとき、初期状態は $ \ket {0} \ket{00\cdots 0} です。返された操作は、両方のレジスタを $ \ チルダ \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \ sqrt{p_j} \ket{j} \ket{\vec{x} _j} \ket{\text{garbage} _j}, \end{align} $ $ に登録します。これにより、対象のエラー $ purification $ の中から、必要な準備を行うために、ガベージレジスタをリセット

## <a name="input"></a>入力

### <a name="targeterror--double"></a>targetError: [Double](xref:microsoft.quantum.lang-ref.double)

ターゲットエラー $ \ イプシロン $。


### <a name="coefficients--doublebool"></a>係数: ([Double](xref:microsoft.quantum.lang-ref.double)、[Bool](xref:microsoft.quantum.lang-ref.bool)[]) []

各係数に関連付けられた bitstring $ \vec{x} _j $ と共に、基準状態の確率を指定する $N $ 係数の配列。
負の値 $-\ alpha_j $ は、正の $ | \ alpha_j | $ として処理されます。



## <a name="output--mixedstatepreparation"></a>出力: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)

結合インデックスとガベージレジスタに対する purification として $ \ チルダ \rho $ を準備する操作。

## <a name="remarks"></a>解説

この演算に指定された係数は、1基準に従って正規化されます。そのため、係数は常に有効なカテゴリ確率分布を表していると見なされます。

## <a name="references"></a>リファレンス

- Babbush、Spectra、Gidney、Dominic W Berry、Nathan Wiebe、Jarrod McClean、Alexandru Er、オースティン Fowler、Hartmut Neven の各クォンタム回線での電子商取引のエンコード https://arxiv.org/abs/1805.03662

## <a name="see-also"></a>参照

- [PurifiedMixedState の準備](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)