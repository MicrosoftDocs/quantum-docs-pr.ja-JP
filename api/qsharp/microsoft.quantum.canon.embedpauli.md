---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: 0e6a93e22ee495abcc44bdf522e7c72c0981308b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840533"
---
# <a name="embedpauli-function"></a><span data-ttu-id="4b8ce-102">EmbedPauli 関数</span><span class="sxs-lookup"><span data-stu-id="4b8ce-102">EmbedPauli function</span></span>

<span data-ttu-id="4b8ce-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4b8ce-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4b8ce-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4b8ce-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4b8ce-105">Single qubit の P# li 演算子と qubit のインデックスが指定されている場合、そのインデックスの指定された単一の qubit 演算子と `PauliI` 他のすべてのインデックスで、マルチ qubit の P# li 演算子を返します。</span><span class="sxs-lookup"><span data-stu-id="4b8ce-105">Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="4b8ce-106">入力</span><span class="sxs-lookup"><span data-stu-id="4b8ce-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="4b8ce-107">p# li: [p#](xref:microsoft.quantum.lang-ref.pauli) li</span><span class="sxs-lookup"><span data-stu-id="4b8ce-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="4b8ce-108">指定された場所に配置される単一の qubit の P# li 演算子。</span><span class="sxs-lookup"><span data-stu-id="4b8ce-108">A single-qubit Pauli operator to be placed at the given location.</span></span>


### <a name="location--int"></a><span data-ttu-id="4b8ce-109">場所: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4b8ce-109">location : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4b8ce-110">インデックス。ここで `output[location] == pauli` 、 `output` はこの関数の出力です。</span><span class="sxs-lookup"><span data-stu-id="4b8ce-110">An index such that `output[location] == pauli`, where `output` is the output of this function.</span></span>


### <a name="n--int"></a><span data-ttu-id="4b8ce-111">n: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4b8ce-111">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4b8ce-112">返される配列の長さ。</span><span class="sxs-lookup"><span data-stu-id="4b8ce-112">Length of the array to be returned.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="4b8ce-113">出力: [P# li](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="4b8ce-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="example"></a><span data-ttu-id="4b8ce-114">例</span><span class="sxs-lookup"><span data-stu-id="4b8ce-114">Example</span></span>

<span data-ttu-id="4b8ce-115">配列を取得するには、次のようにし `[PauliI, PauliI, PauliX, PauliI]` ます。</span><span class="sxs-lookup"><span data-stu-id="4b8ce-115">To obtain the array `[PauliI, PauliI, PauliX, PauliI]`:</span></span>

```qsharp
EmbedPauli(PauliX, 2, 3);
```