---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: ApplyPermutationUsingDecomposition 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 5b25ef3327bbca2dfdbe8fa876f3f797dddf77e8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192130"
---
# <a name="applypermutationusingdecomposition-operation"></a>ApplyPermutationUsingDecomposition 操作

名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


分解ベースの合成を使用する順列を指定して、クォンタムの状態の振幅を Permutes します。

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

この手順では、分解ベースの合成アプローチを実装します。  入力は、$ 2 ^ n $ 要素の順列 $ \ pi $ ($ \{ 0, \ ドット, 2 ^ n-1 $) で、 \} $n $ 変数の元に戻せるブール関数を表します。
このアルゴリズムでは、変数インデックス $i $: の各変数について、次の手順を繰り返し実行します。

1. Compute $ ((\ pi_l, \ pi_r), \ pi ') $ では、$ \ pi_l $ と $ \ pi_r $ のイメージは、要素内のビットを変更しないようにします。 $ \ $ および $ \ $ は、$-pi ' $ のイメージではなく、要素内のビット $i $ を変更しません。
2. $ \ Pi \leftarrow \ pi ' $ を設定し、固定ポイントではない要素に基づいて $ \ pi_l $ と $ \ pi_r $ から真理のテーブルを派生させます。

すべての変数インデックスに対してこれらの手順を適用すると、残りの順列 $ \ pi $ が id になります。また、収集された真理テーブルとインデックスに基づいて、 @"microsoft.quantum.intrinsic.x" 操作を使用して、実際のテーブルで制御される操作を適用でき @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" ます。

変数の順序は、$0、\ ドット、n-$1 です。  操作には、カスタム変数の順序を指定でき @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder" ます。

## <a name="input"></a>入力

### <a name="perm--int"></a>perm: [Int](xref:microsoft.quantum.lang-ref.int)[]

0から始まる $ 2 ^ n $ 要素の順列。


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

順列が適用される $n $ qubits の一覧。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>リファレンス

- [*Alexis De Vos*、 *Yvan Van rentergem*、Adv ((2)、2008、pp. 183--200)](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [*Mathias Soeken*、 *山久 tague*、 *gerhard W Dueck*、 *rolf Drechsler*、シンボル計算のジャーナル 73 (2016)、pp. 1--26](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a>参照

- [ApplyPermutationUsingDecompositionWithVariableOrder です。](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [ApplyPermutationUsingTransformation です。](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)