---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEXY
title: OptimizedBEXY 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBEXY
qsharp.summary: A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$. That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$
ms.openlocfilehash: 359d347fc57be46200a218646911a7a400b4a96d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713909"
---
# <a name="optimizedbexy-operation"></a>OptimizedBEXY 操作

名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)

パック [](https://nuget.org/packages/)


$ (X ^ {z + 1} \_ .py ^ {z} \_ p) z \_ {p-1} に p li 文字列を適用するユニタリ $U $...$ On qubits $ 0.. p $ は、インデックス $z \ \{ 0、1 \} $、$p $ で条件付きで Z_0 ます。 つまり、$ $ \begin{align} U\ket {z} \ k {p} \ k {\ psi} = \ket{z}\ket{p} (X ^ {z + 1} \_ .py ^ {z} \_ p) z \_ {p-1}...Z_0 \ket{\psi} \end{align} $ $

```qsharp
operation OptimizedBEXY (pauliBasis : Qubit, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="paulibasis--qubit"></a>Pています: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

この qubit が state $ \ket $ の場合 {0} 、$X $ が適用されます。 状態が $ \ket $ の場合 {1} 、$Y $ が適用されます。


### <a name="indexregister--littleendian"></a>indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

このレジスタの状態 $ \ket{p} $ によって、$X $ または $Y $ が適用される qubit が決まります。


### <a name="targetregister--qubit"></a>targetRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Pare Li 演算子が適用される qubits の登録です。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>関連項目

- Babbush、Spectra、Gidney、Dominic W Berry、Nathan Wiebe、Jarrod McClean、Alexandru Er、オースティン Fowler、Hartmut Neven の各クォンタム回線での電子商取引のエンコード https://arxiv.org/abs/1805.03662