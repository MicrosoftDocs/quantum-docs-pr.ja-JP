---
uid: Microsoft.Quantum.Canon.RAll1
title: RAll1 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll1
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.
ms.openlocfilehash: 45892f9811faf56d7b9a0eb34e4bde0a32d5586d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715626"
---
# <a name="rall1-operation"></a><span data-ttu-id="25a3b-102">RAll1 操作</span><span class="sxs-lookup"><span data-stu-id="25a3b-102">RAll1 operation</span></span>

<span data-ttu-id="25a3b-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="25a3b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="25a3b-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="25a3b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="25a3b-105">フェーズシフト操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="25a3b-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="25a3b-106">$R = \ bold one-(1-e ^ {i \phi}) \ket{1\cdots 1} \bra{1\cdots 1} $。</span><span class="sxs-lookup"><span data-stu-id="25a3b-106">$R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>

```qsharp
operation RAll1 (phase : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="25a3b-107">入力</span><span class="sxs-lookup"><span data-stu-id="25a3b-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="25a3b-108">フェーズ: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="25a3b-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="25a3b-109">フェーズ $ \ phi $ は、状態 $ \ket{1\cdots 1} \bra{1\cdots 1} $ に適用されています。</span><span class="sxs-lookup"><span data-stu-id="25a3b-109">The phase $\phi$ applied to state $\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="25a3b-110">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="25a3b-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="25a3b-111">$R $ によって回転される状態を持つレジスタ。</span><span class="sxs-lookup"><span data-stu-id="25a3b-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="25a3b-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="25a3b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

