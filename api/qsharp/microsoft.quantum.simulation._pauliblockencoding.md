---
uid: Microsoft.Quantum.Simulation._PauliBlockEncoding
title: _PauliBlockEncoding 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 6ad3e692f68ec2d405e19a7e467ef8fe33d449fc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225569"
---
# <a name="_pauliblockencoding-function"></a><span data-ttu-id="1e87b-102">_PauliBlockEncoding 関数</span><span class="sxs-lookup"><span data-stu-id="1e87b-102">_PauliBlockEncoding function</span></span>

<span data-ttu-id="1e87b-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="1e87b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="1e87b-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1e87b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1e87b-105">Hamiltonian のブロックエンコードのユニタリを作成します。</span><span class="sxs-lookup"><span data-stu-id="1e87b-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="1e87b-106">Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $ は、$ $ \ $P $ という実数の合計によって記述されます。</span><span class="sxs-lookup"><span data-stu-id="1e87b-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function _PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem, statePrepUnitary : (Double[] -> (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)), multiplexer : ((Int, (Int -> (Qubit[] => Unit is Adj + Ctl))) -> ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="1e87b-107">入力</span><span class="sxs-lookup"><span data-stu-id="1e87b-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="1e87b-108">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="1e87b-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="1e87b-109">`GeneratorSystem`$ $H を、P# li 用語の合計として記述する。</span><span class="sxs-lookup"><span data-stu-id="1e87b-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>


### <a name="stateprepunitary--double---littleendian--unit--is-adj--ctl"></a><span data-ttu-id="1e87b-110">statePrepUnitary: [Double](xref:microsoft.quantum.lang-ref.double)[]-> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="1e87b-110">statePrepUnitary : [Double](xref:microsoft.quantum.lang-ref.double)[] -> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="1e87b-111">インデックス $ \ket{j} $ に _j $ j\rightarrow で制御される、$f: V_j $ という関数が指定されている場合に、インデックス $ $ に対して $ によって制御される、$V の $V の単位</span><span class="sxs-lookup"><span data-stu-id="1e87b-111">A unitary operation $V$ that applies the unitary $V_j$ controlled on index $\ket{j}$, given a function $f: j\rightarrow V_j$.</span></span>


### <a name="multiplexer--intint---qubit--unit--is-adj--ctl---littleendianqubit--unit--is-adj--ctl"></a><span data-ttu-id="1e87b-112">マルチプレクサー: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl)-> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + ctl</span><span class="sxs-lookup"><span data-stu-id="1e87b-112">multiplexer : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl) -> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>





## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="1e87b-113">出力: ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span><span class="sxs-lookup"><span data-stu-id="1e87b-113">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="1e87b-114">最初のパラメーター</span><span class="sxs-lookup"><span data-stu-id="1e87b-114">First parameter</span></span>

<span data-ttu-id="1e87b-115">係数 $ \ alpha = \ sum_ {j} | \ alpha_j | $ の1つの基準です。</span><span class="sxs-lookup"><span data-stu-id="1e87b-115">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="1e87b-116">2番目のパラメーター</span><span class="sxs-lookup"><span data-stu-id="1e87b-116">Second parameter</span></span>

<span data-ttu-id="1e87b-117">`BlockEncodingReflection`Hamiltonian $U $ の1つの $U ($) です。</span><span class="sxs-lookup"><span data-stu-id="1e87b-117">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $U$.</span></span> <span data-ttu-id="1e87b-118">このユニタリは $U ^ 2 = I $ に一致するので、リフレクションでもあります。</span><span class="sxs-lookup"><span data-stu-id="1e87b-118">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="1e87b-119">解説</span><span class="sxs-lookup"><span data-stu-id="1e87b-119">Remarks</span></span>

<span data-ttu-id="1e87b-120">操作の例 $ \ sum_ {j} \ sqrt{\ alpha_j/\alpha}\ket{j} $ の準備と準備解除を行い、乗算によって制御される複数のカウントを構築し <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> ます。</span><span class="sxs-lookup"><span data-stu-id="1e87b-120">Example operations the prepare and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and construct a multiply-controlled unitary are <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>