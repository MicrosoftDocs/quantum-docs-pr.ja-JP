---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: DecomposedIntoTimeStepsCA 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: aa5f09f2e1fde878b523b4efc20b86c26ac738ff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216542"
---
# <a name="decomposedintotimestepsca-function"></a>DecomposedIntoTimeStepsCA 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定された操作に対して Trotter – Suzuki インテグレーターを実装する操作を返します。

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>入力

### <a name="nsteps--int"></a>nSteps: [Int](xref:microsoft.quantum.lang-ref.int)

時間ステップに分解される操作の数。


### <a name="op--intdoublet--unit--is-adj--ctl"></a>op: ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です

分解のためのインデックス入力 (型 `Int` ) と時間入力 (型) を受け入れる操作 `Double` 。


### <a name="trotterorder--int"></a>trotterOrder: [Int](xref:microsoft.quantum.lang-ref.int)

使用する Trotter – Suzuki インテグレーターの順序を選択します。
注文1と注文2、4、6,...は現在サポートされています。



## <a name="output--doublet--unit--is-adj--ctl"></a>出力: ([Double](xref:microsoft.quantum.lang-ref.double), t) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl

Trotter – Suzuki インテグレーターを実装するユニタリを返します。最初のパラメーターは `Double` 統合ステップサイズで、2番目のパラメーターは操作対象のターゲットです。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

各時間ステップが動作する型。通常は、 `Qubit[]` またはのいずれか `Qubit` です。

## <a name="remarks"></a>解説

と等しいを指定して呼び出された場合 `order` `1` 、この関数は、最も低い順序の Trotter – Suzuki インテグレーター $ $ \begin{align} S_1 (\ ラムダ) = \ prod_ {j = 1} ^ {m} e ^ {H_j \lambda}, によってシミュレートできる操作を返します。 \end{align} $ $ は、 [quant-ph/0508139 の](https://arxiv.org/abs/quant-ph/0508139) 表記に従い、$/ラムダ $ を進化時間 (返された操作の最初の入力で表される) にします。また、$ H_j \{ _ \} {j = 1} ^ {m} $ は、Dynamical ジェネレーターのセット (Hermitian) として統合されています。これにより、ジェネレーターは、' ^ `op(j, lambda, _)` {H_j \lambda} $ という単位で、ジェネレーターがシミュレートされます。 $e

同様に、 `order` のは、 `2` 2 番目の順序の対称 Trotter – Suzuki インテグレーター $ $ \begin{align} S_2 (\ ラムダ) = \ prod_ {j = 1} ^ {m} e ^ {H_k/ラムダ/2} \ prod_ {j ' = m} ^ {1} e ^ {H_ {j '} \ ラムダ/2} を返します。
\end{align} $ $

の値が大きいほど、 `order` [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139)の再帰的な構築を使用して実装されます。

## <a name="references"></a>リファレンス

- [*Berry、G. Ahokas、Cleve、サンダース、のよう* になります。](https://arxiv.org/abs/quant-ph/0508139)