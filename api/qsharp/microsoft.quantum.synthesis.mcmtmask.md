---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: MCMTMask ユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 3c2debbb1f2019c7188dcb00f8ac09154fd4fd4f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203021"
---
# <a name="mcmtmask-user-defined-type"></a><span data-ttu-id="2002d-102">MCMTMask ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="2002d-102">MCMTMask user defined type</span></span>

<span data-ttu-id="2002d-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="2002d-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="2002d-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2002d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2002d-105">複数制御されたマルチターゲット Toffoli ゲートを表す型。</span><span class="sxs-lookup"><span data-stu-id="2002d-105">A type to represent a multiple-controlled multiple-target Toffoli gate.</span></span>

<span data-ttu-id="2002d-106">最初の整数は、制御線のビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="2002d-106">The first integer is a bit mask for control lines.</span></span>  <span data-ttu-id="2002d-107">設定されるビットインデックスは、制御行インデックスに対応します。</span><span class="sxs-lookup"><span data-stu-id="2002d-107">Bit indexes which are set correspond to control line indexes.</span></span>

<span data-ttu-id="2002d-108">2番目の整数は、ターゲット行のビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="2002d-108">The second integer is a bit mask for target lines.</span></span>  <span data-ttu-id="2002d-109">設定されているビットインデックスは、ターゲットの行インデックスに対応します。</span><span class="sxs-lookup"><span data-stu-id="2002d-109">Bit indexes which are set correspond to target line indexes.</span></span>

<span data-ttu-id="2002d-110">両方の整数のビットインデックスは、不整合である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2002d-110">The bit indexes of both integers must be disjoint.</span></span>

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a><span data-ttu-id="2002d-111">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="2002d-111">Named Items</span></span>

### <a name="controlmask--int"></a><span data-ttu-id="2002d-112">ControlMask: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2002d-112">ControlMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="targetmask--int"></a><span data-ttu-id="2002d-113">TargetMask: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2002d-113">TargetMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

