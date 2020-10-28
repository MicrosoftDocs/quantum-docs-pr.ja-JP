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
# <a name="optimizedbexy-operation"></a><span data-ttu-id="9f98e-102">OptimizedBEXY 操作</span><span class="sxs-lookup"><span data-stu-id="9f98e-102">OptimizedBEXY operation</span></span>

<span data-ttu-id="9f98e-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="9f98e-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="9f98e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9f98e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9f98e-105">$ (X ^ {z + 1} \_ .py ^ {z} \_ p) z \_ {p-1} に p li 文字列を適用するユニタリ $U $...$ On qubits $ 0.. p $ は、インデックス $z \ \{ 0、1 \} $、$p $ で条件付きで Z_0 ます。</span><span class="sxs-lookup"><span data-stu-id="9f98e-105">A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$.</span></span> <span data-ttu-id="9f98e-106">つまり、$ $ \begin{align} U\ket {z} \ k {p} \ k {\ psi} = \ket{z}\ket{p} (X ^ {z + 1} \_ .py ^ {z} \_ p) z \_ {p-1}...Z_0 \ket{\psi} \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="9f98e-106">That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$</span></span>

```qsharp
operation OptimizedBEXY (pauliBasis : Qubit, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="9f98e-107">入力</span><span class="sxs-lookup"><span data-stu-id="9f98e-107">Input</span></span>

### <a name="paulibasis--qubit"></a><span data-ttu-id="9f98e-108">Pています: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9f98e-108">pauliBasis : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9f98e-109">この qubit が state $ \ket $ の場合 {0} 、$X $ が適用されます。</span><span class="sxs-lookup"><span data-stu-id="9f98e-109">When this qubit is in state $\ket{0}$, $X$ is applied.</span></span> <span data-ttu-id="9f98e-110">状態が $ \ket $ の場合 {1} 、$Y $ が適用されます。</span><span class="sxs-lookup"><span data-stu-id="9f98e-110">When it is in state $\ket{1}$, $Y$ is applied.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="9f98e-111">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9f98e-111">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9f98e-112">このレジスタの状態 $ \ket{p} $ によって、$X $ または $Y $ が適用される qubit が決まります。</span><span class="sxs-lookup"><span data-stu-id="9f98e-112">The state $\ket{p}$ of this register determines the qubit on which $X$ or $Y$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="9f98e-113">targetRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9f98e-113">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9f98e-114">Pare Li 演算子が適用される qubits の登録です。</span><span class="sxs-lookup"><span data-stu-id="9f98e-114">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9f98e-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9f98e-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="9f98e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f98e-116">References</span></span>

- <span data-ttu-id="9f98e-117">Babbush、Spectra、Gidney、Dominic W Berry、Nathan Wiebe、Jarrod McClean、Alexandru Er、オースティン Fowler、Hartmut Neven の各クォンタム回線での電子商取引のエンコード https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="9f98e-117">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>