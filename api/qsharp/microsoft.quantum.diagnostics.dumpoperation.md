---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: cde188806506c586c4c77a7f9b2b43ad0e10ef1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829278"
---
# <a name="dumpoperation-operation"></a><span data-ttu-id="18603-102">DumpOperation 操作</span><span class="sxs-lookup"><span data-stu-id="18603-102">DumpOperation operation</span></span>

<span data-ttu-id="18603-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="18603-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="18603-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="18603-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="18603-105">操作が指定された場合、現在の実行ターゲットで使用できるようになった操作に関する診断が表示されます。</span><span class="sxs-lookup"><span data-stu-id="18603-105">Given an operation, displays diagnostics about the operation that are made available by the current execution target.</span></span>

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="18603-106">入力</span><span class="sxs-lookup"><span data-stu-id="18603-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="18603-107">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="18603-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="18603-108">指定された操作が動作する qubits の数。</span><span class="sxs-lookup"><span data-stu-id="18603-108">The number of qubits on which the given operation acts.</span></span>


### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="18603-109">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="18603-109">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="18603-110">診断される操作。</span><span class="sxs-lookup"><span data-stu-id="18603-110">The operation that is to be diagnosed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="18603-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="18603-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="18603-112">例</span><span class="sxs-lookup"><span data-stu-id="18603-112">Example</span></span>

<span data-ttu-id="18603-113">クォンタムシミュレーターのターゲットで実行すると、次のスニペットはマトリックス $ $ \begin{aligned} を出力します (\begin{matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \end{matrix}\right) \end{aligned}.</span><span class="sxs-lookup"><span data-stu-id="18603-113">When run on the quantum simulator target, the following snippet will output the matrix $$ \begin{aligned} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \end{matrix}\right) \end{aligned}.</span></span>
$$

```qsharp
operation DumpCnot() : Unit {
    DumpOperation(2, ApplyToFirstTwoQubitsCA(CNOT, _));
}
```

## <a name="remarks"></a><span data-ttu-id="18603-114">解説</span><span class="sxs-lookup"><span data-stu-id="18603-114">Remarks</span></span>

<span data-ttu-id="18603-115">この操作を呼び出すと、Q # 内からは観察可能な効果がありません。</span><span class="sxs-lookup"><span data-stu-id="18603-115">Calling this operation has no observable effect from within Q#.</span></span> <span data-ttu-id="18603-116">表示されている正確な診断は、現在の実行ターゲットおよびエディター環境に依存しています。</span><span class="sxs-lookup"><span data-stu-id="18603-116">The exact diagnostics that are displayed, if any, are dependent on the current execution target and editor environment.</span></span>
<span data-ttu-id="18603-117">たとえば、完全な状態のクォンタムシミュレーターで使用する場合は、を表すために使用される、1つの単位の行列 `op` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="18603-117">For example, when used on the full-state quantum simulator, a unitary matrix used to represent `op` is displayed.</span></span>

<span data-ttu-id="18603-118">グローバルフェーズのあいまいさ (例: 完全な状態シミュレーター) を許可するシミュレーターで実行する場合、返される表現はグローバルフェーズによって異なる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="18603-118">Note that, when run on simulators that admit a global phase ambiguity (e.g.: the full-state simulator), returned representations may vary up to a global phase.</span></span>

<span data-ttu-id="18603-119">同様に、行と列の行列表現の順序は、この操作をサポートする各シミュレーターで使用される規則によって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="18603-119">Similarly, the ordering of rows and columns matrix representations may vary with the conventions used by each simulator supporting this operation.</span></span>