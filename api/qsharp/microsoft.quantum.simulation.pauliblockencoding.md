---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: P# liblockencoding 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 1426c7cbc257f9263ff45a96738fe798c3679ba1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720218"
---
# <a name="pauliblockencoding-function"></a>P# liblockencoding 関数

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パック [](https://nuget.org/packages/)


Hamiltonian のブロックエンコードのユニタリを作成します。

Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $ は、$ $ \ $P $ という実数の合計によって記述されます。

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a>入力

### <a name="generatorsystem--generatorsystem"></a>generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

`GeneratorSystem`$ $H を、P# li 用語の合計として記述する。



## <a name="output--doubleblockencodingreflection"></a>出力: ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))

## <a name="first-parameter"></a>最初のパラメーター

係数 $ \ alpha = \ sum_ {j} | \ alpha_j | $ の1つの基準です。

## <a name="second-parameter"></a>2番目のパラメーター

`BlockEncodingReflection`Hamiltonian $H $ の1つの $U ($) です。 このユニタリは $U ^ 2 = I $ に一致するので、リフレクションでもあります。

## <a name="remarks"></a>解説

これを取得するには、状態 $ \ sum_ {j} \ sqrt{\ alpha_j/\alpha}\ket{j} $ を準備して準備を解除し、乗算によって制御されるユニタリおよびを構築し <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> ます。