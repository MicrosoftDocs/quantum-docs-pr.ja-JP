---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: d39fcd6b2987b3a4f69df13fa83b69a199d6eddb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840886"
---
# <a name="composedoutput-function"></a><span data-ttu-id="a3dde-102">ComposedOutput 関数</span><span class="sxs-lookup"><span data-stu-id="a3dde-102">ComposedOutput function</span></span>

<span data-ttu-id="a3dde-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a3dde-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a3dde-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a3dde-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a3dde-105">`inner`指定された入力に対するとの構成の出力を返し `outer` ます。</span><span class="sxs-lookup"><span data-stu-id="a3dde-105">Returns the output of the composition of `inner` and `outer` for a given input.</span></span>

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a><span data-ttu-id="a3dde-106">入力</span><span class="sxs-lookup"><span data-stu-id="a3dde-106">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="a3dde-107">外部: ' U-> ' V</span><span class="sxs-lookup"><span data-stu-id="a3dde-107">outer : 'U -> 'V</span></span>




### <a name="inner--t---u"></a><span data-ttu-id="a3dde-108">内部: > ' U</span><span class="sxs-lookup"><span data-stu-id="a3dde-108">inner : 'T -> 'U</span></span>




### <a name="target--t"></a><span data-ttu-id="a3dde-109">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="a3dde-109">target : 'T</span></span>





## <a name="output--v"></a><span data-ttu-id="a3dde-110">出力: ' V</span><span class="sxs-lookup"><span data-stu-id="a3dde-110">Output : 'V</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a3dde-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="a3dde-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a3dde-112">&</span><span class="sxs-lookup"><span data-stu-id="a3dde-112">'T</span></span>


### <a name="u"></a><span data-ttu-id="a3dde-113">' U</span><span class="sxs-lookup"><span data-stu-id="a3dde-113">'U</span></span>


### <a name="v"></a><span data-ttu-id="a3dde-114">' V</span><span class="sxs-lookup"><span data-stu-id="a3dde-114">'V</span></span>

