---
uid: Microsoft.Quantum.Canon.RAll1
title: RAll1 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll1
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.
ms.openlocfilehash: 36e460f93b4349bc2e3da9bfb22cb0aa82ef1795
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205536"
---
# <a name="rall1-operation"></a><span data-ttu-id="e6650-102">RAll1 操作</span><span class="sxs-lookup"><span data-stu-id="e6650-102">RAll1 operation</span></span>

<span data-ttu-id="e6650-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e6650-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e6650-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e6650-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e6650-105">フェーズシフト操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e6650-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="e6650-106">$R = \ bold one-(1-e ^ {i \phi}) \ket{1\cdots 1} \bra{1\cdots 1} $。</span><span class="sxs-lookup"><span data-stu-id="e6650-106">$R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>

```qsharp
operation RAll1 (phase : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e6650-107">入力</span><span class="sxs-lookup"><span data-stu-id="e6650-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="e6650-108">フェーズ: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e6650-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e6650-109">フェーズ $ \ phi $ は、状態 $ \ket{1\cdots 1} \bra{1\cdots 1} $ に適用されています。</span><span class="sxs-lookup"><span data-stu-id="e6650-109">The phase $\phi$ applied to state $\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="e6650-110">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e6650-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e6650-111">$R $ によって回転される状態を持つレジスタ。</span><span class="sxs-lookup"><span data-stu-id="e6650-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e6650-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e6650-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

