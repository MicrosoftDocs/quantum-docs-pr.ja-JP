---
uid: Microsoft.Quantum.Canon.RAll1
title: RAll1 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll1
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.
ms.openlocfilehash: f4159a6cc0e0b4f18f418a53a309b5ce527b2608
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852259"
---
# <a name="rall1-operation"></a><span data-ttu-id="d3baf-102">RAll1 操作</span><span class="sxs-lookup"><span data-stu-id="d3baf-102">RAll1 operation</span></span>

<span data-ttu-id="d3baf-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d3baf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d3baf-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d3baf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d3baf-105">フェーズシフト操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d3baf-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="d3baf-106">$R = \ bold one-(1-e ^ {i \phi}) \ket{1\cdots 1} \bra{1\cdots 1} $。</span><span class="sxs-lookup"><span data-stu-id="d3baf-106">$R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>

```qsharp
operation RAll1 (phase : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d3baf-107">入力</span><span class="sxs-lookup"><span data-stu-id="d3baf-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="d3baf-108">フェーズ: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d3baf-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d3baf-109">フェーズ $ \ phi $ は、状態 $ \ket{1\cdots 1} \bra{1\cdots 1} $ に適用されています。</span><span class="sxs-lookup"><span data-stu-id="d3baf-109">The phase $\phi$ applied to state $\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="d3baf-110">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d3baf-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d3baf-111">$R $ によって回転される状態を持つレジスタ。</span><span class="sxs-lookup"><span data-stu-id="d3baf-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d3baf-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d3baf-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

