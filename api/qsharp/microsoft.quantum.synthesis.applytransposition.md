---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 46cf8c2c891aa02b0d8a1397e6c2b7a4b8618048
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855573"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="f0b66-102">ApplyTransposition 操作</span><span class="sxs-lookup"><span data-stu-id="f0b66-102">ApplyTransposition operation</span></span>

<span data-ttu-id="f0b66-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="f0b66-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="f0b66-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f0b66-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="f0b66-105">説明</span><span class="sxs-lookup"><span data-stu-id="f0b66-105">Description</span></span>

<span data-ttu-id="f0b66-106">この操作では、インデックスの振幅を、 `a` `b` 長さ $n $ の指定した状態ベクトルのインデックス位置の振幅でスワップし `register` ます。</span><span class="sxs-lookup"><span data-stu-id="f0b66-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="f0b66-107">が `a` に等しい場合 `b` 、状態ベクトルは変更されません。</span><span class="sxs-lookup"><span data-stu-id="f0b66-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="f0b66-108">入力</span><span class="sxs-lookup"><span data-stu-id="f0b66-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="f0b66-109">a: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f0b66-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f0b66-110">最初のインデックス (0 ~ $ 2 ^ n-$1 の値である必要があります)</span><span class="sxs-lookup"><span data-stu-id="f0b66-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="f0b66-111">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f0b66-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f0b66-112">2番目のインデックス (0 ~ $ 2 ^ n-$1 の値である必要があります)</span><span class="sxs-lookup"><span data-stu-id="f0b66-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="f0b66-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f0b66-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f0b66-114">転調が適用される $n $ qubits の一覧。</span><span class="sxs-lookup"><span data-stu-id="f0b66-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f0b66-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f0b66-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="f0b66-116">例</span><span class="sxs-lookup"><span data-stu-id="f0b66-116">Example</span></span>

<span data-ttu-id="f0b66-117">2つの qubits に対して、number of 法則 # | 1 \ \rangle $、$ | 2 \ \rangle $、$ | 3 \ \rangle $ という uniform を準備します。</span><span class="sxs-lookup"><span data-stu-id="f0b66-117">Prepare a uniform superposition of number states $|1\rangle$, $|2\rangle$, and $|3\rangle$ on 2 qubits.</span></span>

```qsharp
using (qubits = Qubit[2]) {
  let register = LittleEndian(qubits);
  PrepareUniformSuperposition(3, register);
  ApplyTransposition(0, 3, register);
}
```