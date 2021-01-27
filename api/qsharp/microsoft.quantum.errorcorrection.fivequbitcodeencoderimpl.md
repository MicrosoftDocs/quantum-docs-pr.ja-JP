---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: FiveQubitCodeEncoderImpl 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: 0a40d9674c011567b2fa9c838f31a0ee115e4268
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826080"
---
# <a name="fivequbitcodeencoderimpl-operation"></a><span data-ttu-id="bf582-102">FiveQubitCodeEncoderImpl 操作</span><span class="sxs-lookup"><span data-stu-id="bf582-102">FiveQubitCodeEncoderImpl operation</span></span>

<span data-ttu-id="bf582-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="bf582-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="bf582-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bf582-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bf582-105">5 qubit エンコーダーとデコーダーの両方を実装するために使用されるプライベート操作。</span><span class="sxs-lookup"><span data-stu-id="bf582-105">Private operation used to implement both the 5 qubit encoder and decoder.</span></span>

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="bf582-106">入力</span><span class="sxs-lookup"><span data-stu-id="bf582-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="bf582-107">データ: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bf582-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="bf582-108">入力 qubit である1つの qubit を保持する配列。</span><span class="sxs-lookup"><span data-stu-id="bf582-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="bf582-109">スクラッチ: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bf582-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="bf582-110">冗長性を追加する4つの qubits を保持する配列。</span><span class="sxs-lookup"><span data-stu-id="bf582-110">an array holding 4 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bf582-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bf582-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="bf582-112">解説</span><span class="sxs-lookup"><span data-stu-id="bf582-112">Remarks</span></span>

<span data-ttu-id="bf582-113">選択された特定のエンコーダーは、ペーパー V. KliuchMaslov 氏と d. "Phys. Phys. 88, 052307 (2013); から取得されましたが、これは、「Clifford 回線の最適化」です。 https://arxiv.org/abs/1305.0810、図 4b) では、合計11ゲートが必要です。</span><span class="sxs-lookup"><span data-stu-id="bf582-113">The particular encoder chosen was taken from the paper V. Kliuchnikov and D. Maslov, "Optimization of Clifford Circuits," Phys. Rev. Phys. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figure 4b) and requires a total of 11 gates.</span></span>