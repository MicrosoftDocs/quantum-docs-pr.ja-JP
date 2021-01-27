---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: すべての関数の関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: b953fb8f5737956e8597cd90a7d6bfc0bafce4e3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835616"
---
# <a name="expandedcoefficients-function"></a><span data-ttu-id="a4a2c-102">すべての関数の関数</span><span class="sxs-lookup"><span data-stu-id="a4a2c-102">ExpandedCoefficients function</span></span>

<span data-ttu-id="a4a2c-103">名前空間: [JordanWigner です。 VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="a4a2c-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="a4a2c-104">パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="a4a2c-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="a4a2c-105">Jordan-Wigner 係数のコンパクト表現を拡張して、これらの用語と、それらの用語の間の一対一のマッピングを取得します。</span><span class="sxs-lookup"><span data-stu-id="a4a2c-105">Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.</span></span>

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="a4a2c-106">入力</span><span class="sxs-lookup"><span data-stu-id="a4a2c-106">Input</span></span>

### <a name="coeff--double"></a><span data-ttu-id="a4a2c-107">係数: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a4a2c-107">coeff : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a4a2c-108">Jordan-Wigner Hamiltonian データ構造体から読み取られる係数の配列。</span><span class="sxs-lookup"><span data-stu-id="a4a2c-108">An array of coefficients, as read from the Jordan-Wigner Hamiltonian data structure.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="a4a2c-109">termType: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a4a2c-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a4a2c-110">Jordan-Wigner 用語の型。</span><span class="sxs-lookup"><span data-stu-id="a4a2c-110">The type of the Jordan-Wigner term.</span></span>



## <a name="output--double"></a><span data-ttu-id="a4a2c-111">出力: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a4a2c-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a4a2c-112">係数の拡張された配列 (1 つの条件につき1つ)。</span><span class="sxs-lookup"><span data-stu-id="a4a2c-112">Expanded arrays of coefficients, one per Pauli term.</span></span>