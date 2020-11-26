---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: Id の処理操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: 6e0a43e61e3c49edef94db63f07ed29132d84c83
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210439"
---
# <a name="prepareidentity-operation"></a><span data-ttu-id="0e8e9-102">Id の処理操作</span><span class="sxs-lookup"><span data-stu-id="0e8e9-102">PrepareIdentity operation</span></span>

<span data-ttu-id="0e8e9-103">名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="0e8e9-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="0e8e9-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0e8e9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0e8e9-105">レジスタが指定されている場合、そのレジスタを下回っ混合状態で準備します。</span><span class="sxs-lookup"><span data-stu-id="0e8e9-105">Given a register, prepares that register in the maximally mixed state.</span></span>

<span data-ttu-id="0e8e9-106">レジスタは、depolarizing チャネル全体を各 qubit に適用することで、$/bold done/2 ^ N $ 状態で準備されます。ここで $N $ はレジスタの長さです。</span><span class="sxs-lookup"><span data-stu-id="0e8e9-106">The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.</span></span>

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="0e8e9-107">入力</span><span class="sxs-lookup"><span data-stu-id="0e8e9-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="0e8e9-108">register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0e8e9-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0e8e9-109">前に説明した方法で状態を depolarized するレジスタ。</span><span class="sxs-lookup"><span data-stu-id="0e8e9-109">A register whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0e8e9-110">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0e8e9-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="0e8e9-111">参照</span><span class="sxs-lookup"><span data-stu-id="0e8e9-111">See Also</span></span>

- [<span data-ttu-id="0e8e9-112">PrepareSingleQubitIdentity の準備</span><span class="sxs-lookup"><span data-stu-id="0e8e9-112">Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity</span></span>](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)