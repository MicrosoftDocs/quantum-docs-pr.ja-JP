---
uid: Microsoft.Quantum.Canon.ApplyPauli
title: 実行操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauli
qsharp.summary: Given a multi-qubit Pauli operator, applies the corresponding operation to a register.
ms.openlocfilehash: ccf8e1b3dbe5d4cd916a581aeab190ab0cff2021
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717815"
---
# <a name="applypauli-operation"></a><span data-ttu-id="c7e81-102">実行操作</span><span class="sxs-lookup"><span data-stu-id="c7e81-102">ApplyPauli operation</span></span>

<span data-ttu-id="c7e81-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c7e81-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c7e81-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c7e81-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c7e81-105">指定された複数の演算子がある場合、対応する操作をレジスタに適用します。</span><span class="sxs-lookup"><span data-stu-id="c7e81-105">Given a multi-qubit Pauli operator, applies the corresponding operation to a register.</span></span>

```qsharp
operation ApplyPauli (pauli : Pauli[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c7e81-106">入力</span><span class="sxs-lookup"><span data-stu-id="c7e81-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="c7e81-107">[p# li []](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="c7e81-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="c7e81-108">シングル qubit の P# li 演算子の配列として表されるマルチ qubit の Pan Li 演算子。</span><span class="sxs-lookup"><span data-stu-id="c7e81-108">A multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="c7e81-109">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c7e81-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c7e81-110">を登録して、に指定された P# li 操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="c7e81-110">Register to apply the given Pauli operation on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c7e81-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c7e81-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

