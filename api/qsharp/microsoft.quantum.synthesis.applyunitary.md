---
uid: Microsoft.Quantum.Synthesis.ApplyUnitary
title: ApplyUnitary 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyUnitary
qsharp.summary: >-
  Applies gate defined by 2^n x 2^n unitary matrix.

  Fails if matrix is not unitary, or has wrong size.
ms.openlocfilehash: 58215d3b05b8c6974e979d21a13869f27b436310
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859217"
---
# <a name="applyunitary-operation"></a><span data-ttu-id="8ebd4-102">ApplyUnitary 操作</span><span class="sxs-lookup"><span data-stu-id="8ebd4-102">ApplyUnitary operation</span></span>

<span data-ttu-id="8ebd4-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="8ebd4-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="8ebd4-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8ebd4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8ebd4-105">2 ^ n x 2 ^ n のユニタリ行列で定義されているゲートを適用します。</span><span class="sxs-lookup"><span data-stu-id="8ebd4-105">Applies gate defined by 2^n x 2^n unitary matrix.</span></span>

<span data-ttu-id="8ebd4-106">マトリックスがユニタリでない場合、またはサイズが間違っている場合に失敗します。</span><span class="sxs-lookup"><span data-stu-id="8ebd4-106">Fails if matrix is not unitary, or has wrong size.</span></span>

```qsharp
operation ApplyUnitary (unitary : Microsoft.Quantum.Math.Complex[][], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8ebd4-107">入力</span><span class="sxs-lookup"><span data-stu-id="8ebd4-107">Input</span></span>

### <a name="unitary--complex"></a><span data-ttu-id="8ebd4-108">ユニタリ: [Complex](xref:Microsoft.Quantum.Math.Complex)[] []</span><span class="sxs-lookup"><span data-stu-id="8ebd4-108">unitary : [Complex](xref:Microsoft.Quantum.Math.Complex)[][]</span></span>

<span data-ttu-id="8ebd4-109">操作を説明する 2 ^ n x 2 ^ n のユニタリ行列。</span><span class="sxs-lookup"><span data-stu-id="8ebd4-109">2^n x 2^n unitary matrix describing the operation.</span></span>
<span data-ttu-id="8ebd4-110">マトリックスがユニタリでない場合、または適切なサイズでない場合、は例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="8ebd4-110">If matrix is not unitary or not of suitable size, throws an exception.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="8ebd4-111">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8ebd4-111">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8ebd4-112">に、長さ n の操作レジスタを適用する qubits を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ebd4-112">Qubits to which apply the operation - register of length n.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8ebd4-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8ebd4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

