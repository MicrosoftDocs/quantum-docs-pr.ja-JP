---
uid: Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance
title: AssertQubitIsInStateWithinTolerance 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitIsInStateWithinTolerance
qsharp.summary: >-
  Asserts that a qubit in the expected state.

  `expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$. The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part. The last argument defines the tolerance with which assertion is made.
ms.openlocfilehash: b40c5c4f731190c8c0d00d33718680e5448bf767
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829786"
---
# <a name="assertqubitisinstatewithintolerance-operation"></a>AssertQubitIsInStateWithinTolerance 操作

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


予期される状態の qubit をアサートします。

`expected` 複合ベクター、$ \ket{\psi} = \begin{bmatrix}a & b\ end {bmatrix} ^ {\mathrm{T}} $ を表します。
各 $a $、$b $ を表す組の最初の要素は複素数の実数部ですが、2番目の要素は虚数部です。
最後の引数は、アサーションが行われる許容範囲を定義します。

```qsharp
operation AssertQubitIsInStateWithinTolerance (expected : (Microsoft.Quantum.Math.Complex, Microsoft.Quantum.Math.Complex), register : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a>入力

### <a name="expected--complexcomplex"></a>が必要です: ([complex](xref:Microsoft.Quantum.Math.Complex)、[complex](xref:Microsoft.Quantum.Math.Complex))

$ \Ket {0} $ と $ \ket $ には、それぞれ複雑な振幅が必要です {1} 。


### <a name="register--qubit"></a>register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

状態がアサートされる qubit。 この qubit は、割り当てられた他の qubit から分離可能であり、entangled ではないと見なされます。


### <a name="tolerance--double"></a>tolerance: [Double](xref:microsoft.quantum.lang-ref.double)

実際の振幅が予期された値と異なることが許容される加法許容範囲。
詳細については、以下の解説を参照してください。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>例

```qsharp
using (qubits = Qubit[2]) {
    // Both qubits are initialized as |0〉: a=(1 + 0*i), b=(0 + 0*i)
    AssertQubitIsInStateWithinTolerance((Complex(1., 0.), Complex(0., 0.)), qubits[0], 1e-5);
    AssertQubitIsInStateWithinTolerance((Complex(1., 0.), Complex(0., 0.)), qubits[1], 1e-5);
    Y(qubits[1]);
    // Y |0〉 = i |1〉: a=(0 + 0*i), b=(0 + 1*i)
    AssertQubitIsInStateWithinTolerance((Complex(0., 0.), Complex(0., 1.)), qubits[1], 1e-5);
}
```

## <a name="remarks"></a>解説

次の Mathematica コードは、mi、mx、my、mz の式を検証するために使用できます。

```mathematica
{Id, X, Y, Z} = Table[PauliMatrix[k], {k, 0, 3}];
st = {{ reA + I imA }, { reB + I imB} };
M = st . ConjugateTranspose[st];
mx = Tr[M.X] // ComplexExpand;
my = Tr[M.Y] // ComplexExpand;
mz = Tr[M.Z] // ComplexExpand;
mi = Tr[M.Id] // ComplexExpand;
2 m == Id mi + X mx + Z mz + Y my // ComplexExpand // Simplify
```

許容範囲は $L、 \_ 3 次元の実数ベクトル (x ₂) 間の {\ infty} $ 距離です。 x ₃、x ₄) で定義されている $ \langle\psi | \psi\rangle = x \_ 1 I + x \_ 2 x + x \_ 3 Y + x \_ 4 Z $ および実数ベクトル (y ₂、y ₃、y ₄) によって定義された複素数 = y ₁ I + y ₂ x + y ₃ y + y ₄ Z
これは、Tr (複素数) と Tr (| ψ⟩⟨ψ |) が両方とも 1 (たとえば、x ₁ = 1/2、y ₁ = 1/2) であることを前提としています。
そうでない場合、関数は、(x ₂-x ₁、x ₃₁、x ₄-x ₁、x ₄ + x ₁) と (y ₂-y ₁、y ₃-y ₁、y ₄-y ₁、y ₄ + y ₁) が tolerance パラメーターより小さいことをアサートします。