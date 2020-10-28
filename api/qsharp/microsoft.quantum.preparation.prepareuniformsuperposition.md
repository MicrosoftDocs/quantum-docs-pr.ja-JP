---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: PrepareUniformSuperposition 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: 8b57a7a02e9f704cf9677574824dfdc93fff25b0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709457"
---
# <a name="prepareuniformsuperposition-operation"></a>PrepareUniformSuperposition 操作

名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)

パック [](https://nuget.org/packages/)


0 ~ をエンコードする州に対して一様な法則を作成し `nIndices - 1` ます。

つまり、このユニタリ $U $ は、入力状態が $ \ket{0\cdots 0} $ の場合に、すべての数値の州 $0 $ に対して $M-$1 に対して uniform 法則を作成します。 つまり、$ $ \begin{align} U\ket {0} = \ frac {\ {1} sqsum_ rt{\ket{j}. {j = 0} ^ {m.-1}
\end{align} $ $。

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>入力

### <a name="nindices--int"></a>n インデックス: [Int](xref:microsoft.quantum.lang-ref.int)

Uniform 法則内で、必要な状態の数を $ $M します。


### <a name="indexregister--littleendian"></a>indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

数値の状態を形式で格納する qubit レジスタ `LittleEndian` 。
このレジスタは $M-$1 の数値を格納できる必要があり、$ \ket{0\cdots 0} $ という状態で初期化されると想定されています。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

操作は adjointable ですが、その場合は、 `indexRegister` が1つ目の状態に対して一様な法則にある必要があり `nIndices` ます。