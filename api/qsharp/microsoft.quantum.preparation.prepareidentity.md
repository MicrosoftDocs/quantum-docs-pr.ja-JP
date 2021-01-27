---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: Id の処理操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: ec7e813110ccd9e6d499fc469fa27249a182b870
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855886"
---
# <a name="prepareidentity-operation"></a><span data-ttu-id="d9ad7-102">Id の処理操作</span><span class="sxs-lookup"><span data-stu-id="d9ad7-102">PrepareIdentity operation</span></span>

<span data-ttu-id="d9ad7-103">名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="d9ad7-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="d9ad7-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d9ad7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d9ad7-105">レジスタが指定されている場合、そのレジスタを下回っ混合状態で準備します。</span><span class="sxs-lookup"><span data-stu-id="d9ad7-105">Given a register, prepares that register in the maximally mixed state.</span></span>

<span data-ttu-id="d9ad7-106">レジスタは、depolarizing チャネル全体を各 qubit に適用することで、$/bold done/2 ^ N $ 状態で準備されます。ここで $N $ はレジスタの長さです。</span><span class="sxs-lookup"><span data-stu-id="d9ad7-106">The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.</span></span>

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="d9ad7-107">入力</span><span class="sxs-lookup"><span data-stu-id="d9ad7-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="d9ad7-108">register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d9ad7-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d9ad7-109">前に説明した方法で状態を depolarized するレジスタ。</span><span class="sxs-lookup"><span data-stu-id="d9ad7-109">A register whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d9ad7-110">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d9ad7-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="d9ad7-111">参照</span><span class="sxs-lookup"><span data-stu-id="d9ad7-111">See Also</span></span>

- [<span data-ttu-id="d9ad7-112">PrepareSingleQubitIdentity の準備</span><span class="sxs-lookup"><span data-stu-id="d9ad7-112">Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity</span></span>](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)