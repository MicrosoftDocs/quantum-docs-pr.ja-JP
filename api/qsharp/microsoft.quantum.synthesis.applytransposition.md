---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 1bd6f9580e09752f1de75927d6bb35417bb1ff21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725262"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="cee68-102">ApplyTransposition 操作</span><span class="sxs-lookup"><span data-stu-id="cee68-102">ApplyTransposition operation</span></span>

<span data-ttu-id="cee68-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="cee68-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="cee68-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cee68-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="cee68-105">説明</span><span class="sxs-lookup"><span data-stu-id="cee68-105">Description</span></span>

<span data-ttu-id="cee68-106">この操作では、インデックスの振幅を、 `a` `b` 長さ $n $ の指定した状態ベクトルのインデックス位置の振幅でスワップし `register` ます。</span><span class="sxs-lookup"><span data-stu-id="cee68-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="cee68-107">が `a` に等しい場合 `b` 、状態ベクトルは変更されません。</span><span class="sxs-lookup"><span data-stu-id="cee68-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="cee68-108">入力</span><span class="sxs-lookup"><span data-stu-id="cee68-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="cee68-109">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cee68-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cee68-110">最初のインデックス (0 ~ $ 2 ^ n-$1 の値である必要があります)</span><span class="sxs-lookup"><span data-stu-id="cee68-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="cee68-111">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cee68-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cee68-112">2番目のインデックス (0 ~ $ 2 ^ n-$1 の値である必要があります)</span><span class="sxs-lookup"><span data-stu-id="cee68-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="cee68-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="cee68-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="cee68-114">転調が適用される $n $ qubits の一覧。</span><span class="sxs-lookup"><span data-stu-id="cee68-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cee68-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cee68-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

