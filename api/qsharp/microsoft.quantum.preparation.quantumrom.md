---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: QuantumROM 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  > [!WARNING]

  > QuantumROM has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.


  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 1ee805fb2ea02121daaab7fc3eb5dbbcb134b470
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229887"
---
# <a name="quantumrom-function"></a>QuantumROM 関数

名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> QuantumROM は非推奨となりました。 代わりに、<xref:Microsoft.Quantum.Preparation.PurifiedMixedState> を使用してください。

は、指定された密度マトリックスを表すために、クォンタム ROM の手法を使用します。

$N $ 係数 $ \ alpha_j $ のリストが指定されている場合、$U この例では、クォンタム-ROM 手法を使用して近似 $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j 密度マトリックス $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| alpha_j |} の purification の \ket{j}\bra{j} $ を準備します。{\ sum_k | \ alpha_k |}\ket{j}\bra{j} $。 この近似値では、$/イプシロン $ というエラーが $ | p_j-\frac{| alpha_j |} のようになります。{\ sum_k | \ alpha_k |} |\ le/イプシロン/N $ と $ \| \tilde\rho-\rho \| $。 つまり、$ $ \begin{align} U\ket {0} ^ {\lceil\ log_2 N\r ceil} \ k {0} ^ {m} = \ sum_ {j = 0} ^ {N-1} \ sqrt{p_j} \ket{j}\ket{\text{garbage} _j} です。
\end{align} $ $

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a>入力

### <a name="targeterror--double"></a>targetError: [Double](xref:microsoft.quantum.lang-ref.double)

ターゲットエラー $ \ イプシロン $。


### <a name="coefficients--double"></a>係数: [Double](xref:microsoft.quantum.lang-ref.double)[]

ベース状態の確率を指定する $N $ 係数の配列。
負の値 $-\ alpha_j $ は、正の $ | \ alpha_j | $ として処理されます。



## <a name="output--intintintdoublelittleendianqubit--unit--is-adj--ctl"></a>出力: (([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double), ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl)

## <a name="first-parameter"></a>最初のパラメーター

は、 `(x,(y,z))` `x = y + z` 割り当てられた qubits の合計数、は `y` レジスタの qubits の数、は `LittleEndian` `z` ガベージ qubits の数であるタプルです。

## <a name="second-parameter"></a>2番目のパラメーター

係数配列の1基準 $ \ sum_j | \ alpha_j | $。

## <a name="third-parameter"></a>3番目のパラメーター

$U のユニタリは $ です。

## <a name="references"></a>リファレンス

- Babbush、Spectra、Gidney、Dominic W Berry、Nathan Wiebe、Jarrod McClean、Alexandru Er、オースティン Fowler、Hartmut Neven の各クォンタム回線での電子商取引のエンコード https://arxiv.org/abs/1805.03662