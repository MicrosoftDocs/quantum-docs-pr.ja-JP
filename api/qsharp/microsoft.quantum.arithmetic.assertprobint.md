---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: 85ff04bbad9dc2ed0f803db65508fdfbb0d22c56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843400"
---
# <a name="assertprobint-operation"></a><span data-ttu-id="2d56c-102">AssertProbInt 操作</span><span class="sxs-lookup"><span data-stu-id="2d56c-102">AssertProbInt operation</span></span>

<span data-ttu-id="2d56c-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2d56c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2d56c-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2d56c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2d56c-105">クォンタムレジスタの特定の状態の確率に予期される値があることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="2d56c-105">Asserts that the probability of a specific state of a quantum register has the expected value.</span></span>

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="2d56c-106">説明</span><span class="sxs-lookup"><span data-stu-id="2d56c-106">Description</span></span>

<span data-ttu-id="2d56c-107">$ \Ket{\psi} = \ sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $ という $n が指定されている場合、$j $ によってインデックスが作成された状態 $ \ket{j} $ の確率 $ | \ alpha_j | ^ 2 $ が予期される値であることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="2d56c-107">Given an $n$-qubit quantum state $\ket{\psi}=\sum^{2^n-1}_{j=0}\alpha_j \ket{j}$, asserts that the probability $|\alpha_j|^2$ of the state $\ket{j}$ indexed by $j$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="2d56c-108">入力</span><span class="sxs-lookup"><span data-stu-id="2d56c-108">Input</span></span>

### <a name="stateindex--int"></a><span data-ttu-id="2d56c-109">stateIndex: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2d56c-109">stateIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2d56c-110">レジスタによって表される状態 $ \ket{j} $ の $j $ のインデックス `LittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="2d56c-110">The index $j$ of the state $\ket{j}$ represented by a `LittleEndian` register.</span></span>


### <a name="expected--double"></a><span data-ttu-id="2d56c-111">が必要です。 [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2d56c-111">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2d56c-112">予期される値 $ | \ alpha_j | ^ 2 $。</span><span class="sxs-lookup"><span data-stu-id="2d56c-112">The expected value of $|\alpha_j|^2$.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="2d56c-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2d56c-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2d56c-114">リトルエンディアン形式で $ \ket{\psi} $ を格納する qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="2d56c-114">The qubit register that stores $\ket{\psi}$ in little-endian format.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="2d56c-115">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2d56c-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2d56c-116">実際と予想される差に対する絶対許容値。</span><span class="sxs-lookup"><span data-stu-id="2d56c-116">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2d56c-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2d56c-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="2d56c-118">例</span><span class="sxs-lookup"><span data-stu-id="2d56c-118">Example</span></span>

<span data-ttu-id="2d56c-119">このレジスタでは、 `qubits` 3-qubit クォンタムの状態 $ \ket{\psi} = \ sqrt {1/8} \ k {0} + \ sqrt {7/8} \ k {6} $ をリトルエンディアン形式でエンコードするとします。</span><span class="sxs-lookup"><span data-stu-id="2d56c-119">Suppose that the `qubits` register encodes a 3-qubit quantum state $\ket{\psi}=\sqrt{1/8}\ket{0}+\sqrt{7/8}\ket{6}$ in little-endian format.</span></span>
<span data-ttu-id="2d56c-120">これは、番号が $ \ket {0} \equiv\ket {0} \ket {0} \ket {0} $ と $ \ket \equiv\ket \ket \ket $ {6} {0} {1} {1} であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="2d56c-120">This means that the number states $\ket{0}\equiv\ket{0}\ket{0}\ket{0}$ and $\ket{6}\equiv\ket{0}\ket{1}\ket{1}$.</span></span> <span data-ttu-id="2d56c-121">その後、次のアサートは成功します。</span><span class="sxs-lookup"><span data-stu-id="2d56c-121">Then the following asserts succeed:</span></span>

```qsharp
AssertProbInt(0, 0.125, qubits, 10e-10);
AssertProbInt(6, 0.875, qubits, 10e-10);
```