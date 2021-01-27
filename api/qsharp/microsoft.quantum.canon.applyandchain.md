---
uid: Microsoft.Quantum.Canon.ApplyAndChain
title: ApplyAndChain 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAndChain
qsharp.summary: Computes a chain of AND gates
ms.openlocfilehash: 3991ded1a9c70bf4b58d19b0304a1df3b31896d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842015"
---
# <a name="applyandchain-operation"></a><span data-ttu-id="7b5fd-102">ApplyAndChain 操作</span><span class="sxs-lookup"><span data-stu-id="7b5fd-102">ApplyAndChain operation</span></span>

<span data-ttu-id="7b5fd-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7b5fd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7b5fd-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7b5fd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7b5fd-105">ゲートとゲートのチェーンを計算します</span><span class="sxs-lookup"><span data-stu-id="7b5fd-105">Computes a chain of AND gates</span></span>

```qsharp
operation ApplyAndChain (auxRegister : Qubit[], ctrlRegister : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="7b5fd-106">説明</span><span class="sxs-lookup"><span data-stu-id="7b5fd-106">Description</span></span>

<span data-ttu-id="7b5fd-107">一時的な結果を計算する補助 qubits を明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b5fd-107">The auxiliary qubits to compute temporary results must be specified explicitly.</span></span>
<span data-ttu-id="7b5fd-108">少なくとも2つのコントロールがある場合、そのレジスタの長さはになり `Length(ctrlRegister) - 2` ます。それ以外の場合は、長さが0になります。</span><span class="sxs-lookup"><span data-stu-id="7b5fd-108">The length of that register is `Length(ctrlRegister) - 2`, if there are at least two controls, otherwise the length is 0.</span></span>

## <a name="input"></a><span data-ttu-id="7b5fd-109">入力</span><span class="sxs-lookup"><span data-stu-id="7b5fd-109">Input</span></span>

### <a name="auxregister--qubit"></a><span data-ttu-id="7b5fd-110">auxRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7b5fd-110">auxRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="ctrlregister--qubit"></a><span data-ttu-id="7b5fd-111">ctrlRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7b5fd-111">ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="7b5fd-112">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7b5fd-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="7b5fd-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7b5fd-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

