---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: e9042ca9eac4b8791057037dc5698eb14deadd31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207039"
---
# <a name="embedpauli-function"></a><span data-ttu-id="eafdd-102">EmbedPauli 関数</span><span class="sxs-lookup"><span data-stu-id="eafdd-102">EmbedPauli function</span></span>

<span data-ttu-id="eafdd-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eafdd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eafdd-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eafdd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eafdd-105">Single qubit の P# li 演算子と qubit のインデックスが指定されている場合、そのインデックスの指定された単一の qubit 演算子と `PauliI` 他のすべてのインデックスで、マルチ qubit の P# li 演算子を返します。</span><span class="sxs-lookup"><span data-stu-id="eafdd-105">Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="eafdd-106">入力</span><span class="sxs-lookup"><span data-stu-id="eafdd-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="eafdd-107">p# li: [p#](xref:microsoft.quantum.lang-ref.pauli) li</span><span class="sxs-lookup"><span data-stu-id="eafdd-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="eafdd-108">指定された場所に配置される単一の qubit の P# li 演算子。</span><span class="sxs-lookup"><span data-stu-id="eafdd-108">A single-qubit Pauli operator to be placed at the given location.</span></span>


### <a name="location--int"></a><span data-ttu-id="eafdd-109">場所: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eafdd-109">location : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eafdd-110">インデックス。ここで `output[location] == pauli` 、 `output` はこの関数の出力です。</span><span class="sxs-lookup"><span data-stu-id="eafdd-110">An index such that `output[location] == pauli`, where `output` is the output of this function.</span></span>


### <a name="n--int"></a><span data-ttu-id="eafdd-111">n: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eafdd-111">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eafdd-112">返される配列の長さ。</span><span class="sxs-lookup"><span data-stu-id="eafdd-112">Length of the array to be returned.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="eafdd-113">出力: [P# li](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="eafdd-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

