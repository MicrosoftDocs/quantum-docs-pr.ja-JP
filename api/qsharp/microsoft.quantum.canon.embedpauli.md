---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: c78406aa4557834ac2bb40cf1847696d075e5135
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716200"
---
# <a name="embedpauli-function"></a><span data-ttu-id="b90f3-102">EmbedPauli 関数</span><span class="sxs-lookup"><span data-stu-id="b90f3-102">EmbedPauli function</span></span>

<span data-ttu-id="b90f3-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b90f3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b90f3-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b90f3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b90f3-105">Single qubit の P# li 演算子と qubit のインデックスが指定されている場合、そのインデックスの指定された単一の qubit 演算子と `PauliI` 他のすべてのインデックスで、マルチ qubit の P# li 演算子を返します。</span><span class="sxs-lookup"><span data-stu-id="b90f3-105">Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="b90f3-106">入力</span><span class="sxs-lookup"><span data-stu-id="b90f3-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="b90f3-107">p# li: [p#](xref:microsoft.quantum.lang-ref.pauli) li</span><span class="sxs-lookup"><span data-stu-id="b90f3-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="b90f3-108">指定された場所に配置される単一の qubit の P# li 演算子。</span><span class="sxs-lookup"><span data-stu-id="b90f3-108">A single-qubit Pauli operator to be placed at the given location.</span></span>


### <a name="location--int"></a><span data-ttu-id="b90f3-109">場所: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b90f3-109">location : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b90f3-110">インデックス。ここで `output[location] == pauli` 、 `output` はこの関数の出力です。</span><span class="sxs-lookup"><span data-stu-id="b90f3-110">An index such that `output[location] == pauli`, where `output` is the output of this function.</span></span>


### <a name="n--int"></a><span data-ttu-id="b90f3-111">n: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b90f3-111">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b90f3-112">返される配列の長さ。</span><span class="sxs-lookup"><span data-stu-id="b90f3-112">Length of the array to be returned.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="b90f3-113">出力: [P# li](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="b90f3-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

