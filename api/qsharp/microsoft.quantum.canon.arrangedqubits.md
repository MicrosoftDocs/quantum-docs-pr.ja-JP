---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: 並べ替え Edqubits 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 07a4ed5fe99dedb333246f7161d157dcd01a01da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841073"
---
# <a name="arrangedqubits-function"></a><span data-ttu-id="0e4d7-102">並べ替え Edqubits 関数</span><span class="sxs-lookup"><span data-stu-id="0e4d7-102">ArrangedQubits function</span></span>

<span data-ttu-id="0e4d7-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0e4d7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0e4d7-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0e4d7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0e4d7-105">インデックスに基づいてコントロール、ターゲット、ヘルパーの qubits を整列する</span><span class="sxs-lookup"><span data-stu-id="0e4d7-105">Arrange control, target, and helper qubits according to an index</span></span>

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a><span data-ttu-id="0e4d7-106">説明</span><span class="sxs-lookup"><span data-stu-id="0e4d7-106">Description</span></span>

<span data-ttu-id="0e4d7-107">インデックス0のターゲットを持つ Qubit 配列を返し、インデックス 2 ^ i のコントロール i を返します。</span><span class="sxs-lookup"><span data-stu-id="0e4d7-107">Returns a Qubit array with target at index 0, and control i at index 2^i.</span></span>  <span data-ttu-id="0e4d7-108">ヘルパーの qubits は、配列内の他のすべての位置に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="0e4d7-108">The helper qubits are inserted to all other positions in the array.</span></span>

## <a name="input"></a><span data-ttu-id="0e4d7-109">入力</span><span class="sxs-lookup"><span data-stu-id="0e4d7-109">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="0e4d7-110">コントロール: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0e4d7-110">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="0e4d7-111">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0e4d7-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>




### <a name="helper--qubit"></a><span data-ttu-id="0e4d7-112">ヘルパー: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0e4d7-112">helper : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--qubit"></a><span data-ttu-id="0e4d7-113">出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0e4d7-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

