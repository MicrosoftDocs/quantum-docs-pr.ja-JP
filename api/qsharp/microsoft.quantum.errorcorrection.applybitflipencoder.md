---
uid: Microsoft.Quantum.ErrorCorrection.ApplyBitFlipEncoder
title: ApplyBitFlipEncoder 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: ApplyBitFlipEncoder
qsharp.summary: >-
  Private operation used to implement both the bit flip encoder and decoder.

  Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`. In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.
ms.openlocfilehash: 4d78cbb5892aabc600321185641bbf217bd4d745
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712518"
---
# <a name="applybitflipencoder-operation"></a><span data-ttu-id="14e44-102">ApplyBitFlipEncoder 操作</span><span class="sxs-lookup"><span data-stu-id="14e44-102">ApplyBitFlipEncoder operation</span></span>

<span data-ttu-id="14e44-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="14e44-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="14e44-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="14e44-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="14e44-105">ビットフリップエンコーダーとデコーダーの両方を実装するために使用されるプライベート操作。</span><span class="sxs-lookup"><span data-stu-id="14e44-105">Private operation used to implement both the bit flip encoder and decoder.</span></span>

<span data-ttu-id="14e44-106">このエンコーダーは、インプレース整合性復旧を利用できることに注意してください。この場合、の初期状態で記述されたエラーが "発生" し `auxQubits` ます。</span><span class="sxs-lookup"><span data-stu-id="14e44-106">Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`.</span></span>
<span data-ttu-id="14e44-107">特に、 `auxQubits` が最初に状態が $ \ket $ の場合、これにより、エンコードされ {10} た qubit で $X _1 $ error が発生します。</span><span class="sxs-lookup"><span data-stu-id="14e44-107">In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.</span></span>

```qsharp
operation ApplyBitFlipEncoder (coherentRecovery : Bool, data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="14e44-108">入力</span><span class="sxs-lookup"><span data-stu-id="14e44-108">Input</span></span>

### <a name="coherentrecovery--bool"></a><span data-ttu-id="14e44-109">coherentRecovery: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="14e44-109">coherentRecovery : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="data--qubit"></a><span data-ttu-id="14e44-110">データ: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="14e44-110">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="scratch--qubit"></a><span data-ttu-id="14e44-111">スクラッチ: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="14e44-111">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="14e44-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="14e44-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="14e44-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="14e44-113">References</span></span>

- <span data-ttu-id="14e44-114">doi: 10.1103/PhysRevA</span><span class="sxs-lookup"><span data-stu-id="14e44-114">doi:10.1103/PhysRevA.85.044302</span></span>