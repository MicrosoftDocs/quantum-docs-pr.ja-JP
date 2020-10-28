---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 407a139da816281346eb06849f81e91b83202653
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712971"
---
# <a name="assertoperationsequalinplace-operation"></a><span data-ttu-id="2965c-102">AssertOperationsEqualInPlace 操作</span><span class="sxs-lookup"><span data-stu-id="2965c-102">AssertOperationsEqualInPlace operation</span></span>

<span data-ttu-id="2965c-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2965c-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2965c-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2965c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2965c-105">2つの操作を指定すると、すべての入力状態で同じ動作をするようにアサートされます。</span><span class="sxs-lookup"><span data-stu-id="2965c-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="2965c-106">このアサーションは、フォームのすべての状態に対して操作のアクションを確認することによって実装されます。 $V 0/otimes V_ {n-1} $ です。 $V _k $ は、状態 $ \ket {0} $、$ \ket {1} $、$ \ket{+} $、$ \ket{i} $ (+ 1 eigenstate of Pauli Y 演算子) です</span><span class="sxs-lookup"><span data-stu-id="2965c-106">This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).</span></span>

<span data-ttu-id="2965c-107">このアサーションは $n $ qubits を使用し、比較対象の操作の複数の呼び出しを必要とします。</span><span class="sxs-lookup"><span data-stu-id="2965c-107">This assertion uses $n$ qubits and requires multiple calls of the operations being compared.</span></span>

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="2965c-108">入力</span><span class="sxs-lookup"><span data-stu-id="2965c-108">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="2965c-109">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2965c-109">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2965c-110">操作と演算を実行する qubits $n $ の数 `givenU` `expectedU` 。</span><span class="sxs-lookup"><span data-stu-id="2965c-110">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="2965c-111">与え u: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2965c-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="2965c-112">$N $ qubits の操作を確認します。</span><span class="sxs-lookup"><span data-stu-id="2965c-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit-adj"></a><span data-ttu-id="2965c-113">expectedU: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="2965c-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="2965c-114">比較対象の $n $ qubits に対する参照操作 `givenU` です。</span><span class="sxs-lookup"><span data-stu-id="2965c-114">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2965c-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2965c-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="2965c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2965c-116">References</span></span>

<span data-ttu-id="2965c-117">州 $ \ket {0} $、$ \ket {1} $、$ \ket{+} $、$ \ket{i} $ の基礎は、「 [ *i. 語,*](https://arxiv.org/abs/quant-ph/9610001)」で説明されているように、Chuang-Nielsen の基礎です。</span><span class="sxs-lookup"><span data-stu-id="2965c-117">The basis of states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ is the Chuang-Nielsen basis, described in [ *I. L. Chuang, M. A. Nielsen* ](https://arxiv.org/abs/quant-ph/9610001).</span></span>

## <a name="see-also"></a><span data-ttu-id="2965c-118">参照</span><span class="sxs-lookup"><span data-stu-id="2965c-118">See Also</span></span>

- [<span data-ttu-id="2965c-119">AssertOperationsEqualReferenced です。</span><span class="sxs-lookup"><span data-stu-id="2965c-119">Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)