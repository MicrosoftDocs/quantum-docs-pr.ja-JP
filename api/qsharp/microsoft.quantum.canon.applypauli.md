---
uid: Microsoft.Quantum.Canon.ApplyPauli
title: 実行操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauli
qsharp.summary: Given a multi-qubit Pauli operator, applies the corresponding operation to a register.
ms.openlocfilehash: b3557c6d8b5a90019f6d4cfa7b405475a3ab39fb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844754"
---
# <a name="applypauli-operation"></a><span data-ttu-id="2a005-102">実行操作</span><span class="sxs-lookup"><span data-stu-id="2a005-102">ApplyPauli operation</span></span>

<span data-ttu-id="2a005-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2a005-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2a005-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2a005-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2a005-105">指定された複数の演算子がある場合、対応する操作をレジスタに適用します。</span><span class="sxs-lookup"><span data-stu-id="2a005-105">Given a multi-qubit Pauli operator, applies the corresponding operation to a register.</span></span>

```qsharp
operation ApplyPauli (pauli : Pauli[], target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2a005-106">入力</span><span class="sxs-lookup"><span data-stu-id="2a005-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="2a005-107">[p# li []](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="2a005-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="2a005-108">シングル qubit の P# li 演算子の配列として表されるマルチ qubit の Pan Li 演算子。</span><span class="sxs-lookup"><span data-stu-id="2a005-108">A multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="2a005-109">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2a005-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2a005-110">を登録して、に指定された P# li 操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="2a005-110">Register to apply the given Pauli operation on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2a005-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2a005-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="2a005-112">例</span><span class="sxs-lookup"><span data-stu-id="2a005-112">Example</span></span>

<span data-ttu-id="2a005-113">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="2a005-113">The following are equivalent:</span></span>

```qsharp
ApplyPauli([PauliY, PauliZ, PauliX], target);
```

<span data-ttu-id="2a005-114">and</span><span class="sxs-lookup"><span data-stu-id="2a005-114">and</span></span>

```qsharp
Y(target[0]);
Z(target[1]);
X(target[2]);
```