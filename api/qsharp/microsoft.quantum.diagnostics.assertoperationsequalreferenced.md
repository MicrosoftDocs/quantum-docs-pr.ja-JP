---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced
title: AssertOperationsEqualReferenced 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers. Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated. This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.
ms.openlocfilehash: a3e8791321b4f2ca1885dffeb92c7b13e5491a32
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712957"
---
# <a name="assertoperationsequalreferenced-operation"></a><span data-ttu-id="10195-102">AssertOperationsEqualReferenced 操作</span><span class="sxs-lookup"><span data-stu-id="10195-102">AssertOperationsEqualReferenced operation</span></span>

<span data-ttu-id="10195-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="10195-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="10195-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="10195-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="10195-105">2つの操作を指定すると、すべての入力状態で同じ動作をするようにアサートされます。</span><span class="sxs-lookup"><span data-stu-id="10195-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="10195-106">このアサーションは、Jamiołkowski isomorphism を使用することによって実装されます。このアサーションは、2つのありレジスタの qubit 状態アサーションのいずれかに軽減されます。</span><span class="sxs-lookup"><span data-stu-id="10195-106">This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers.</span></span>
<span data-ttu-id="10195-107">このため、この操作では、テスト対象の各操作を1回だけ呼び出す必要がありますが、割り当てられる qubits は2倍必要です。</span><span class="sxs-lookup"><span data-stu-id="10195-107">Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated.</span></span>
<span data-ttu-id="10195-108">このアサーションを使用して、最適化されたバージョンの操作がその単純な実装と同じように動作すること、またはクォンタム以外の入力の範囲に対して動作する操作が既知のケースと一致することを確認できます。</span><span class="sxs-lookup"><span data-stu-id="10195-108">This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.</span></span>

```qsharp
operation AssertOperationsEqualReferenced (nQubits : Int, actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="10195-109">入力</span><span class="sxs-lookup"><span data-stu-id="10195-109">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="10195-110">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="10195-110">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="10195-111">各操作に渡す qubits の数。</span><span class="sxs-lookup"><span data-stu-id="10195-111">Number of qubits to pass to each operation.</span></span>


### <a name="actual--qubit--unit"></a><span data-ttu-id="10195-112">実際: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="10195-112">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="10195-113">テストする操作。</span><span class="sxs-lookup"><span data-stu-id="10195-113">Operation to be tested.</span></span>


### <a name="expected--qubit--unit-adj"></a><span data-ttu-id="10195-114">想定: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="10195-114">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="10195-115">テスト対象の操作の予期される動作を定義する操作。</span><span class="sxs-lookup"><span data-stu-id="10195-115">Operation defining the expected behavior for the operation under test.</span></span>



## <a name="output--unit"></a><span data-ttu-id="10195-116">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="10195-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="10195-117">解説</span><span class="sxs-lookup"><span data-stu-id="10195-117">Remarks</span></span>

<span data-ttu-id="10195-118">この操作を行うには、予期される動作をモデル化する操作が adjointable であることが必要です。これにより、逆のをターゲットレジスタだけで実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="10195-118">This operation requires that the operation modeling the expected behavior is adjointable, so that the inverse can be performed on the target register alone.</span></span>
<span data-ttu-id="10195-119">正式には、この要件を緩和されする置換操作を指定できますが、入れ替え操作は、通常、任意のクォンタム操作に対して物理的には機能しないため、ここにはオプションとして含まれていません。</span><span class="sxs-lookup"><span data-stu-id="10195-119">Formally, one can specify a transpose operation, which relaxes this requirement, but the transpose operation is not in general physically realizable for arbitrary quantum operations and thus is not included here as an option.</span></span>