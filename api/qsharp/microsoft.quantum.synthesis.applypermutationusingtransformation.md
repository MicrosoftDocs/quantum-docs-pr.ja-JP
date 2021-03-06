---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation
title: ApplyPermutationUsingTransformation 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingTransformation
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.
ms.openlocfilehash: 79913bec44514d477b7ee0668b43396b297b9ab8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858991"
---
# <a name="applypermutationusingtransformation-operation"></a>ApplyPermutationUsingTransformation 操作

名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


変換ベースの合成を使用した順列を指定して、クォンタムの状態の振幅を Permutes します。

```qsharp
operation ApplyPermutationUsingTransformation (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

この手順では、一方向の変換に基づく合成アプローチを実装します。  入力は、$ 2 ^ n $ 要素の順列 $ \ pi $ ($ \{ 0, \ ドット, 2 ^ n-1 $) で、 \} $n $ 変数の元に戻せるブール関数を表します。
アルゴリズムは、次の手順を繰り返し実行します。

1. $X \n e & pi (x) = y $ のように、最小の $x $ を検索します。
2. 出力に適用される複数の制御された Toffoli 操作を見つけます $ \ pi (x) = x $、すべての $x ' < x $ の $ \ pi (x ') $ を変更しません

## <a name="input"></a>入力

### <a name="perm--int"></a>perm: [Int](xref:microsoft.quantum.lang-ref.int)[]

0から始まる $ 2 ^ n $ 要素の順列。


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

順列が適用される $n $ qubits の一覧。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>例

操作を合成するには `SWAP` :

```qsharp
using (qubits = Qubit[2]) {
  ApplyPermutationUsingTransformation([0, 2, 1, 3], LittleEndian(qubits));
}
```

## <a name="references"></a>References

- [*D. Michael 明美*、 *Dmitri Maslov*、 *gerhard W. Dueck*、Proc. DAC 2003、IEEE、pp. 318-323、2003](https://doi.org/10.1145/775832.775915)
- [*Mathias Soeken*、 *Gerhard W. Dueck* 2016 *、springer link*、、pp. 307-321、2016を行います。](https://doi.org/10.1007/978-3-319-40578-0_22)

## <a name="see-also"></a>参照

- [ApplyPermutationUsingDecomposition です。](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)