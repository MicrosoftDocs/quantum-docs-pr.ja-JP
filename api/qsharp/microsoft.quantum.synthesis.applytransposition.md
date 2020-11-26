---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: ca22b090f2b2613f07caef698941ea608374ab1e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203316"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="6bab4-102">ApplyTransposition 操作</span><span class="sxs-lookup"><span data-stu-id="6bab4-102">ApplyTransposition operation</span></span>

<span data-ttu-id="6bab4-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="6bab4-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="6bab4-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6bab4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="6bab4-105">説明</span><span class="sxs-lookup"><span data-stu-id="6bab4-105">Description</span></span>

<span data-ttu-id="6bab4-106">この操作では、インデックスの振幅を、 `a` `b` 長さ $n $ の指定した状態ベクトルのインデックス位置の振幅でスワップし `register` ます。</span><span class="sxs-lookup"><span data-stu-id="6bab4-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="6bab4-107">が `a` に等しい場合 `b` 、状態ベクトルは変更されません。</span><span class="sxs-lookup"><span data-stu-id="6bab4-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="6bab4-108">入力</span><span class="sxs-lookup"><span data-stu-id="6bab4-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="6bab4-109">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6bab4-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6bab4-110">最初のインデックス (0 ~ $ 2 ^ n-$1 の値である必要があります)</span><span class="sxs-lookup"><span data-stu-id="6bab4-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="6bab4-111">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6bab4-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6bab4-112">2番目のインデックス (0 ~ $ 2 ^ n-$1 の値である必要があります)</span><span class="sxs-lookup"><span data-stu-id="6bab4-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="6bab4-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6bab4-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6bab4-114">転調が適用される $n $ qubits の一覧。</span><span class="sxs-lookup"><span data-stu-id="6bab4-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6bab4-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6bab4-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

