---
uid: Microsoft.Quantum.Synthesis.Extended
title: 拡張関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Extended
qsharp.summary: Extends a spectrum by inverted coefficients
ms.openlocfilehash: 1855f3cab98c5fbf08c4505b90423df50cbec95b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855469"
---
# <a name="extended-function"></a><span data-ttu-id="aeef1-102">拡張関数</span><span class="sxs-lookup"><span data-stu-id="aeef1-102">Extended function</span></span>

<span data-ttu-id="aeef1-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="aeef1-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="aeef1-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aeef1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aeef1-105">反転係数でスペクトルを拡張します</span><span class="sxs-lookup"><span data-stu-id="aeef1-105">Extends a spectrum by inverted coefficients</span></span>

```qsharp
function Extended (spectrum : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="aeef1-106">入力</span><span class="sxs-lookup"><span data-stu-id="aeef1-106">Input</span></span>

### <a name="spectrum--int"></a><span data-ttu-id="aeef1-107">スペクトラム: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="aeef1-107">spectrum : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="aeef1-108">スペクトル係数</span><span class="sxs-lookup"><span data-stu-id="aeef1-108">Spectral coefficients</span></span>



## <a name="output--int"></a><span data-ttu-id="aeef1-109">出力: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="aeef1-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="aeef1-110">係数の後に逆コピーが続く</span><span class="sxs-lookup"><span data-stu-id="aeef1-110">Coefficients followed by inverted copy</span></span>

## <a name="example"></a><span data-ttu-id="aeef1-111">例</span><span class="sxs-lookup"><span data-stu-id="aeef1-111">Example</span></span>

```qsharp
Extended([2, 2, 2, -2]); // [2, 2, 2, -2, -2, -2, -2, 2]
```